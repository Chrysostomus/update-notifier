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
and mark the relevant files as executables:
```
cd update-notifier && chmod +x update-notifier update-checker
```


## How to Use
update-notifier can be used in differnt ways. Here are some common examples:

### conky
Add the following line to the main part of your conky in order to check for updates every 7200 seconds (= 2 hours) and display a notification: 
```
${execi 7200 update-notifier}
```

### cron
You can also put update-notifier in your crontab file. There are differnt ways to do this. If you are already using a crontab file, you know what you need to do.

### autostart
Autostart can vary in function and form depending on your Desktop Environment or Window Manager. Add the following command to your autostart in order to check for updates every 2.5 hours and display a notification: 
```
update-checker 2h 30m
```