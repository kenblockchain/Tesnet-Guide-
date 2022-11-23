To create a wallet you need go to the [explorer](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Feu-1.gemini-2a.subspace.network%2Fws#/accounts) and follow the examples in the screenshots.
**Don’t forget save mnemonics!**


![11 (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664256191129/AueB9p4c5.png align="left")


![12 (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664256225958/5tq7P3GIN.png align="left")



![13.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664256246903/PcQHkVP5Y.png align="left")



![14.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664256278620/CJmgptleb.png align="left")



![15.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664256300529/dg-mi9kp4.png align="left")



![16.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664256328992/3paGUPb3-.png align="left")







### Official Instructions:
[docs.subspace.network](https://docs.subspace.network/)

[Telemetry](https://telemetry.subspace.network/#list/0x43d10ffd50990380ffe6c9392145431d630ae67e89dbc9c014cac2a417759101)






### Required ports

Currently, TCP port 30333 needs to be exposed for node to work properly. If you have a server with no firewall, there is nothing to be done, but otherwise make sure to open TCP port 30333 for incoming connections.



```
tmux new -s node
``` 


# Installing

```
wget https://github.com/subspace/subspace/releases/download/gemini-2a-2022-sep-10/subspace-node-ubuntu-x86_64-gemini-2a-2022-sep-10
``` 



```
sudo chmod +x subspace-node-ubuntu-x86_64-gemini-2a-2022-sep-10
``` 



```
./subspace-node-ubuntu-x86_64-gemini-2a-2022-sep-10 \
  --chain gemini-2a \
  --execution wasm \
  --state-pruning archive \
  --validator \
  --name isienworkermu
``` 

**CTRL +B D**



```
tmux new -s farm
``` 


```
wget https://github.com/subspace/subspace/releases/download/gemini-2a-2022-sep-10/subspace-farmer-ubuntu-x86_64-gemini-2a-2022-sep-10
``` 


```
sudo chmod +x subspace-farmer-ubuntu-x86_64-gemini-2a-2022-sep-10
``` 



```
./subspace-farmer-ubuntu-x86_64-gemini-2a-2022-sep-10 farm \
--reward-address isienwalletmu \
--plot-size 100G
``` 

CTRL + B D


## Additional

Check node logs:


```

tmux ls
``` 


```
tmux attach -t node
``` 


Check cek plotting:


```

tmux attach -t farm
``` 







