# Homelab CLI

A lightweight CLI to remotely wake, monitor, access, and manage a self-hosted Linux homelab using SSH, Tailscale, and Wake-on-LAN.

## Features

- **Status Check**: Quickly verify if the Raspberry Pi and the desktop server are online.
- **Wake-on-LAN**: Wake up the desktop server by sending a command through the Raspberry Pi.
- **Easy SSH**: One-command access to the desktop server.
- **Safe Shutdown**: Remotely power off the desktop server.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/gokul-t/homelab-cli.git
   cd homelab-cli
   ```

2. Install the script to your local bin:
   ```bash
   install -m 755 homelab ~/.local/bin/homelab
   ```

   Or install the latest public release binary directly:
   ```bash
   curl -sLo homelab https://github.com/gokul-t/homelab-cli/releases/latest/download/homelab
   chmod +x homelab
   install -m 755 homelab ~/.local/bin/homelab
   ```

## Usage

```bash
./homelab <command>
```

### Commands

| Command | Description |
| :--- | :--- |
| `status` | Check if the Pi and Desktop are reachable |
| `wake` | Wake the Desktop server via the Raspberry Pi |
| `ssh` | SSH into the Desktop server |
| `shutdown` | Shut down the Desktop server safely |
| `help` | Show usage information |

## Prerequisites

- SSH keys configured for passwordless access to both `homelab-pi` and `homelab`.
- A wake script located at `/usr/local/bin/homelab-wake` on the Raspberry Pi.
- Sudo permissions on the desktop server to execute `systemctl poweroff` without a password.
