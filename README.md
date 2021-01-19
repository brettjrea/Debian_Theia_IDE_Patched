# Debian_Theia_IDE_Patched
Commands to run Theia IDE on Debian Linux with patches for mobile usability.

```
sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y
```

```
sudo apt install curl git python make g++ wget -y
```

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash
```

```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" 
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```
*If you can't copy and paste the above command, close and reopen the terminal to start using NVM and continue.*


```
nvm install 12.20.1
```

```
npm install -g yarn
```

```
mkdir ~/.theia
cd ~/.theia
```

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/master/settings.json
```

```
mkdir ~/theia
mkdir ~/theia/patches/
cd ~/theia/patches/
```

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/main/%40theia%2Bcore%2B1.10.0-next.31d47498.patch
```

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/main/%40theia%2Bfilesystem%2B1.10.0-next.31d47498.patch
```

```
cd ~/theia/
```

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/master/package.json
```

```
yarn add patch-package postinstall-postinstall
```

```
yarn theia build
```

```
yarn start /my-workspace --hostname 0.0.0.0 --port 8080
```
