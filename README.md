# Masternode Setup - Step by step guide

Requirements: 	
1.) VPS for example on vultr or AWS on Amazon Services or Digital Ocean (on digitalocean you can get bonus 50$ for 30 days)
2.) for 1 Masternode you need a wallet with 50001 APH Coins

Feel free to use our reflinks to signup: 
vultr:  <a href="https://www.vultr.com/?ref=7811287"><img src="https://www.vultr.com/media/banner_2.png" width="468" height="60"></a>

Feel free to use our reflinks to signup: 
DigitalOcean ( to get the Bonus of 50$ ) you can use this link: https://m.do.co/c/620c3ac29a40


setup start with security on vps in putty (firewall)

```bash
sudo ufw allow 22
```
```bash
sudo ufw allow 80
```
```bash
sudo ufw allow 5662
```
```bash
sudo ufw enable
```
You will be prompted with "Yes or no". type y and press enter

```bash
sudo 
```

start install the requirements on VPS:
```bash
sudo apt-get upgrade -y
```

```bash
sudo wget https://github.com/1apdeveloper/mn-setup-v20/raw/master/install.sh
```

```bash
sudo chmod +x install.sh
```
```bash
./install.sh
```
Please no working on any other things on the computer or it makes a mistake. 
This is an automatically installation 



# it starts automatically the vps server 


if everything is fine: you get an output: 

```bash
config file= .apholding/.apholding.conf
IP:PORT = YOUR IP: 5662
MASTERNODE PRIVATEKEY is: YOUR-NEW_PRIVATE_KEY 
```
copy the privatekey in a textfile

 
## start in the wallet 

<table>
<tr><td>example</td></tr>
<tr><td>6ehsxiEwmLzeT4EaCuX9v2euuYQNGSjjBKxRUTrmbdXG</td></tr>
</table>

```bash
getaccountaddress "MN1"  
```

<table>
<tr><td>example</td></tr>
<tr><td>HRbcQmmJUUPJ9RKZfa1ariykE1z774156P</td></tr>
</table>

send exact 50000 Coins to the address (confirmation need: 15) 


# Installation: for Security use SSH on your vps!!




### back in wallet
 
go to debug console

```bash
masternode outputs
```
<table>
<tr><td>example</td></tr>
 <tr><td>{</td></tr>
<tr><td>    "txhash": "c8ab8aa43d50cae6bf2b89b09f124bd83beaec00537884be8ec6585d1922", </td></tr>
<tr><td>     "outputidx": 1 {</td></tr>
<tr><td>   }</td></tr>
</table>


# Configure masternode.conf file (look at the example in file), reopen wallet and start masternode in debug console

<table>
<tr><td>example for masternode in masternode.conf file </td></tr>
<tr><td>mn1 IP_OF_THE_SERVER:5662 MASTERNODE_GENKEY TX_HASH TX_OUTPUTS</td></tr>
<tr><td>mn1 123.12.15.14:5662 THE-PRIVATE-KEY-FROM-VPS c8ab8aa43d50cae6bf2b89b09f124bd83beaec00537884be8bae6585d1922 1</td></tr>
</table>

save file, reopen wallet and start in debug console !

```bash
startmasternode alias false MN1
```
