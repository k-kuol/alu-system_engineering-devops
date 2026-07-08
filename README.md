# alu-system_engineering-devops

## SSH

This project covers the basics of servers and the SSH protocol: what a server is,
where servers live, what SSH is, and how to generate and use an RSA key pair to
connect to a remote host without a password.

### Directory: `ssh`

| File | Description |
| --- | --- |
| [0-use_a_private_key](ssh/0-use_a_private_key) | Connects to the server as `ubuntu` using the private key `~/.ssh/school`. |
| [1-create_ssh_key_pair](ssh/1-create_ssh_key_pair) | Generates a 4096-bit RSA key pair named `school`, protected by the passphrase `betty`. |
| [2-ssh_config](ssh/2-ssh_config) | SSH client configuration that uses the private key `~/.ssh/school` and disables password authentication. |
