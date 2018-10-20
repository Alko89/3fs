# VM Setup

## Update

Update system packages `apt update & apt upgrade` and upgrade to latest release with `do-release-upgrade`.

## Set up firewall

Enable Uncomplicated Firewall with `ufw enable`.

Allow access from your IP to SSH `ufw allow proto tcp from YOUR_IP to any port 22`.

Allow access from your IP to DNS `ufw allow from YOUR_IP to any port 52`

Allow access from 89.212.81.128/27 `ufw allow from 89.212.81.128/27`.

Allow access to tcp/43210 `ufw allow 43210/tcp`

Edit `/etc/ssh/sshd_config` file to enable SSH to linsten on ports 22 and 43210:

    Port 22
    Port 43210

Save the file and restart the daemon with `systemctl restart sshd.service`.

    ufw status
