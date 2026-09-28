# SSH Tutorial for Back-End Access

## SSH Key Generation

Step-by-step instructions to generate SSH keys for secure access.

1. **Open the Terminal/Command Prompt:**

   - **Windows**: Press `Windows + R`, type `cmd`, and hit **Enter**.
   - **macOS/Linux**: Open the Terminal from the applications menu or use `Ctrl + Alt + T`.

2. **Run the `ssh-keygen` Command:**

   Use the following command to generate an RSA key of 4096 bits with an email comment:

   ```bash
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com" 
   ```

### Understanding Public and Private Keys

When you generate an SSH key pair, two files are created:

1. **Private Key** (`id_rsa`): This is your **private** key. It is stored securely on your local machine, typically in the `~/.ssh` directory. This key should **never be shared** with anyone. It acts as the secure authentication mechanism that proves your identity when connecting to servers or services using SSH. Think of it as your personal digital signature.

2. **Public Key** (`id_rsa.pub`): This is your **public** key. It can be freely shared with anyone or any service that you need to authenticate with (e.g., GitHub, GitLab, a remote server). When you provide a service with your public key, that service will use it to encrypt data that only your private key can decrypt, ensuring a secure connection.

## Connecting via SSH
How to connect to remote servers via SSH for deployment or maintenance.
Once you have generated your SSH key pair, someone with access to the server needs to install your **public key** to allow you to authenticate. Here's how to do it:

### Steps for Setting Up the Public Key on the Server

1. **Provide Your Public Key**:  
   Share your **public key** (`id_rsa.pub`) with the person who has access to the server. Do **not** share your private key.

#### Creating the user on the server :

2. **Access the Server**:  
   The person who has access to the server should log in using SSH:
   
   ```bash
   ssh username@server_ip_address
   ```
3. **Create Sudo Privileges User**
    Use the following command to create a new user. Replace username with the desired username :
    ```bash
    adduser username
    usermod -aG sudo username
    ```

4. **Set-up the SSH key on the server**
    
    Go to the User's Home Directory:
    Navigate to the home directory of the user for whom SSH access is being set up:
        `cd /home/username`

    Create the .ssh Directory (if not already present):
    ```bash
    mkdir -p .ssh
    chmod 700 .ssh
    ```
    Copy the public key directly from a file using scp or another secure method :
    ```bash
    scp /path/to/id_rsa.pub username@server_ip_address:~/.ssh/temp_key.pub
    ssh username@server_ip_address
    cat ~/temp_key.pub >> ~/.ssh/authorized_keys
    rm ~/temp_key.pub
    ```
    Set the Correct Permissions:
    ```bash
    chmod 600 ~/.ssh/authorized_keys
    ```
### Try the connection

#### Connection by CMD :
`ssh username@server_ip_address`

#### SSH Connection via Remote - SSH
##### Step 1: Install the Remote - SSH Extension
Open Visual Studio Code.
Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or pressing `Ctrl + Shift + X`.
Search for Remote - SSH and click Install.

##### Step 2: Configure SSH in Visual Studio Code

1. **Open the config :**

`Ctrl + alt + o`

Click on "Connect to Host"

Select "Configure SSH Hosts..."

Add the server :

> **Note:** Replace `YOUR_SERVER_IP` and `YOUR_USERNAME` with the actual server credentials. Contact the project lead (or check the team's password manager / Bitwarden / 1Password) to obtain the current server IP and your assigned username.

```bash
Host Digital-Ocean
  HostName YOUR_SERVER_IP
  User YOUR_USERNAME
  IdentityFile "C:\Path\of\your\private\key"
```

`IdentityFile` is not necessary, this applies if your private key is stored in a location other than the usual one and you wish to localize it.

2.  **Connect to the Server**

`Ctrl + alt + o`

Select : "Digital-Ocean"

Enter your passphrase.

Done !

## Security Best Practices
Recommendations for securing SSH connections, such as using public-key authentication.

To ensure that your SSH connections remain secure, follow these best practices:

1. **Use Public-Key Authentication**:  
   Avoid password-based login and use SSH key pairs for authentication. This reduces the risk of brute-force attacks.

2. **Protect Your Private Key with a Passphrase**:  
   Always set a strong passphrase to encrypt your private key. This adds an extra layer of security in case your private key is exposed.

3. **Keep Your Private Key Secure**:  
   Never share your private key. Store it securely with appropriate file permissions (`chmod 600`) and generate a new key if compromised.
