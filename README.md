**Join Us**: [![Slack](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)](https://harrythedevopsguy.slack.com)  [![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/TheDevOpsProfessionals)  [![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://chat.whatsapp.com/Go0FgwQs9GtKp6js2l6RTG)

# gCrypt
gCrypt is a utility to encrypt and decrypt the sensitive data stored in git repository. it's wrapper on top of git-crypt tool. it allow you to configure git-crypt, manage users, trust level, encrypt and decrypt files easily.


# gCrypt Version
 **Version**        : v0.1.2 <br>
 **Release Date**   : 02-Sep-23 <br>


## Installation 
```
sudo apt-get install git-crypt
sudo curl -sL "https://github.com/HarryTheDevOpsGuy/gcrypt/raw/master/$(uname -p)/gcrypt" -o /usr/bin/gcrypt
chmod +x /usr/bin/gcrypt
gcrypt help 
```

## Getting Started with your git Repository. 
```
git clone https://github.com/HarryTheDevOpsGuy/gCrypt.git
cd gCrypt
git config user.email "YourEmail@domain.com"
git config user.name "YourName"

gcrypt init
gcrypt trust gitusersemail@domain.com

```
 