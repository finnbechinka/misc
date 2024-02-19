## ssh windows/wsl

[guide](https://devblogs.microsoft.com/commandline/sharing-ssh-keys-between-windows-and-wsl-2/)
[gh guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=windows)

```bash
// copy key to wsl
cp -r /mnt/c/Users/<username>/.ssh ~/.ssh
chmod 600 ~/.ssh/id_rsa

// other gitstuff
git config --global user.name "finnbechinka"
git config --global user.email "contact@bechinka.eu"
```

## install stuff
### starship

[starship docs](https://starship.rs/guide/#%F0%9F%9A%80-installation)

```bash
curl -sS https://starship.rs/install.sh | sh
mv .bashrc .bashrc.backup
printf '\n\neval "$(starship init bash)"' >> .bashrc
exec bash
mkdir -p ~/.config && touch ~/.config/starship.toml
hx ~/.config/starship.toml
```
### helix

[helix docs](https://docs.helix-editor.com/install.html#ubuntu)
[rust docs](https://doc.rust-lang.org/book/ch01-01-installation.html#installing-rustup-on-linux-or-macos)

```bash
sudo add-apt-repository ppa:maveonair/helix-editor
sudo apt update
sudo apt install helix

sudo update-alternatives --set editor /usr/bin/hx

# install rust for lsp shit
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
# python lsp
sudo apt install python3 python3-pip
pip install python-lsp-server
# c lsp
sudo apt install clangd
```
### zellij

[zellij docs](https://zellij.dev/documentation/installation#rust---cargo)

```bash
cargo install --locked zellij
```

### lazygit

[lazygit docs](https://github.com/jesseduffield/lazygit?tab=readme-ov-file#ubuntu)

```bash
LAZYGIT_VERSION=$(curl -s "https://api.github.com/repos/jesseduffield/lazygit/releases/latest" | grep -Po '"tag_name": "v\K[^"]*')
curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/latest/download/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz"
tar xf lazygit.tar.gz lazygit
sudo install lazygit /usr/local/bin
```
### neofetch

```bash
sudo apt install neofetch
printf '\nneofetch' >> ~/.bashrc
```