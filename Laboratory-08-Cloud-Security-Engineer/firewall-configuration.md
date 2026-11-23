# Firewall Configuration

## Allow SSH
```bash
sudo ufw allow ssh
```

## Default Deny Policy
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

## Allow Port 8080 (Web Application)
```bash
sudo ufw allow 8080/tcp
```

## What happens if `ufw enable` runs before `ufw allow ssh`?
If `sudo ufw enable` is run before SSH is allowed, the firewall immediately blocks all incoming traffic, including the SSH session that is currently open. The administrator would be locked out of the server and could only get back in through the cloud provider's emergency console.
