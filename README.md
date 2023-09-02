**Join Us**: [![Slack](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)](https://harrythedevopsguy.slack.com)  [![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/TheDevOpsProfessionals)  [![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)](https://chat.whatsapp.com/Go0FgwQs9GtKp6js2l6RTG)

# gCrypt
gCrypt is a utility to encrypt and decrypt the sensitive data stored in git repository. it's wrapper on top of git-crypt tool. it allow you to configure git-crypt, manage users, trust level, encrypt and decrypt files easily.

## Helpful Links to know more about git-crypt
 - [Git-Crypt docs ](https://glennklockwood.com/sysadmin-howtos/git-crypt.html)


# gCrypt Version
 **Version**        : v0.1.3 <br>
 **Release Date**   : 02-Sep-23 <br>


## Installation 
```
sudo apt-get install git-crypt
sudo curl -sL "https://github.com/HarryTheDevOpsGuy/gcrypt/raw/master/$(uname -p)/gcrypt" -o /usr/bin/gcrypt
chmod +x /usr/bin/gcrypt
```

## What is Git-Crypt ? 

 `git-crypt` is an open-source tool that allows you to encrypt and decrypt specific files or directories within a Git repository. It provides a way to protect sensitive data, such as configuration files or credentials, while still keeping them under version control. `git-crypt` works by encrypting the files with GPG (GNU Privacy Guard) and then storing them in the Git repository.

Here's how to install and configure `git-crypt` for a Git repository:

**Installation:**

1. **Install GPG:**
   Before using `git-crypt`, you need to have GPG installed on your system. You can download and install GPG from the official GnuPG website (https://gnupg.org/download/).

2. **Install `git-crypt`:**
   You can install `git-crypt` using a package manager or by building it from source. Here's how to install it using common package managers:

   - **Debian/Ubuntu:**
     ```bash
     sudo apt-get install git-crypt
     ```

   - **Fedora/RHEL:**
     ```bash
     sudo dnf install git-crypt
     ```

   - **macOS (Homebrew):**
     ```bash
     brew install git-crypt
     ```

   - **Windows (Cygwin):**
     You can use Cygwin to install `git-crypt` on Windows. Follow the Cygwin installation instructions, and then install `git-crypt` within the Cygwin environment using its package manager.

Once you have installed `git-crypt`, `gnupg` then you have install `gcrypt` by following commands. 

```bash 
sudo curl -sL "https://github.com/HarryTheDevOpsGuy/gcrypt/raw/master/$(uname -p)/gcrypt" -o /usr/bin/gcrypt
chmod +x /usr/bin/gcrypt
```


**Configuration:**

1. **Initialize `gcrypt` for the Repository:**
   In your Git repository, run the following command to initialize `gcrypt`:

   ```bash
   gcrypt init
   ```

   This creates a `.gitattributes` file and a `.git-crypt` directory in the repository.

2. **Edit `.gitattributes`:**
   Open the `.gitattributes` file that was created in your repository. You can specify which files or directories should be encrypted by adding patterns to the file. For example:

   ```plaintext
   sensitive-file.txt filter=git-crypt diff=git-crypt
   sensitive-directory/** filter=git-crypt diff=git-crypt
   ```

   This example specifies that the `sensitive-file.txt` and the contents of the `sensitive-directory/` should be encrypted.

3. **Add GPG Keys:**
   To encrypt and decrypt files, you need to have GPG keys configured. Ensure that you have a GPG key pair (public and private keys) set up on your system.

   ```bash 
   gpg --gen-key  # To generate new gpg private and public key.
   gpg --list-keys  # To list all gpg keys in your system
   ```

4. **Share the Public Key:**
   If you are collaborating with others, you need to share your GPG public key with them. They will use your public key to encrypt files that you can decrypt with your private key.

    If you are using any centralized gpg key server you have to set variable `KEY_SERVER`.
   ```bash
     export KEY_SERVER="https://keyserver.ubuntu.com"
     gcrypt trust gitusersemail@domain.com
   ```

**Usage:**

- After configuring `gcrypt`, simply commit the changes to the `.gitattributes` file and any files or directories you specified to be encrypted.

- When collaborators clone the repository, they need to have access to your GPG public key to decrypt the encrypted files. They can then use their own GPG keys to encrypt files for you.

- Remember to commit changes to the `.git-crypt/` directory and `.gitattributes` file whenever you make changes to the encryption configuration.

With `git-crypt`, you can selectively encrypt and decrypt sensitive data in your Git repository, providing an added layer of security for your version-controlled files.

