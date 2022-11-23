
![183239082-09722b8d-9cc7-49a1-9d93-15ce3ab8d752.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662888613883/cJK6RusCM.png align="left")


Minimum hardware requirements:

Node Type	CPU	RAM	Storage
Testnet	4	8GB	160GB

1) Auto_install script


```
wget -O sources https://raw.githubusercontent.com/obajay/nodes-Guides/main/Source/sources && chmod +x sources && ./sources
``` 

2) Manual installation


```
sudo apt update && sudo apt upgrade -y && \
sudo apt install curl tar wget clang pkg-config libssl-dev libleveldb-dev jq build-essential bsdmainutils git make ncdu htop screen unzip bc fail2ban htop -y
``` 

GO 18.3 (one command)


```
ver="1.18.3" && \
cd $HOME && \
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz" && \
sudo rm -rf /usr/local/go && \
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz" && \
rm "go$ver.linux-amd64.tar.gz" && \
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile && \
source $HOME/.bash_profile && \
go version
``` 

Binary 01.08.22


```
git clone -b testnet https://github.com/Source-Protocol-Cosmos/source.git
cd ~/source
make install
``` 

```
sourced version --long | head
``` 


version: v1.0.0-2-ge06b810
commit: e06b810e842e57ec8f5432c9cdd57883a69b3cee


Initialisation


```
sourced init <moniker-name> --chain-id=sourcechain-testnet
``` 

Add wallet


```
sourced keys add <walletName>
sourced keys add <walletName> --recover
``` 

Genesis


```
curl -s  https://raw.githubusercontent.com/Source-Protocol-Cosmos/testnets/master/sourcechain-testnet/genesis.json > ~/.source/config/genesis.json
``` 
*
sha256sum $HOME/.source/config/genesis.json*

2bf556b50a2094f252e0aac75c8018a9d6c0a77ba64ce39811945087f6a5165d genesis.json



Pruning (optional) one command


```
pruning="custom" && \
pruning_keep_recent="100" && \
pruning_keep_every="0" && \
pruning_interval="10" && \
sed -i -e "s/^pruning *=.*/pruning = \"$pruning\"/" $HOME/.source/config/app.toml && \
sed -i -e "s/^pruning-keep-recent *=.*/pruning-keep-recent = \"$pruning_keep_recent\"/" $HOME/.source/config/app.toml && \
sed -i -e "s/^pruning-keep-every *=.*/pruning-keep-every = \"$pruning_keep_every\"/" $HOME/.source/config/app.toml && \
sed -i -e "s/^pruning-interval *=.*/pruning-interval = \"$pruning_interval\"/" $HOME/.source/config/app.toml
``` 


Indexer (optional) one command


```
indexer="null" && \
sed -i -e "s/^indexer *=.*/indexer = \"$indexer\"/" $HOME/.source/config/config.toml
``` 

Set up the minimum gas price and Peers/Seeds/Filter peers


```
sed -i.bak -e "s/^minimum-gas-prices *=.*/minimum-gas-prices = \"0.0usource\"/;" ~/.source/config/app.toml
sed -i -e "s/^filter_peers *=.*/filter_peers = \"true\"/" $HOME/.source/config/config.toml
external_address=$(wget -qO- eth0.me) 
sed -i.bak -e "s/^external_address *=.*/external_address = \"$external_address:26656\"/" $HOME/.source/config/config.toml

peers="6ca675f9d949d5c9afc8849adf7b39bc7fccf74f@164.92.98.17:26656"
sed -i.bak -e "s/^persistent_peers *=.*/persistent_peers = \"$peers\"/" $HOME/.source/config/config.toml

seeds=""
sed -i.bak -e "s/^seeds =.*/seeds = \"$seeds\"/" $HOME/.source/config/config.toml

sed -i 's/max_num_inbound_peers =.*/max_num_inbound_peers = 100/g' $HOME/.source/config/config.toml
sed -i 's/max_num_outbound_peers =.*/max_num_outbound_peers = 100/g' $HOME/.source/config/config.toml
``` 

Download addrbook


```
wget -O $HOME/.source/config/addrbook.json "https://raw.githubusercontent.com/obajay/nodes-Guides/main/Source/addrbook.json"
``` 

Create a service file


```
sudo tee /etc/systemd/system/sourced.service > /dev/null <<EOF
[Unit]
Description=source
After=network-online.target

[Service]
User=$USER
ExecStart=$(which sourced) start
Restart=on-failure
RestartSec=3
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target
EOF
``` 

SnapShot 06.09.22 (0.1 GB) block height --> 2226618


```
# install the node as standard, but do not launch. Then we delete the .data directory and create an empty directory
sudo systemctl stop sourced
rm -rf $HOME/.source/data/
mkdir $HOME/.source/data/

# download archive
cd $HOME
wget http://116.202.236.115:8000/sourcedata.tar.gz

# unpack the archive
tar -C $HOME/ -zxvf sourcedata.tar.gz --strip-components 1
# !! IMPORTANT POINT. If the validator was created earlier. Need to reset priv_validator_state.json  !!
wget -O $HOME/.source/data/priv_validator_state.json "https://raw.githubusercontent.com/obajay/StateSync-snapshots/main/priv_validator_state.json"
cd && cat .source/data/priv_validator_state.json
{
  "height": "0",
  "round": 0,
  "step": 0
}

# after unpacking, run the node
# don't forget to delete the archive to save space
cd $HOME
rm sourcedata.tar.gz
# start the node
sudo systemctl daemon-reload && \
sudo systemctl enable sourced && \
sudo systemctl restart sourced && \
sudo journalctl -u sourced -f -o cat
``` 

Start node (one command)


```
sudo systemctl daemon-reload && \
sudo systemctl enable sourced && \
sudo systemctl restart sourced && \
sudo journalctl -u sourced -f -o cat
``` 

Create validator


```
sourced tx staking create-validator \
--amount=1000000usource \
--pubkey=$(sourced tendermint show-validator) \
--moniker=<moniker> \
--chain-id=sourcechain-testnet \
--commission-rate="0.10" \
--commission-max-rate="0.20" \
--commission-max-change-rate="0.1" \
--min-self-delegation="1" \
--fees=100usource \
--from=<walletName> \
--identity="" \
--website="" \
--details="" \
-y
``` 

Delete node (one command)


```
sudo systemctl stop sourced && \
sudo systemctl disable sourced && \
rm /etc/systemd/system/sourced.service && \
sudo systemctl daemon-reload && \
cd $HOME && \
rm -rf .source && \
rm -rf source && \
rm -rf $(which sourced)
``` 













