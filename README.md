<p align="center">
    <a href="https://snapcraft.io/calaboka">
        <img src="media/banner-800x200.png">
    </a>
</p>
<p align="center">
    <a href="https://www.paypal.com/donate?hosted_button_id=VVRR9R68YUWZ6">
        <img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif">
    </a>
</p>
<hr/>
<p>Welcome! This is where you can find some help and report issues with Calaboka.</p>

# Issue reporting
First, please make sure you are using the latest version, as bug fixes may have already been implemented in newer versions.

[![calaboka](https://snapcraft.io/calaboka/badge.svg)](https://snapcraft.io/calaboka)

Follow the [installation instructions](#installation) below and the troubleshooting instructions provided by the Calaboka app itself. If you are still having a problem, go ahead and [create a new issue](https://github.com/goodsoftworx/calaboka-issues/issues) if one doesn't already exist for that problem. Feel free to comment on existing issues, but please don't create duplicates.

## Installation
If you are having issues installing Calaboka on your choice of Linux distribution, refer to the installation instructions provided by Snapcraft on the [Calaboka snap page](https://snapcraft.io/calaboka).

## Collecting logs
When reporting an issue, please attach logs if applicable. Calaboka has two processes: a user daemon (background service) and a GUI app. Both produce log output, which can help with troubleshooting and bug investigations. Try to keep track of when the issue occurred and collect the logs for that period of time.

### Background service logs
Open a terminal and get the logs from the systemd journal:
```Shell
journalctl --user-unit snap.calaboka.daemon.service -e
```
To avoid output truncation, add the `--no-pager` option to the command before copying log lines:
```Shell
journalctl --user-unit snap.calaboka.daemon.service -e --no-pager
```

### GUI app logs
Run the app from a terminal and collect its output:
```Shell
calaboka
```

# Other helpful information

## GTK themes
Calaboka supports common GTK themes out of the box. This section provides information on how to install additional themes (if available).

### Pop!\_OS theme
Install the [pop-themes snap](https://snapcraft.io/pop-themes) and follow the instructions provided in its description. Relaunch the Calaboka app and you should see the Pop themes listed in the _Change theme_ dialog. Alternatively, you can run the following commands from a terminal:
```Shell
sudo snap install pop-themes
sudo snap connect calaboka:gtk-3-themes pop-themes:gtk-3-themes
sudo snap connect calaboka:icon-themes pop-themes:icon-themes
```

## Limitations
- Calaboka can only mute Spotify ads playing on the same computer. While Spotify allows you to play music on other (remote) devices, Calaboka can only mute Spotify on the same local machine. So make sure you install Calaboka where you intend to play your music (as long as it's a Linux machine).
