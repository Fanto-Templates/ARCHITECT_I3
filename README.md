# CREATING AND CONFIGURING AN MANJARO I3

### MY CHEAT-SHEETS

* [TMUX](Cheat-Sheets/TMUX_Commands.txt)
* [I3 COMMANDS](Cheat-Sheets/i3_commands.txt)
* [QUTEBROWSER](Cheat-Sheets/qute_commands.txt)
* [CMUS](Cheat-Sheets/cmus_command.txt)


### PROGRAMS I KEEP BASICS

| Name | Use for | Command | Config File Location
|---|---|---|---|
| Ranger | GUI look on directories from terminal(to exit press <kbd>Q</kbd>)|`ranger`|**~/.config/ranger/rc.conf**
| Scrot  | screenshot the scren from terminal | `scrot -d 10 (10 seconds to take screenshot)`| None 
| Nitrogen | To change the wallpaper from Desktop | `nitrogen directory/with/images` | None
| Gtop | sudo pacman -S npm && npm install gtop -g | `gtop`|None

### MY CONFIGURATIONS

| Program | Use for | My Configuration | Status |
|---|---|---|---|
| Color Configuration| Define the System Colors| [Click Here](Colors/README.md) | :heavy_check_mark:
| Git Configurations|Define Shell Git configurations|[Click Here](Git/README.md)|:heavy_check_mark:
| My Font - xos4 Terminus|Define my favorite Font|[Click Here](Terminus_Font/README.md)| :heavy_check_mark:
| My PS1 Configuration|Define the information showed on terminal|[Click Here](Bashrc/README.md)|:heavy_check_mark:
| Cmus|	Program to run music on terminal|[Click Here](Cmus/README.md)|:heavy_check_mark:
| Conky| Program to show system information on Desktop|[Click Here](Conky/README.md)|:heavy_check_mark:
| Urxvt Terminal| Terminal 100% customizable|[Click Here](Urxvt/README.md)|:heavy_check_mark:
| Cli-visualizer| Sound visualization on Terminal |[Click Here](Cli-visualizer/README.md)|:heavy_check_mark:
| Qutebrowser | Command-Line Browser |[Click Here](Qutebrowser/README.md)|:heavy_check_mark:
| Picom | Program to make windows transparent|[Click Here](Picom/README.md)|:heavy_check_mark:
| i3-blocks| status bar to i3|[Click Here](i3_blocks/README.md)|:x:

### VIM CONFIGURATION

* vimrc CONFIG FILE LOCATION: **/etc/vimrc**
* Here some types of modifications

```sh
# Show number informations
set number
# Code Highlight
syntax on
# Tab space
set tabstop=2
# Autoindentation
set autoindent
```
* Website to create colorscheme for VIM: http://bytefluent.com/vivify/
* My Colorscheme is in **VIM** Directory on this Repo
* WHERE TO PUT THE COLORSCHEME: **/usr/share/vim/vim82/colors**
* AFTER OPEN YOUR VIMRC FILE AND PUT:

```sh
colorscheme <nameofthescheme>
```

### NEOFETCH

* CONFIGURATION FILE LOCATION: **~/.config/neofetch/config.conf**
* inside this file, there is the part of the font colors
* I insert the w3m settings downloaded: `sudo pacman -S w3m`
	* This serves to insert image on neofetch
* i putted like this:

```sh
#order: tittle,@,underline,subtittle,colon,info
colors=(2 2 2 2 2 7) #green

#Image source
image_source="w3m"

#Ascii Distro
ascii_distro="~/Imagens/Wallpapers/manjaro_neofetch.png"

"Ascii color
ascii_colors(2)
```
* My configuration is on **Neofetch** Directory

### SOUND - PULSEAUDIO WITH PAVUCONTROL
* First we need to download pulseaudio = `sudo pacman -S pulseaudio`
* Second we download pavucontrol = `sudo pacman -S pavucontrol`
* Restart the Computer = `shutdown -r now`
* To use the system, write on the Shell the Following command: `pavucontrol`
* I create a file on **~/.config/pulse/launch.sh** with the following:

```sh
pulseaudio --kill
pulseaudio --start 
```
* I create a command to the i3 configuration to call this file:

```sh
exec --no-startup ~/.config/pulse/launch.sh
bindsym $mod+Ctrl+m exec pavucontrol
```
* if the sound doesn't work, stop with `pulseaudio --kill` and then `pulseaudio --start`

### PCMANFM

* pcmanfm is a GUI visualization for i3, to see all files and archives
* INSTALLATION: it already comes with manjaro i3, but you can install with: `sudo pacman -S pcmanfm`
* CONFIGURATION FILE: 

### POLYBAR

* Polybar is to apresent some information on desktop
* INSTALLATION: `sudo pacman -S polybar`
* Send the config to **~/.config/polybar**: `install -Dm644 /usr/share/doc/polybar/config ~/.config/polybar/`
* to test the example you go to the _.config/polybar/_ and use this command: `polybar example`
* I create my example from the Github Repo of Polybar
* My config file is in the **Polybar** Directory
* Create the _launch.sh_ to call on i3 and it is in the **Polybar** Directory too
* Make Runnable: `chmod +x launch.sh`
* Call the file on i3 config:
```sh
exec_always --no-startup-id $HOME/.config/polybar/launch.sh
```
* Comment all bar{} part on the i3 config file

### VIM PLUGINS

* we can add vim plugins using vim-plug
* It's a minimalist plugins installations to vim
* take the **plug.vim** on my **vim** directory and put on **~/.vim/autoload**
* now put this command on terminal:

```sh
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
* now go to **/etc/vimrc** and put inside the plugin, like the lightline

```sh
Plug 'itchyny/lightline.vim'
```
* Open your vim













