# palbs
## PALBS (PulseAudio LoopBack Streaming) - Stream audio over WebRTC in Linux with PulseAudio

**`palbs`** is a simple Bash Script that temporarily configures the sources and sinks of programs using `pactl` to allow audio streaming.
Check out `man pactl` for more info on pactl.

## Installation

1. Clone this repository.
```
git clone https://github.com/gourish13/palbs.git ~/.palbs
```
2. `palbs` is a single bash script and has no other dependency.
If you are using `bash or bash-compatible` shell and want to try it without installing, you can directly source it or add the following line to bashrc.
```bash
source ~/.palbs/palbs
```
3. You can also perform user or system wide installation with the `install` script provided.
```bash
cd ~/.palbs/
chmod +x install palbs
```
  - For user installation.
  ```bash
  ./install
  ```
  Or,
  - For system wide installation run with root priviledges.
  ```bash
  sudo ./install
  ```
  
## Uninstallation
Run the `install` script with `-r` option with the correct priviledges as used during user or system wide installation.
```
./install -r
# Or,
sudo ./install -r
```

## Usage
The below usage information is available in the manpage for offline access. Make sure to check it after installation, if required.
```
  Usage: palbs command
  
      Commands
          -v | version    Shows version information.
          
          -h | -? | help  Shows help and exit.
          
          list-media [name]
              Shows the a list of ids and names of all the program instances playing some media.
              If the optional parameter name is specified with the name of a  particular program,
              then the list only contains instances of that program.
              
          list-stream [name]
              Shows the a list of ids and names of all the program instances recording audio.
              If the optional parameter name is specified with the name of a particular program,
              then the list only contains instances of that program.
              
          start media-name stream-name
              Configures and changes the sink and source of the media playing program and streaming
              program respectively specified as media-name and stream-name  and sets them in such 
              a way that the streaming program receives input from media being played by the 
              other one.
              
          stop   
              Unloads the modules changed to make the source and sink set back to initial defaults.
              
          force-stop
              Restarts the PulseAudio service to load default PulseAudio configuration.
              
```
