# ubuntu16Setup

# update

```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```

apt://ubuntu-restricted-extras
apt://flashplugin-installer

# vlc
```shell
sudo apt install vlc
```

# sublime stuff
------------
* "ctrl + shift + p"
* *package control
* material theme
* anaconda
* advance new file
* sidebar enhancement

Linux - create "Default (Linux).sublime-mousemap" in ~/.config/sublime-text-3/Packages/User

Mac - create "Default (OSX).sublime-mousemap" in ~/Library/Application Support/Sublime Text 3/Packages/User

Win - create "Default (Windows).sublime-mousemap" in %appdata%\Sublime Text 3\Packages\User

[
    {
        "button": "button1", 
        "count": 1, 
        "modifiers": ["ctrl"],
        "press_command": "drag_select",
        "command": "goto_definition"
    }
]


# enable ‘Minimise on Click’
```shell
gsettings set org.compiz.unityshell:/org/compiz/profiles/unity/plugins/unityshell/ launcher-minimize-window true
```

# customize
```shell
sudo apt-get install unity-tweak-tool
```

# theme
```shell
sudo sh -c "echo 'deb http://download.opensuse.org/repositories/home:/Horst3180/xUbuntu_16.04/ /' >> /etc/apt/sources.list.d/arc-theme.list"

sudo apt-get update && sudo apt-get install arc-theme

wget http://download.opensuse.org/repositories/home:Horst3180/xUbuntu_16.04/Release.key

sudo apt-key add - < Release.key
```

# icon
```shell
sudo add-apt-repository ppa:noobslab/icons
sudo apt-get update
sudo apt-get install arc-icons
```


# opencv
```shell
sudo apt-get install build-essential cmake pkg-config
sudo apt-get install libjpeg8-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install libgtk-3-dev
sudo apt-get install libatlas-base-dev gfortran
```

http://www.pyimagesearch.com/2016/10/24/ubuntu-16-04-how-to-install-opencv/
