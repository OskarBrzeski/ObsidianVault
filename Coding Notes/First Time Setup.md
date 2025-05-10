# Download Node
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.3/install.sh | bash

npm install node  # download latest
npm install --lts # download lts
```
# Download Rust
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
# Download Go
Go to https://go.dev/doc/install
Download Linux tarball
In directory with tarball
```bash
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.24.3.linux-amd64.tar.gz
```
In `.bashrc` add
```bash
export PATH=$PATH:/usr/local/go/bin
```
Reload `.bashrc`
```bash
source .bashrc
```
