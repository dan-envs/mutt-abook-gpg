# abook-get-gpg-keys
Receive new GPG keys from within Mutt or NeoMutt with the "abook" TUI program.

**Note**: All contact names added to abook by Mutt or NeoMutt are prefixed
automatically with '#'. These are again removed when searching in Mutt or
NeoMutt. This is needed to find those entries by the `get_new_keys.sh`
script. So if you enter an address to your abook contacts manually, you
**have** to prefix the contact's name with a '#' char, otherwise they'll be
deleted when running the `get_new_keys.sh` script manually or from inside
Mutt or NeoMutt. That is because the `abook --mutt-query` command can't be
used with an empty string as an parameter. So I search addresses with the
command `abook --mutt-query '#'`. Keep that in mind!

# Setup
1. Setup your '~/.gnupg/gpg.conf' as follows:

```
auto-key-locate wkd,keyserver
keyserver hkps://keys.openpgp.org/
auto-key-retrieve
```

2. Run the following command to initialize the repo. This is a non destructive
   command, which doesn't delete any keys. It just creates the files needed by
   GnuPG, if they're not already present:

  `gpg --list-keys`

3. Clone this repository to '~/.abook':

  `git clone https://git.envs.net/dan/abook-get-gpg-keys.git ~/.abook`

## Setup for Mutt
Add the following line to your '.muttrc':

`source ~/.abook/abook.mutt.rc`

### How to operate with Mutt
**Start Mutt with the following command**: `mutt`  
**Add an email address to abook**: `'<SHIFT>+a'`  
**Refresh public GPG/OpenPGP keys for all contacts**: `'<CTRL>+k'`  
**Query addressbook**: `'<SHIFT>+q'`

## Setup for NeoMutt
Add the following line to your '~/.config/mutt/muttrc':

`source ~/.abook/abook.neomutt.rc`

Create an alias in your '.bashrc' or '.zsh' for `mutt`:

`alias mutt="neomutt"`

### How to operate with NeoMutt
**Start Mutt with the following command**: `mutt` or `neomutt`  
**Add an email address to abook**: `'<SHIFT>+a'`  
**Receive public GPG/OpenPGP keys for all unknown contacts**: `'<CTRL>+k'`  
**Query email contacts**: Press `'<TAB>'`

