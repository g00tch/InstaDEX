![Example-Logo](https://i.imgur.com/zpaKz0S.png)

# InstaDEX Masternode Setup Guide (Ubuntu 16.04)
This guide will assist you in setting up an InstaDEX Masternode on a Linux Server running Ubuntu 16.04. (Use at your own risk)

If you require further assistance contact the support team @ [Discord](https://discord.gg/VXchtBt)

## Requirements
1) **10,000 InstaDEX coins.**
2) **A Vultr VPS running Linux Ubuntu 16.04.**
3) **A Windows local wallet.**
4) **An SSH client such as [Bitvise](https://dl.bitvise.com/BvSshClient-Inst.exe)**
***
## Contents
* **Section A**: Creating the VPS within [Vultr](https://www.vultr.com/?ref=7475078).
* **Section B**: Downloading and installing Bitvise.
* **Section C**: Connecting to the VPS and installing the MN script via Bitvise.
* **Section D**: Preparing the local wallet.
* **Section E**: Connecting & Starting the masternode.
***

## Section A: Creating the VPS within [Vultr](https://www.vultr.com/?ref=7475078) 
***Step 1***
* Register at [Vultr](https://www.vultr.com/?ref=7475078)
***
***Step 2***
* After you have added funds to your account go [here](https://my.vultr.com/deploy/) to create your Server
***

***Step 3*** 
* Choose a server location (preferably somewhere close to you)
![Example-Location](https://i.imgur.com/ozi7Bkr.png)
***

***Step 4***
* Choose a server type: Ubuntu 16.04
![Example-OS](https://i.imgur.com/aSMqHUK.png)
***

***Step 5***
* Choose a server size: $5/mo will be fine 
![Example-OS](https://i.imgur.com/UoGoHcM.png)
***

***Step 6*** 
* Set a Server Hostname & Label (name it whatever you want)
![Example-hostname](https://i.imgur.com/nuh6Roz.png)
***

***Step 7***
* Click "Deploy now"

![Example-Deploy](https://i.imgur.com/4qpYuH0.png)
***


## Section B: Downloading and installing BitVise. 

***Step 1***
* Download Bitvise [here](https://dl.bitvise.com/BvSshClient-Inst.exe)
***

***Step 2***
* Select the correct installer depending upon your operating system. Then follow the install instructions. 

![Example-PuttyInstaller](https://i.imgur.com/yF3694G.png)
***


## Section C: Connecting to the VPS & Installing the MN script via Bitvise.

***Step 1***
* Copy your VPS IP (you can find this by going to the server tab within Vultr and clicking on your server. 
![Example-Vultr](https://i.imgur.com/z41MiwY.png)
***

***Step 2***
* Open the bitvise application and fill in the "Hostname" box with the IP of your VPS.
![Example-PuttyInstaller](https://i.imgur.com/vkN1alC.png)
***

***Step 3***
* Copy the root password from the VULTR server page.
![Example-RootPass](https://i.imgur.com/JnXQXav.png)
***

***Step 4***
* Type "root" as the login/username.
![Example-Root](https://i.imgur.com/11GMkvA.png)
***

***Step 5*** 
* Paste the password into the Bitvise terminal by right clicking (it will not show the password so just press enter)
![Example-RootPassEnter](https://i.imgur.com/zVhOAKu.png)
***

***Step 6*** 
* Once you have clicked open it will open a security alert (click yes).  
***


***Step 7***
* Paste the code below into the Bitvise terminal, and then press enter

`wget -q https://github.com/g00tch/InstaDEX/raw/master/instadex_install.sh && bash instadex_install.sh`

![Example-Bash](https://i.imgur.com/P7dogoR.png)

***

***Step 8***
* Sit back and wait for the install (this will take between 1-10 minutes)
***

***Step 9***
* When prompted to enter your Masternode GEN key, just press enter

![Example-installing](https://i.imgur.com/mgQz90H.png)
***

***Step 10***
* You will now see all of the relavant information for your server.
* Keep this terminal open as we will need the info for the wallet setup.
![Example-installing](https://i.imgur.com/tidLdvI.png)
***

## Section D: Preparing the Local wallet

***Step 1***
* Download and install the Anodos wallet [here](https://github.com/InstaDex-Coin/InstaDEX/releases)
***

***Step 2***
* Create a text document to temporarily store information that you will need.
***

***Step 3***
* Create a new receiving address and send EXACTLY 10,000 InstaDEX to that address from within your wallet.
![Example-address](https://i.imgur.com/dcC5ZRu.png)
![Example-address2](https://i.imgur.com/2AnJX16.png)
![Example-send](https://i.imgur.com/2AnJX16.png)
***

***step 4***
* After your transaction confirms, go to the debug console within the wallet 

![Example-console](https://i.imgur.com/HRsJVLO.png)
***

***Step 5***
* Type the command below and press enter 

`masternode outputs` 

![Example-outputs](https://i.imgur.com/8VLrqiv.png)
***

***Step 6***
* Copy the long key (this is your transaction ID) and the 1 or 2 at the end (this is your output index)
* Paste these into the text document you created earlier as you will need them in the next step.
***

# Section E: Connecting & Starting the masternode 

***Step 1***
* Go to the tools tab within the wallet and click open "masternode configuration file" 
![Example-create](https://i.imgur.com/pauxD0x.png)
***

***Step 2***

* Fill in the form. 
* For `Alias` type something like "MN01" **don't use spaces**
* The `Address` is the IP and port of your server (this will be in the Bitvise terminal that you still have open).
* The `PrivKey` is your masternode GEN key (This is also in the Bitvise terminal that you have open).
* The `TxHash` is the transaction ID/long key that you copied to the text file.
* The `Output Index` is the 0 or 1 that you copied to your text file.
![Example-create](https://i.imgur.com/rfEzyQV.png)

Click "File Save"
***

***Step 3***
* Close out of the wallet and reopen Wallet
*Click on the Masternodes tab
* Click on the Masternode you want to start, and click Start Alias
***

***step 4***
* Check the status of your masternode within the VPS by using the command below:

`instadex-cli masternode status`


`instadex-cli getinfo`

*You should see ***Masternode Successfully Started***

If you do, congratulations! You have now setup a masternode. If you do not, please contact support and they will assist you.

Donations are not required, but greatly appreciated :)

InstaDEX Wallet: iAXJhWRiF5zh2jmszWA6SmbBRFoCRLkqjf

BTC Wallet: 1NcGHPgUQ6mkB1h8HLj9HceuL8uJEKnJ2a

