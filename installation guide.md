# Netroot AI tarball quick start

The tarball is a 64-bit Linux package. It requires a Linux system with `systemd` and root or `sudo` access.

## Verify the download

Keep the tarball and its `.sha256` file in the same directory, then run:

```bash
sha256sum -c netrootai_1.0.0_local_linux_amd64.tar.gz.sha256
```

## Install and start

```bash
tar -xzf netrootai_1.0.0_local_linux_amd64.tar.gz
cd netrootai-1.0.0
sudo ./install.sh
```

The installer creates the service account and directories, installs Netroot AI under `/opt/netrootai`, and starts the systemd service.

## Verify

```bash
sudo systemctl status netrootai --no-pager
curl -I http://127.0.0.1:3005/login
```

For a local Linux desktop, open `http://127.0.0.1:3005`.

For a remote Linux server, run this command on your computer and leave it open:

```bash
ssh -L 3005:127.0.0.1:3005 USER@SERVER_IP
```

Then open `http://127.0.0.1:3005` on your computer.

## Useful commands

```bash
sudo systemctl restart netrootai
sudo systemctl stop netrootai
sudo journalctl -u netrootai -f
```

Persistent data remains in `/var/lib/netrootai` when the application is upgraded. See the bundled `README.md` and [Netroot AI documentation](https://netrootai.app/docs) for configuration and public HTTPS deployment instructions.
