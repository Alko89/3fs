# VM Setup

## Update

Update system packages `apt update & apt upgrade` and upgrade to latest release with `do-release-upgrade`.

## Set up firewall

Enable Uncomplicated Firewall with `ufw enable`.

Allow access from your IP to SSH `ufw allow proto tcp from YOUR_IP to any port 22`.

Allow access from your IP to DNS `ufw allow from YOUR_IP to any port 52`

Allow access from 89.212.81.128/27 `ufw allow from 89.212.81.128/27`.

Allow access to tcp/43210 `ufw allow 43210/tcp`

Check the configuration `ufw status`

## Set up SSH

Edit `/etc/ssh/sshd_config` file to enable SSH to linsten on ports 22 and 43210:

    Port 22
    Port 43210

Save the file and restart the daemon with `systemctl restart sshd.service`.

## DNS Setup

Install unbound `apt install unbound`

Create a new file in `/etc/unbound/unbound.conf.d` and insert the following lines:

    server:
        interface: 0.0.0.0
        interface: ::0

        access-control: 193.77.147.172 allow

        local-zone: "test.3fs.si" static
        #local-data: "test.3fs.si A 82.196.1.116"
        local-data: "www.test.3fs.si A 82.196.1.116"
