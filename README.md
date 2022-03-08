# PiggyBank Intro

The AnimalFarm PiggyBank is a deflationary daily ROI platform that allows
you to earn up to 3% daily return on your investment sustainably through a tax system
on transactions. It also allows team building through a referral system, and most
importantly, compound interest. 

## Disclaimer
Signing transactions via this script requires the use of a wallet's private key, meaning you need to handle your private key locally on the computer from which you want to run this script on.
By using this script you agrees to take full responsibility for your private key and wallets security!
I take no responsibility in lost funds, wallets or anything related to using this script.

## Prerequisites
1. A clean and secure computer/nuc/raspberry pi that can run 24/7.
2. Minor programming knowledge

## The PiggyBank

The [PiggyBank](https://theanimal.farm/piggybank/0x361472B5784e83fBF779b015f75ea0722741f304) is a high risk, high reward contract that operates similar to a high yield 
certificate of deposit. You can participate by purchasing PIGS/BUSD LP through these steps: 
1. First you need to buy PIGS via [pancakeswap](https://pancakeswap.finance/swap#/swap?outputCurrency=0x3A4C15F96B3b058ab3Fb5FAf1440Cc19E7AE07ce) 
2. Add LP using BUSD on this [page](https://theanimal.farm/addliquidityPigs). 
3. Now that you have your PIGS/BUSD LP, you need to stake them via the PiggyBank [using this link](https://theanimal.farm/piggybank/0x361472B5784e83fBF779b015f75ea0722741f304).

It is necessary, depending on your deposit size, to compound up to several times a day. The purpose of this code
is to do this automatically for you so you don't have to. 

## Setup

This code was specifically written to be as secure as possible, since signing transactions requires the use of
a wallet's private key. It's imparative you use the encryption outlined in the code to best protect yourself
in the event your computer is ever compomised. 

1. Download [Python](https://www.python.org/downloads/) if you do not already have it. I was not able to get this code
to work on Python 3.9, so I would recommending using Python 3.7 or 3.8. There are a number of resources that will walk 
you through installing Python depending on your operating system.

2. Once Python is installed, the following packages need to be installed.

web3, cryptography, python-dotenv
 ```bash
$ python -m pip install web3
$ python -m pip install cryptography
$ python -m pip install python-dotenv
```

3. In a python terminal, import `cryptography` and encrypt your private key
```py
>>>from cryptography.fernet import Fernet
>>>key = Fernet.generate_key()
```

4. Open `.env.example` and replace the key from above with the example one in the file. Save the file without '.example' at the end. Make sure the file type is saved as 'ENV'. 

5. Go back to the python terminal and do the following:
```py
>>>fernet = Fernet(key)
>>>encMessage = fernet.encrypt('YOURKEYHERE'.encode())
>>>encMessage.decode()
```

6. Take the output value from the last line `encMessage.decode()`, create a file called `key.txt` and save the output in the file. 
7. Save the `key.text` to the root of the project.

8. Open the `bank.py` file and replace the string stored in `wallet_public_addr` with your own public wallet.

## Usage

In a terminal window, navigate to the location where you saved all the files. Run the `bank.py` file.

```bash
$ python bank.py
```

This terminal window will always need to remain open for the script to function. If the terminal window closes, just execute
`python bank.py` again.

If this script helps you, consider supporting me gifiting me some piglets: 
- **wallet:** *0x361472B5784e83fBF779b015f75ea0722741f304*
Or using my buddy referral code:
- [Animal Farm, PiggyBank](https://theanimal.farm/piggybank/0x361472B5784e83fBF779b015f75ea0722741f304)


Other projects to take a look at:
[DRIP Faucet](https://drip.community/faucet?buddy=0x361472B5784e83fBF779b015f75ea0722741f304) - 1% per day - low risk, high reward, no decay
[My DiamondTeam v2](https://mydiamondteam.online/v2/?ref=0x361472b5784e83fbf779b015f75ea0722741f304) - 1.5% per day - low risk, high reward, no decay, 5% reinvest bonus!
[Animal Farm, Garden](https://theanimal.farm/referrals/0x361472B5784e83fBF779b015f75ea0722741f304) - 3% per day, high risk, high reward!
