# Ksize
Simple script to monitor disk size, files or directories and notifies you by email.

- **Dependencies**
```
# apt install curl -y
# dnf install curl -y
```
- **Usage**
```
# chmod +x Ksize
# ./Ksize
```
- **Email settings**

Create file, `~/.kmailrc`:
```
SMTP_URL="smtp.gmail.com"
SMTP_PORT="465"
MAIL_FROM="your-email"
MAIL_PASS="email-password"
REALNAME="Your Name"
```
- **Monitor disk space and send by email after the limit is reached**

Discover the partition to be monitored:
```
# df
# fdisk -l
# lsblk
```
Set maximum size for notification after limit reached:

Type: Kilobyte(K), Megabytes(M), Gigabyte(G) or Porcentage (1-100%)

Ex: `--max-device 10G or 50%`

Add to cron:
```
# m h  dom mon dow   command
  x x   x   x   x     Ksize --device <device> --max-device <size> --mail-rcpt <email-recept>
```
