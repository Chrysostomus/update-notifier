# update-notifier
Script to check for pacman and yaourt updates and notify user about it. Can be called with conky, autostart script or cron.
 
 This script will notify the user as soon as updates are available. It uses the "notify-send" command to do this. If you want to test, whether it can work on your system, execute this command in your terminal:
 ```
 notify-send "Hi"
 ```
 You should see a notification pop up. If you don't you probably lack either libnotify or notification daemon (dunst, xfce4-notification-daemon etc). If you use a desktop enviroment, you should have these installed by default.

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

An example line in crontab can be (in order to check for updates every 7 hours):
 ```
 * */7 * * * update-notifier
 ```
 

### autostart
Autostart can vary in function and form depending on your Desktop Environment or Window Manager. Add the following command to your autostart in order to check for updates every 2.5 hours and display a notification: 
```
update-checker 2h 30m
```
Other examples are (for updating every 2 hours and 3 days):
 ```
 +update-checker 7200
 ```
 ```
 update-checker 3d
 ```

The default is 6 hours. This happens if you run update-checker witgout arguments.
