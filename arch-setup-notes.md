## ssh windows/wsl

[guide](https://devblogs.microsoft.com/commandline/sharing-ssh-keys-between-windows-and-wsl-2/)
[gh guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=windows)

```bash
# copy key to wsl
cp -r /mnt/c/Users/conta/.ssh ~/.ssh
chmod 600 ~/.ssh/id_ed25519

sudo pacman -S openssh

# other gitstuff
git config --global user.name "finnbechinka"
git config --global user.email "contact@bechinka.eu"
```

## update system

[error fix source](https://bbs.archlinux.org/viewtopic.php?id=258247)

```bash
sudo pacman-key --init
sudo pacman -Sy archlinux-keyring
# the above should not be necessary? but i got error on the below so...
sudo pacman -Syy
sudo pacman -Syu
```

## install stuff
### helix

[helix docs](https://docs.helix-editor.com/install.html#ubuntu)
[rust docs](https://doc.rust-lang.org/book/ch01-01-installation.html#installing-rustup-on-linux-or-macos)

```bash
sudo pacman -S helix

printf '\nexport EDITOR=helix' >> .bashrc

# install rust for lsp shit
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
# python lsp
sudo pacman -S python
sudo pacman -S python-pip
sudo pacman -S python-lsp-server
# c lsp ?
sudo pacman -S clang
```
### starship

[starship docs](https://starship.rs/guide/#%F0%9F%9A%80-installation)

```bash
sudo pacman -S starship
cp .bashrc .bashrc.backup
printf '\n\neval "$(starship init bash)"' >> .bashrc
exec bash
mkdir -p ~/.config && touch ~/.config/starship.toml
hx ~/.config/starship.toml
```
### zellij

[zellij docs](https://zellij.dev/documentation/installation#rust---cargo)

```bash
sudo pacman -S zellij
```

### lazygit

[lazygit docs](https://github.com/jesseduffield/lazygit?tab=readme-ov-file#ubuntu)

```bash
sudo pacman -S lazygit
```
### neofetch

```bash
sudo pacman -S fastfetch
printf '\nfastfetch' >> ~/.bashrc
```

### other stuff
```bash
printf '\nset completion-ignore-case On' >> ~/.inputrc

sudo pacman -S pyenv

# golang
sudo pacman -S go gopls revive staticcheck
```
