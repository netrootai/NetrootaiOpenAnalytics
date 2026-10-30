# Netrootai Open Analytics

Open Analytics for the Netroot AI free edition.

## Quick start

The release package is a 64-bit Linux tarball. It requires a Linux system with
`systemd` and root or `sudo` access.

### 1. Verify the download

Keep the tarball and checksum file in the same directory:

```bash
sha256sum -c netrootai_1.0.0_local_linux_amd64.tar.gz.sha256
```

### 2. Install and start Netroot AI

```bash
tar -xzf netrootai_1.0.0_local_linux_amd64.tar.gz
cd netrootai-1.0.0
sudo ./install.sh
```

The installer creates the service account and required directories, installs
Netroot AI under `/opt/netrootai`, and starts the `netrootai` systemd service.

### 3. Open the application

Verify that the service is running:

```bash
sudo systemctl status netrootai --no-pager
curl -I http://127.0.0.1:3005/login
```

Then open <http://127.0.0.1:3005> in a browser.

For a remote Linux server, create an SSH tunnel from your computer:

```bash
ssh -L 3005:127.0.0.1:3005 USER@SERVER_IP
```

Leave the tunnel open and visit <http://127.0.0.1:3005>.

## Useful commands

```bash
sudo systemctl restart netrootai
sudo systemctl stop netrootai
sudo journalctl -u netrootai -f
```

Persistent application data is stored in `/var/lib/netrootai` and remains
available when the application is upgraded.

See the [installation guide](installation%20guide.md) and
[Netroot AI documentation](https://netrootai.app/docs) for configuration and
public HTTPS deployment instructions.
