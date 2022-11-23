1. Installing
If you don’t already have an Alchemy account, follow step 2. Endpoints, then go to the next step.
Replace YOUR_ALCHEMY_HTTP_ADDRESS with your alchemy address.


```
ALCHEMY=YOUR_ALCHEMY_HTTP_ADDRESS
echo 'export ALCHEMY='$ALCHEMY >> $HOME/.bash_profile
``` 

Example, do not copy!


```
ALCHEMY=https://eth-goerli.alchemyapi.io/v2/Ey8Guru7zpg3EfUcLm8iR4FTxPAvqMS
echo 'export ALCHEMY='$ALCHEMY >> $HOME/.bash_profile
``` 

![Screenshot_4.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662876028081/QtVRbrAM5.png align="left")

Use our script for a quick installation:


```
wget -O starknet.sh https://api.nodes.guru/starknet.sh && chmod +x starknet.sh && ./starknet.sh
``` 

2. Endpoints
To run starknet we will use the nodes provided by the Alchemy service, so register at alchemy.com and create endpoints in your personal account.



![11.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662876147389/nRjcnTLjZ.png align="left")


![1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662876156748/7utjZASrS.png align="left")


![2.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662876167950/J9VC81EhN.png align="left")


![3.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662876178609/6qX4lMEwb.png align="left")


![12.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662876210690/Sf-IjYhMC.png align="left")

Copy the address and go to step 1. Installing


Additional
Check logs:


```
journalctl -u starknetd -f
``` 

Restart node:


```
systemctl restart starknetd
``` 

Delete node:

```
systemctl stop starknetd
systemctl disable starknetd
rm -rf ~/pathfinder/
rm -rf /etc/systemd/system/starknetd.service
rm -rf /usr/local/bin/pathfinder
``` 

update node :

```
#!/bin/bash

echo "-----------------------------------------------------------------------------"
curl -s https://raw.githubusercontent.com/razumv/helpers/main/doubletop.sh | bash
echo "-----------------------------------------------------------------------------"
echo "Начинаем обновление репрозитория "
echo "-----------------------------------------------------------------------------"
cd ~/pathfinder/py
git fetch &>/dev/null
git checkout v0.3.0-alpha &>/dev/null
echo "Репозиторий успешно обновлен, начинаем билд"
echo "-----------------------------------------------------------------------------"
python3 -m venv .venv &>/dev/null
source .venv/bin/activate &>/dev/null
PIP_REQUIRE_VIRTUALENV=true pip install --upgrade pip &>/dev/null
PIP_REQUIRE_VIRTUALENV=true pip install -r requirements-dev.txt &>/dev/null
rustup update
cargo build --release --bin pathfinder &>/dev/null
sleep 2
source $HOME/.bash_profile &>/dev/null
echo "Билд завершен успешно"
echo "-----------------------------------------------------------------------------"
systemctl restart starknet
echo "Нода обновлена и запущена"
echo "-----------------------------------------------------------------------------"
``` 




