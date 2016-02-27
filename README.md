# update-notifier
Script to check for pacman updates and notify user about it. Can be called with conky, autostart script or cron.


## Installation

### Installation from Repositories
Install update-notifier from Manjaro Repositories:
```
sudo pacman -S update-notifier
```

### Manual Installation
First, make sure all dependencies are installed on your system:
- pacman
- [yaourt](https://wiki.archlinux.org/index.php/Yaourt)
- git

Then, clone this Github repository to your system with the command:
```
git clone https://github.com/Chrysostomus/update-notifier.git
```
and execute pacli:
```
cd update-notifier && chmod +x update-notifier update-checker
```


## How to Use

###conky

${execi 7200 update-notifier}


###cron


### autostart

