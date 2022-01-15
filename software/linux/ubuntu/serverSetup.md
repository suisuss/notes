### Ubuntu Server Setup (recommendation)

#### Instructions

**On local computer:**

- SSH into your server 
    - `ssh root@[IP ADDRESS]`

**On server:**

- Update and Upgrade
    - `apt update && apt upgrade`

- Set hostname
    - `hostnamectl set-hostname [HOST NAME]`
    - Check hostname
        - `hostname`
    - `nano /etc/hosts`
        - Put `[IP ADDRESS] [HOST NAME]` under `127.0.0.1 localhost`

- Add a new user
    - `adduser [USERNAME]`
- Add new user to sudo group
    - `adduser [USERNAME] sudo`

- Exit and ssh into new user account
    - `exit`
    - `ssh [USER]@[IP ADDRESS]`
- `mkdir .ssh && mkdir .ssh/authorized_keys`
- `exit`


**On local computer:**

- Create SSH key
- Copy SSH key to server 
    - `scp ~/.ssh/id_rsa.pub [USER]@[IP ADDRESS]:~/.ssh/authorized_keys`


**On server:**

- Add appropriate permissions to `.ssh` and files contained 
    - `sudo chmod 700 ~/.ssh/`
    - `sudo chmod 600 ~/.ssh/*`

- Test SSH
    - `exit`
    - **On local computer:**
        - `ssh [USER]@[IP ADDRESS]`

**On server:**

- Make SSH more secure by editing the config
    - `sudo nano /etc/ssh/sshd_config`
        - Change PermitRootLogin from yes to no
        - Uncomment out PasswordAuthentication and change from yes to no (optional)
    - Restart ssh daemon program
        - `sudo systemctl restart sshd`

- Install uncomplicated firewall
    `sudo apt install ufw`

- Configure and enable UFW
    - Allow outgoing data
        - `sudo ufw default allow outgoin`
    - Deny incoming data
        - `sudo ufw default deny incoming`
    - Allow SSH **!!!IMPORTANT!!!**
        - `sudo ufw allow ssh`
    - Enable UFW
        - `sudo ufw enable`
        - Will disrupt SSH connection...
            **On local computer:**
                - `ssh [USER]@[IP ADDRESS]`
    **On server:**
        - Check status and make sure UFW is running
            - `sudo ufw status`
            
- `exit`

COMPLETE
