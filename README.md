# abook-get-gpg-keys
Receive new GPG keys from within Mutt or NeoMutt with the "abook" TUI program.

**!!!THIS IS A WORK-IN-PROGRESS!!!**

# Setup
1. Setup your '~/.gnupg/gpg.conf' as follows:

```
auto-key-locate wkd,keyserver
keyserver hkps://keys.openpgp.org/
auto-key-retrieve
```

2. Clone this repository to '~/.abook':
`git clone https://git.envs.net/dan/abook-get-gpg-keys.git ~/.abook`

## Setup for Mutt
Add the following line to your '.muttrc':

`source ~/.abook/abook.mutt.rc`

### How to operate with Mutt
**Start Mutt with the following command**: `mutt`  
**Add an email address to abook**: `'<SHIFT>+a'`  
**Receive public GPG/OpenPGP keys for all unknown contacts**: `'<CTRL>+a'`

## Setup for NeoMutt
Add the following line to your '~/.config/mutt/muttrc':

`source ~/.abook/abook.neomutt.rc`

Create an alias in your '.bashrc' or '.zsh' for `mutt`:

`alias mutt="neomutt"`

### How to operate with NeoMutt
**Start Mutt with the following command**: `mutt` or `neomutt`  
**Add an email address to abook**: `'a'`  
**Receive public GPG/OpenPGP keys for all unknown contacts**: `'<SHIFT>+a'`  
**Query email contacts**: Press `'<TAB>'`

