---
sidebar_position: 1
---

# Install Oh-My-Zsh!

### Install zsh

```bash
sudo apt install zsh
chsh -s /bin/zsh "$USER"
```

### Install Oh-My-Zsh!

```bash
git clone https://github.com/ohmyzsh/ohmyzsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

### Install powerlevel10k

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/custom/themes/powerlevel10k
```

### Install plugins

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-autosuggestions.git ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-completions.git ~/.oh-my-zsh/custom/plugins/zsh-completions
```

### Configure powerlevel10k

```bash
vim ~/.zshrc
```

Add these lines:

```
ZSH_THEME=powerlevel10k/powerlevel10k

plugins=(
	 git
	 zsh-syntax-highlighting
	 zsh-autosuggestions
	 zsh-completions
)
```

Execute zsh:

```
zsh
```

Follow the config steps
