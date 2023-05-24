# AI/DEV 서버 설정하기

## Server 단(Ubuntu 22.04 LTS)

- Locale 설정 

https://beomi.github.io/2017/07/10/Ubuntu-Locale-to-ko_KR/

```bash
sudo locale-gen ko_KR.UTF-8
sudo dpkg-reconfigure locales
```

- zsh 및 configuration

```bash
curl -fsSL https://raw.githubusercontent.com/donny-son/gh-zsh/main/gh-zsh.sh | bash 
```

- pyenv
```bash
sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev -y

curl https://pyenv.run | bash
```

- Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

- nvm

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
```

- Go

```bash
curl -LO https://get.golang.org/$(uname)/go_installer && chmod +x go_installer && ./go_installer && rm go_installer
```

- Docker

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt install docker-ce -y
```

- Postgres

```bash
sudo apt install libpq-dev
```

- Dev tools

```bash
sudo apt install build-essential manpages-dev -y
```

- CUDA

```bash
# https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_network
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.0-1_all.deb
sudo dpkg -i cuda-keyring_1.0-1_all.deb
sudo apt-get update
sudo apt-get -y install cuda

# in ~/.zshrc
# export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}
# export LD_LIBRARY_PATH=/usr/local/cuda/lib${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```

- Nvim

```bash
sudo apt-get update
sudo apt-get install python-dev python-pip python3-dev python3-pip
sudo apt-get install ninja-build gettext cmake unzip curl

git clone git@github.com:neovim/neovim.git
cd neovim
git checkout release-0.9
make CMAKE_BUILD_TYPE=Release
sudo make install
git clone https://github.com/AstroNvim/AstroNvim ~/.config/nvim
git clone https://github.com/donny-son/astronvim-config ~/.config/nvim/lua/user

# in ~/.zshrc
# export SUDO_EDITOR=/usr/local/bin/nvim
# export VISUAL=$SUDO_EDITOR
# export EDITOR=$SUDO_EDITOR
```

- Tmux

```bash
git clone https://github.com/gpakosz/.tmux.git $HOME/.oh-my-tmux
mkdir -p $HOME/.oh-my-tmux
mkdir -p $HOME/.config/tmux
ln -s $HOME/.oh-my-tmux/.tmux.conf ~/.config/tmux/tmux.conf
cp $HOME/.oh-my-tmux/.tmux.conf.local ~/.config/tmux/tmux.conf.local
```

- Monitoring Tool

```bash
go install github.com/xxxserxxx/gotop/v4/cmd/gotop@latest
```

## Client 단

- [termscp](https://termscp.veeso.dev/#get-started) 
