
# HBSender
[![License](https://img.shields.io/badge/license-MIT-red.svg)](https://github.com/KeepWannabe/HBSender/blob/main/LICENSE.md)   [![Version](https://img.shields.io/badge/Release-1.0-red.svg?maxAge=259200)]()  [![Build](https://img.shields.io/badge/Supported_OS-Linux-yellow.svg)]()  [![Build](https://img.shields.io/badge/Supported_WSL-Windows-blue.svg)]() [![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/KeepWannabe/HBSender/issues)
### Plivo and Nexmo Bulk Sending SMS Tools
<img width="935" alt="hbsender" src="https://raw.githubusercontent.com/KeepWannabe/HBSender/main/top-header.jpg">


### But it's shit! And your implementation sucks!
- Yes, you're probably correct. Feel free to "Not use it" and there is a pull button to "Make it better". 

## Installation
*HBSender* is currently extended with the following tools. Instructions on how to install & use the application are linked below.

### To Download HBSender From Github
```bash
# Clone this repository
git clone --recursive https://github.com/KeepWannabe/HBSender.git
```

## Dependencies
*HBsender* requires [jq](https://stedolan.github.io/jq/download/) to run and parse. Information on how to download and install jq can be accessed [here](https://stedolan.github.io/jq/download/)

```bash
# Linux
apt-get update
apt-get install jq curl dos2unix
sed -i 's/\r$//' HBSender module/*.send

```
### Post Installation
API Key is needed before querying on third-party sites, such as ```Plivo, Nexmo and Twillio```.
- The API key setting can be done in **Account** folder.
- **The plivo and twillio are sending with random number (based on your owned numbers at plivo/twillio) and shuffling**
```json
## NEXMO
{"apikey":"YOUR_APIKEY","apisecret":"YOUR_SECRETKEY","fromnumber":1234567890}

## PLIVO
{"authid":"YOUR_APIKEY","secretid":"YOUR_SECRETKEY"}

## TWILLIO
{"accountsid":"ACXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX","token":"YOUR_TOKEN"}
```
And you can setting the messages Letter at **module/nexmo.send**, **module/plivo.send** and **module/twillio.send**
```bash
## NEXMO
## LETTER ##
## $(((RND=RANDOM<<15|RANDOM)) ; echo ${RND: -6}) >> ITS A 6 DIGIT RANDOM NUMBER
## $(date +"%A, %d %B %Y") >> SHOWING DATE e.g. Wednesday, 03 March 2021
nLetter="<#> Company: Your OTP code is ($(((RND=RANDOM<<15|RANDOM)) ; echo ${RND: -6})). This code will expire in 10 minutes - $(date +"%A, %d %B %Y")."

## PLIVO
## LETTER ##
## $(((RND=RANDOM<<15|RANDOM)) ; echo ${RND: -6}) >> ITS A 6 DIGIT RANDOM NUMBER
## $(date +"%A, %d %B %Y") >> SHOWING DATE e.g. Wednesday, 03 March 2021
pLetter="<#> Company: Your OTP code is ($(((RND=RANDOM<<15|RANDOM)) ; echo ${RND: -6})). This code will expire in 10 minutes - $(date +"%A, %d %B %Y")."

##TWILLIO##
## LETTER ##
## $(((RND=RANDOM<<15|RANDOM)) ; echo ${RND: -6}) >> ITS A 6 DIGIT RANDOM NUMBER
## $(date +"%A, %d %B %Y") >> SHOWING DATE e.g. Wednesday, 03 March 2021
tLetter="<#> Company: Your OTP code is ($(((RND=RANDOM<<15|RANDOM)) ; echo ${RND: -6})). This code will expire in 10 minutes - $(date +"%A, %d %B %Y")."
```
## Usage
```text
➜  HypeBrotherSender ➜ bash HBSender
      __  ______ _____                __
     / / / / __ ) ___/___  ____  ____/ /__  _____
    / /_/ / __  \__ \/ _ \/ __ \/ __  / _ \/ ___/
   / __  / /_/ /__/ /  __/ / / / /_/ /  __/ /    
  /_/ /_/_____/____/\___/_/ /_/\__,_/\___/_/     

  [HYPEBROTHER SENDER 2K21 - LICENSE : FREE]

  ▸ [1] NEXMO SENDER
  ▸ [2] PLIVO SENDER
  ▸ [3] TWILLIO SENDER

  ▸ OPTIONS : 
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
