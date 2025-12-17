# katoolin-fix

A quick and reliable fix for the **`apt-key deprecated`** warning/error when using **Katoolin** to add Kali Linux repositories on Ubuntu/Debian-based systems.

##  Problem

[Katoolin](https://github.com/LionSec/katoolin) is a popular Python script that lets you install Kali Linux tools on Ubuntu or Debian by adding Kali's official repositories. However, recent versions of `apt` (starting from Ubuntu 22.04 and Debian 11) have **deprecated the `apt-key` command**, which Katoolin relies on to add GPG keys.

This causes errors like:
```bash
Warning: apt-key is deprecated. Manage keyring files in trusted.gpg.d instead.
```
or even repository addition failures.

##  Solution

This project provides a **patched version of Katoolin** (or a companion fix script) that replaces the deprecated `apt-key` usage with the modern, secure method:

- Downloads the Kali GPG key directly
- Saves it as `/etc/apt/trusted.gpg.d/kali-archive-keyring.gpg`
- Maintains full compatibility with current APT standards

##  How to run

1. **Clone this repository:**
   ```bash
   git clone https://github.com/yourusername/katoolin-fix.git
   cd katoolin-fix
   sudo python3 katoolin-fix.py
   ```
