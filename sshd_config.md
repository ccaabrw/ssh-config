# Server Configuration: Password Authentication by Subnet

The `sshd_config` file shows how to configure an OpenSSH server to:

- **Require SSH key authentication** for all connections by default (`PasswordAuthentication no`)
- **Allow password authentication** only from specific trusted subnets using a `Match Address` block

Edit the `Address` values in the `Match` block to match your own internal network ranges, then copy the file to `/etc/ssh/sshd_config` (or merge relevant sections into your existing server config) and restart the SSH service:

```
sudo systemctl restart sshd
```

---

The ssh change may not work if you have "UsePAM yes" in sshd_config.
To fix you need to also add "ChallengeResponseAuthentication no".
