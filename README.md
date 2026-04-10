# demers-nssdc

Configuration code for the Demers machine called nssdc.
This is a Secondary Domain Controller (NSSDC) running on Debian.

## Installation

The server can be configured by calling this one-liner:

<!-- markdownlint-disable MD013 -->
```bash
wget -qO- 'https://raw.githubusercontent.com/jeremfg/setup/refs/heads/main/src/setup_git' | bash -s -- git@github.com:homeinfra/demers-nssdc.git main -- ./src/setup
```
<!-- markdownlint-enable MD013 -->

## Development

Using Microsoft VS Code

### Setup

1. Create SSH credentials on your client dev machine if you
don't have any already.
1. Add the public key to `/root/.ssh/authorized_keys` on the
server (nssdc)
1. Using the VS Code extension "Remote - SSH" from Microsoft, edit
your client-local `~/.ssh/config` by adding the following entry:

```txt
Host nssdc
  HostName nssdc.demers.jeremfg.com
  User root
  PreferredAuthentications publickey
  IdentityFile <private key>
```

1. Open a remote session in VS Code, on nssdc, and open this git
repository folder which should already be on the server following
the installation above.

### Developer environment

To set up your local development environment (pre-commit hooks, tools), run:

```bash
./tool/setup
```

