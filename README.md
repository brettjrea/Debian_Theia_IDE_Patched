# Debian_Theia_IDE_Patched
Commands to run Theia IDE on Debian Linux with patches for mobile usability.

### Quickscript:

```
sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y
sudo apt install git python make g++ wget -y
nvm install 12.20.1
npm install -g yarn
mkdir ~/.theia
cd ~/.theia
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/master/settings.json
mkdir ~/theia
mkdir ~/theia/patches/
cd ~/theia/patches/
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/main/%40theia%2Bcore%2B1.10.0-next.31d47498.patch
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/main/%40theia%2Bfilesystem%2B1.10.0-next.31d47498.patch
cd ~/theia/
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/master/package.json
yarn add patch-package postinstall-postinstall
yarn theia build
yarn start /my-workspace --hostname 0.0.0.0 --port 8080
```

---

### Always be updating:

```
sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y
```

### Install required programs:

```
sudo apt install git python make g++ wget -y
```

### Install version of node required for theia:

```
nvm install 12.20.1
```

### Set default Node as 12.20.1:

```
nvm alias default 12.20.1
```

*Because theia uses yarn to start, the default node has to be set to 12.20.1, so other apps have to have node set in there .nvmrc files and be run with NPM*

### Use NPM to install yarn globally:

```
npm install -g yarn
```

### Create and move into a .theia directory:

```
mkdir ~/.theia
cd ~/.theia
```

### Download a settings.json file for the .theia directory:

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/master/settings.json
```

### Create a theia directory, a patches subfolder and move into it:

```
mkdir ~/theia
mkdir ~/theia/patches/
cd ~/theia/patches/
```

### Download patches with CSS fixes for mobile use:

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/main/%40theia%2Bcore%2B1.10.0-next.31d47498.patch
```

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/main/%40theia%2Bfilesystem%2B1.10.0-next.31d47498.patch
```

### Move into theia directory:

```
cd ~/theia/
```

### Download package.json to build theia with yarn from:

```
wget https://raw.githubusercontent.com/brettjrea/Debian_Theia_IDE_Patched/master/package.json
```

### Use yarn to add patch-package and install patches.

```
yarn add patch-package postinstall-postinstall
```

### Use yarn to build theia:

```
yarn theia build
```

### Use yarn to start theia on localhost port 8080:

```
yarn start /my-workspace --hostname 0.0.0.0 --port 8080
```

---

*Quickly start after a shutdown or reboot.*

```
cd ~/theia/
yarn start /my-workspace --hostname 0.0.0.0 --port 8080
```
