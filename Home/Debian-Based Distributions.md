---
Alias: Pop_OS! / Ubuntu / Debian Based
Tag: linux
Date: 2024-02-21
Status: In-Progress
---

## List of Contents



# Installing Applications

## [eza]()

>[!tip] Replacement for `ls`

### Install `gpg`

To install `gpg`, we need to run the following commands:

```bash

sudo apt update
sudo apt install -y gpg

```

### Install eza

```bash

sudo mkdir -p /etc/apt/keyrings
wget -qO- https://raw.githubusercontent.com/eza-community/eza/main/deb.asc | sudo gpg --dearmor -o /etc/apt/keyrings/gierens.gpg
echo "deb [signed-by=/etc/apt/keyrings/gierens.gpg] http://deb.gierens.de stable main" | sudo tee /etc/apt/sources.list.d/gierens.list
sudo chmod 644 /etc/apt/keyrings/gierens.gpg /etc/apt/sources.list.d/gierens.list
sudo apt update
sudo apt install -y eza

```

## Neovim

Normally, when you run the command:

```bash

sudo apt install neovim

# OR

sudo apt-get install neovim

```

It will **not** be of the latest version. Instead, it will be some random old version of Neovim.

This is because, *Debian* based distribution are "*stable*". Meaning that **packages** and **softwares** are generally not updated compared to *rolling* distribution like [[Arch Linux]].

Hence, we need to **add** the most recent version / repository of Neovim. Follow the steps below $\downarrow$ to get the latest version of Neovim.

### Add Neovim Stable and Unstable PPA Repository

```bash

# Add Stable Neovim Repository
sudo add-apt-repository ppa:neovim-ppa/stable

# Add Unstable Neovim Repository
sudo add-apt-repository ppa:neovim-ppa/unstable

```

### Perform an Update

To be able to use these repositories that we just added. We need to perform a quick **update**.

>I also like to upgrade any packages ( that needs to be upgraded ) while doing this.

```bash

sudo apt update; sudo apt upgrade -y

```

### Finally, Install Neovim

To install Neovim, use the command below $\downarrow$

```bash

sudo apt install neovim

```

To check the current version of Neovim, just run the command:

```bash

nvim --version

```

>It should be on the latest version!

### Install `ripgrep` and `fd`

>[!note] For [telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)
>This is optional, but they are really **small** packages / softwares.
>Just download them!

#### ripgrep

```bash

sudo apt install ripgrep

```

#### fd

```bash

sudo apt install fd-find

```

### Clone [dotfiles](https://www.github.com/Sunhaloo/dotfiles) Repository

To clone the repository, run the command below $\downarrow$:

```bash

git clone https://www.github.com/dotfiles

```