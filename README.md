# Lyra Viewer — APT repository

The APT distribution channel for [Lyra Viewer](https://github.com/lyra-viewer/Lyra).

This repo is served as a static, GPG-signed APT repository via **GitHub Pages**.

---

## Install

```bash
# 1. Trust the repository signing key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://lyra-viewer.github.io/apt-lyra/lyra-archive-keyring.asc \
  | sudo gpg --dearmor -o /etc/apt/keyrings/lyra.gpg

# 2. Add the repository
echo "deb [signed-by=/etc/apt/keyrings/lyra.gpg] https://lyra-viewer.github.io/apt-lyra stable main" \
  | sudo tee /etc/apt/sources.list.d/lyra.list

# 3. Install
sudo apt update
sudo apt install lyra-viewer
```

Updates then arrive through the normal `sudo apt update && sudo apt upgrade`.

To remove the repository:

```bash
sudo rm /etc/apt/sources.list.d/lyra.list /etc/apt/keyrings/lyra.gpg
sudo apt update
```

---
