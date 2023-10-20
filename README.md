# MBCS
Hi! This is a Repository for a [MusicBee](https://www.getmusicbee.com/) addon that allows you to control your MusicBee application from a WebServer with a nice, clean, non-interruptive UI
Currently, it's at a state where it's mostly alright, but it still needs some features, like a song progression bar, love status/rating, and a few other tweaks

# Getting Started
## Installing
Included are a few things:  
MusicBeeIPC.dll  
MBCS.exe  
config.yml  
app.log  
MusicBeeServer.lnk
placeholder.png  
favicon.ico  

MusicBeeIPC.dll is what allows the webserver to talk to MusicBee and get the current song data, as well as allowing it to control the song playback and shuffle/repeat states

MBCS.exe is the MusicBee Control Server. It's the Frontend/Middleman for the service

config.yml is the configuration. It allows the server to use whatever IP and port it wants, along with the Debug state of the server

app.log is, well, a log file. It's the server's output

DO NOT TAMPER! IF AN ERROR IS THROWN, CHECK HERE, THEN OPEN AN ISSUE

MusicBeeServer.lnk is an app shortcut. If you want to have the server launch on boot,  
open the Windows run dialog `⊞ Win` + `R`  
Type in `shell:startup`  
Hit `Enter`  
Now, move the shortcut to folder it opened by using `Left Mouse Button`, `Right Mouse Button` + `Hold` + `Drag` into the folder  
`Release`, click on `Move Here`

placeholder.png is, well, a placeholder image. It's used as a fallback for the album art in case it can't be found or errors out when serving

THIS IS CUSTOMIZABLE! FEEL FREE TO REPLACE


favicon.ico is the image the webserver will serve for the browser favicon. Simple
THIS IS CUSTOMIZABLE! FEEL FREE TO REPLACE


## Usage
http://`host`:`port` | All endpoints and app routes  
http://`host`:`port`/widget | OBS Stream Overlay  
http://`host`:`port`/dashboard | Control Dashboard. Includes Play, Pause, Stop, Previous, Next, Shuffle, Repeat, Lyrics, Expanded Basic Track Info  
http://`host`:`port`/controls | Control routes 
http://`host`:`port`/controls/<control> | Controls that don't require an argument  
http://`host`:`port`/controls/<control>/<arg> | Controls that do require arguments  

## Usage with OBS
Click on the + in the sources tab

Click on Browser, input a name, then click OK

Locate the directory you downloaded the exe to, there should be a config.yml file  
In there, look for  
config:  
  host: <ip>  
  port: <port>  

Put in to the URL bar in the OBS scene creation "http://`host`:`port`/widget"  
Be sure to replace the `host` with the host value in the config and `port` with the port value in confog.yml  
Set the Custom CSS to this `body { background-color: rgba(0, 0, 0, 0); margin: 0px auto; overflow: hidden;} h1, h3 {color: #FFF;}` 
Check `Shutdown source when not visible` and `Refresh Browser when scene becomes active`  
Click OK  
Now resize to your liking and you're all good!

## Endpoints
In case you want to access any track data to build your own control dashboard  
/get_track_info | GET, returns `JSON` => `trackTitle`: `str` , `artist`: `str`  `playState`: `bool -- str` , `shuffle`: `bool`,
                       `repeat`: `int -- [0, 1, 2]`, `album`: `str` , `year`: `str`   
/album_art | GET, returns `IMG` => `WEBP`  
/favicon.ico | GET, returns `IMG` => `ICO`  
/placeholder.png | GET, returns `IMG` => `PNG`  
/lyrics | GET, returns `JSON` => `lyrics`: `str`  



# Gallery 
## Control Dashboard
Plain  
![Dash 1](https://github.com/veillax1354/MBCS/blob/main/gallery/Dash1.png?raw=true)

Snackbar Toast Pause  
![Dash Snackbar Preview Pause](https://github.com/veillax1354/MBCS/blob/main/gallery/DashPause.png?raw=true)

Sackbar Toast Play  
![Sackbar Toast Play](https://github.com/veillax1354/MBCS/blob/main/gallery/DashPlay.png?raw=true)

OBS Stream Overlay/Widget  
![OBS Stream Overlay](https://github.com/veillax1354/MBCS/blob/main/gallery/Widget.png?raw=true)
