# ssh-config
SSH Client Configuration Samples



\[ WIP \]



TODO: Demonstrate setting this config on different platforms.



To get started with OpenSSH configuration:

Ensure .ssh exists

```
mkdir -p ~/.ssh
```

If you don't have an exisitng configuration, then start with this one.

Download sample config:

```
Unix:
curl -L http://bit.ly/ssh-config -o ~/.ssh/config

Windows 11:
curl.exe -L http://bit.ly/ssh-config | Out-File config -encoding ascii
```

Edit the file to include your userid





## Server Configuration: Password Authentication by Subnet

The `sshd_config` file shows how to configure an OpenSSH server to:

- **Require SSH key authentication** for all connections by default (`PasswordAuthentication no`)
- **Allow password authentication** only from specific trusted subnets using a `Match Address` block

Edit the `Address` values in the `Match` block to match your own internal network ranges, then copy the file to `/etc/ssh/sshd_config` (or merge relevant sections into your existing server config) and restart the SSH service:

```
sudo systemctl restart sshd
```

---

Useful articles:



https://www.redhat.com/sysadmin/ssh-proxy-bastion-proxyjump

https://www.digitalocean.com/community/tutorials/how-to-configure-custom-connection-options-for-your-ssh-client

