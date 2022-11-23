# Introduction to NULINK
NuLink provides privacy-preserving technology for decentralized applications via APIs. It will enable and facilitate developers, startups, small businesses and enterprises to build their own applications with security and privacy best practices.


[Whitepape](https://www.nulink.org/whitepaper)


![1_k3o_b6XtS5rYZlKo4srr_g.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664237512533/2WBxq7Lv2.png align="left")



[Fill the foarm](https://docs.google.com/forms/d/e/1FAIpQLSep0rgPRcMd2kUhz53GYmBoktu-u-8npU2DakmzGpmpCmYZPw/viewform)


## CHAPTER01: Staking DAPP


Go to  [Nulink website](https://test-staking.nulink.org/) and connect your Metamask Wallet




### Part2- Stake NLKs(test) to the staking pool

Once log in with METAMASK wallet, please check the balance and click the “Staking” button to stake tokens to the staking pool. Make sure claim](https://test-staking.nulink.org/faucet) enough NLKs(test) and BNBs(test) in the staking account as initial funds. Remember bonding an active worker after staking, otherwise no reward will be issued.


> [Click Here](https://test-staking.nulink.org/faucet)

> [Get BNB Tesnet Faucet](https://testnet.binance.org/faucet-smart)

> and Get NLK faucet



![Cuplikan web_27-9-2022_72519_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238370417/5aoQkfPpS.jpeg align="left")


![Cuplikan web_27-9-2022_72659_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238427858/U0NS2haBz.jpeg align="left")


![Cuplikan web_27-9-2022_72720_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238453869/2qMoV9ZM0.jpeg align="left")


![Cuplikan web_27-9-2022_72754_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238489832/25cdGMYvF.jpeg align="left")


![Cuplikan web_27-9-2022_72846_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238535818/0fLHsxXcn.jpeg align="left")



![Cuplikan web_27-9-2022_7298_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238561771/Bo7P6voha.jpeg align="left")


![Cuplikan web_27-9-2022_72948_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238716398/_Cqkr4iyI.jpeg align="left")



![Cuplikan web_27-9-2022_73224_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238758257/V_SJBlvGY.jpeg align="left")


### CHAPTER02: NULINK WORKER

**Part 01: How order and configure your VPS server in 2 minutes (Choose VPS WITH ubuntu 20.04 with Docker)**

Before installing the node you need to rent a VPS server
The advantages of VPS are that they have high availability and are easy to configure.
Of course I’ll explain how to rent a VPS server at a lower cost and especially how to configure it in less than 2 minutes.



### Part 03:Preparation

Update packages:


```
sudo apt update && sudo apt upgrade -y
``` 

![1_61wehw_FXVx8HaZ9M51hpg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238937717/zrpk5GUv6.png align="left")


```
apt install python3-pip -y
``` 

![1_IdULqYCKhxxCBIxX-bptOA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664238958155/Hipo2SGuF.png align="left")


### Part 04: Create a worker account

Download geth:


```
wget https://gethstore.blob.core.windows.net/builds/geth-linux-amd64-1.10.23-d901d853.tar.gz
``` 

![1_epOs8zuEMtptL65RAc_zpQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239004165/do-frYtex.png align="left")

Unzip the downloaded installation package:


```
tar -xvzf geth-linux-amd64-1.10.23-d901d853.tar.gz
``` 


![1_z6kbVVEYP5q7XSH17eqDig.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239054606/_h3U5-5dZ.png align="left")


Enter the unzipped directory:


```
cd geth-linux-amd64-1.10.23-d901d853/
``` 


![1_qcgTm6ZI-dqNG_Ol6aKhYA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239109988/zD7l8t24Y.png align="left")

Use. / get account new — keystore. / keystore to generate Ethereum account and keystore:


```
./geth account new --keystore ./keystore
``` 


![1_r2TI9xZBob9sCIubCRo7yQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239150608/IzVn4cSzX.png align="left")


> Enter a new password and press enter


![1_sEW6JphnYVtComSEHPaEqg.png](Uploading...)

> Confirm your password


![1_pJzy0Py3Md0m_0MvsbK1Aw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239288021/2ldWXubwV.png align="left")



![1_4F9ULJoksCLF4IjmAyIHkg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239306946/T5ePdrtIJ.png align="left")


> Save all information in a notepad


![1_u3LqSi9yO7dUSFT1kNmnEw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239337041/qqBUQ1VKE.png align="left")

From your metamask wallet send NBT to your operator address

operator adress=Public adress of the key (see image above)


![Cuplikan web_27-9-2022_74258_medium.com.jpeg](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239383888/3JmDQ90Yo.jpeg align="left")


### Part 05: NuLink Worker Installation

Go to $home


```
cd $home
``` 

Pull the latest NuLink image:


```
docker pull nulink/nulink:latest
``` 


![1_lEpZg5QerNSANW2vbH-NrA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239483198/Ns2-g6GW7.png align="left")


![1_ULH3LJvl9hZQNPIyp2ZAIg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239505711/sZlWf9Ynh.png align="left")


Create a directory in your host machine for later usage:


```
cd /root
mkdir nulink
``` 


![1_f0DcHkC0cGQici_qrfTu2w.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239572885/J4DiFPdCz.png align="left")

Copy the keystore file of the Worker account to the host directory selected in step 3. The private file generated by NuLink Worker will also be stored in this directory. ****Please ensure that this directory has 777 permissions:


```
cp xxxxxxxxxxxxxxxxxxxxx /root/nulink
``` 
Remplace “xxxxxxxxxxx” by your Path of the “secret key file”


![1_wfmG9N9iyyPX8RDD1Lc3tw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239675421/AEdpKA0ec.png align="left")


```
cp /root/geth-linux-amd64-1.10.23-d901d853/keystore/UTC--2022-09-16T16-46-42.233370072Z--e686bf9b57cec541e0f46f2c0a41bc8836b9b270 /root/nulink
``` 



![1_-kLGoRBYTRfNirjYmxUGLA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239708818/UD4OtTRmQ.png align="left")

Next


```
chmod -R 777 /root/nulink
``` 


![1_Kvbfq7NIqYAmQU3hJs7wDg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239754290/mKueu_mcz.png align="left")

In order to isolate global system dependencies from nulink-specific dependencies, we highly recommend using python-virtualenv to install nulink inside a dedicated virtual environment



```
pip install virtualenv
``` 


![1_rylKoGxBobQLzS3GSzEj3Q.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239797530/qjwZskjoP.png align="left")


Create a Virtual Environment:

Create a virtual environment in a folder somewhere on your machine. This virtual environment is a self-contained directory tree that will contain a python installation for a particular version of Python, and various installed packages needed to run the node



``` 
virtualenv /root/nulink-venv
``` 


![1_lVHapkMh50_3qhrcO8YRsg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239851075/MCdfjWTZa.png align="left")



Activate the newly created virtual environment:


```
source /root/nulink-venv/bin/activate
``` 



![1_Wdb4dOYaPs6XZuYdVDAHiA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239884256/uSTp1M0yu.png align="left")

Download the Nulink package:


```
wget https://filetransfer.nulink.org/release/nulink-0.1.0-py3-none-any.whl
``` 


![1_tb7hxLppun1EQ2jr-rVjSg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239921568/AUSlnUClx.png align="left")


Install the Nulink package:


![1_i-szEiIEmcFvAdOGDvSBmQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239944380/TAaZUyjbd.png align="left")




```
pip install nulink-0.1.0-py3-none-any.whl
``` 


![1_uzLGTPzvvzQK6wAG8mYvyg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239983040/bh0pFIaup.png align="left")



![1_pClv0JGrIhP__zQEMEDdrw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664239992501/RiVYt_E6F.png align="left")



Verify Installation

Before continuing, verify that your Nulink installation and entry points are functional.

Activate your virtual environment, if not activated already:


```
source /root/nulink-venv/bin/activate
``` 


![1_qGPUZ5qbFNWUhAdRnTrUNg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240043948/hMIAaiDiQ.png align="left")


Next, verify nulink is importable. No response is successful, silence is golden:


```
python -c "import nulink"
``` 


![1_09B917UP45OX3PabboVMlA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240091859/dOEmENfFN.png align="left")


> And type this command



```
nulink --help
``` 


![1_OLrK52EFPZly21rh7mzIDw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240123143/4y5lp723U.png align="left")



### PART 06: NuLink Worker Initialization and Running

**Export Node Environment Variables**

These environment variables are used to better simplify the Docker installation process


```
export NULINK_KEYSTORE_PASSWORD=xxxxxxxxxxxx
``` 


Remplace by a new password (You can choose some characters(8 minimum) as the password here. Do not forget it!!!)



```
export NULINK_KEYSTORE_PASSWORD=xxxxxxxxxx
``` 



![1_JWWKiSJR4ElGYEm3y7cGyA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240216140/D_DjKrrQa.png align="left")


**And Type**



```
export NULINK_OPERATOR_ETH_PASSWORD=xxxxxxxxxx
``` 

Password used to unlock the keystore file of Worker account, you should have set it up when you create the Worker account using Geth or other sources. Make sure you enter the same one!!!



```
export NULINK_OPERATOR_ETH_PASSWORD=xxxxxxxxxxx
``` 



![1_3FYI3w6yEe-xoSMig1qXFg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240276859/p0ckFOnNb.png align="left")


### **Run Node via Docker**

Initialize Node Configuration:


```
docker run -it --rm \
-p 9151:9151 \
-v /root/nulink:/code \
-v /root/nulink:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
nulink/nulink nulink ursula init \
--signer keystore:///code/xxxxxxxxxxxxxxxxxxxxxxx \
--eth-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
--network horus \
--payment-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
--payment-network bsc_testnet \
--operator-address yyyyyyyyyyyyyyy \
--max-gas-price 100
``` 

Remplace xxxxxxxxxxx by the your keystore file of the Worker


![1_nMOg2Ahs-PWBxPW45HtpzA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240350920/ctWIaL3Wb.png align="left")


Remplace yyyyyyy by your operator adress


![1_E1mMXPDgi-plf0s2uRuY3A.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240380114/Fa7FE4Xvt.png align="left")


For example:



```
docker run -it --rm \
-p 9151:9151 \
-v /root/nulink:/code \
-v /root/nulink:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
nulink/nulink nulink ursula init \
--signer keystore:///code/UTC--2022-09-16T16-46-42.233370072Z--e686bf9b57cec541e0f46f2c0a41bc8836b9b270 \
--eth-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
--network horus \
--payment-provider https://data-seed-prebsc-2-s2.binance.org:8545/ \
--payment-network bsc_testnet \
--operator-address 0xe686bf9B57CEC541e0F46F2c0a41BC8836B9B270 \
--max-gas-price 100
``` 




![1_W6vDkQCYDgF2k2YPNsHJmg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240430649/JY8r3r2hw.png align="left")

> Press y and Enter


![1_VBu0LdSoDZbWV2yvfWluMg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240460907/PlHGkVRA6.png align="left")


> Take a screenshot of your seedphrase

> Now press y and ENTER



![1_cEs6nkdtmkay6vgfnZqFzg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240595563/kiDZzL5pH.png align="left")


Now with the help of your screenshot fill in your seedphrase, I advise you to write it down on a note and make sure there are no errors before copying it to the terminal



![1_L6z-zIhpEhZkvRQ-ZXqn7g.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240640819/06lSiOM3n.png align="left")


> Now press ENTER and wait a few moment


![1_RGm0poL2jOxA2pUXXPRuSw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240666800/NOux7jb7k.png align="left")


Save all info on a notepad


![1_inlEXOZ0VJm2VDZSmdblGw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240686300/N2FJg8MZz.png align="left")


### Launch the Node


The following command will start the node. Make sure you use the same host directory as the configuration.



```
docker run --restart on-failure -d \
--name ursula \
-p 9151:9151 \
-v /root/nulink:/code \
-v /root/nulink:/home/circleci/.local/share/nulink \
-e NULINK_KEYSTORE_PASSWORD \
-e NULINK_OPERATOR_ETH_PASSWORD \
nulink/nulink nulink ursula run --no-block-until-ready
``` 



![1_8oH40DrqFApjg8BrANPtDg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240734210/mEiT-DvSl.png align="left")



**Check Node URI for Worker Account**

The following command describes how to view worker addresses:


```
docker logs -f ursula
``` 


![1_Y9SwHoPZCrZiOz-STTIRdQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240781386/ltAYVTh-M.png align="left")


> Press CTRL+C to stop the logs

Go home:


```
cd $home
``` 

Open port:


```
apt install ufw -y 
ufw allow ssh 
ufw allow https 
ufw allow http 
ufw allow 9151
ufw enable
``` 


![1_fGpFpFSZ4NFKpxR6o3ybBg.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664240892198/naMAXTvnz.png align="left")


> Now press Enter

> Now Press y and Enter


**You can close your Client linux!**


### **CHAPTER03: Bond an active worker to gain reward**

[Please click here ](https://test-staking.nulink.org/)



![1_advrRururcJljdx5qgjOTw.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241032753/YZBppKt6o.png align="left")



![1_SCiwWK3-yjDZ5dGXSDs6mQ (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241063713/vJBJ0KHmH.png align="left")


![1_KFWMgRiaoUo0qY284y6XnQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241081060/hZD6exVrw.png align="left")
*Your worker adress*



NODE URI=https://Your_adress_VPS:9151

For example:

NODE URI=https://130.185.118.39:9151



![1_ilYG9rnERJDhCBvsHW7nZQ (1).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241207575/6Dw3caGw_.png align="left")


![1_uTH8NRr5-GETBnWSAn1DBQ.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241223515/EKFHdHL5i.png align="left")



![1_cd4uxEQA4-hZIgeu1mWKIA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241240418/ZZOi_BRV_.png align="left")




![1_TUiOScy3-VE14pqJ1PjOAA.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664241355282/umRB2egn6.png align="left")



Congratulations , Your Node is working and done





