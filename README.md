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
placeholder.png  
favicon.ico  

MusicBeeIPC.dll is what allows the webserver to talk to MusicBee and get the current song data, as well as allowing it to control the song playback and shuffle/repeat states

MBCS.exe is the MusicBee Control Server. It's the Frontend/Middleman for the service

config.yml is the configuration. It allows the server to use whatever IP and port it wants, along with the Debug state of the server

app.log is, well, a log file. It's the server's output

DO NOT TAMPER! IF AN ERROR IS THROWN, CHECK HERE, THEN OPEN AN ISSUE


placeholder.png is, well, a placeholder image. It's used as a fallback for the album art in case it can't be found or errors out when serving

THIS IS CUSTOMIZABLE! FEEL FREE TO REPLACE


favicon.ico is the image the webserver will serve for the browser favicon. Simple
THIS IS CUSTOMIZABLE! FEEL FREE TO REPLACE


## Usage
http://{host}:{port} | All endpoints and app routes  
http://{host}:{port}/widget | OBS Stream Overlay  
http://{host}:{port}/dashboard | Control Dashboard. Includes Play, Pause, Stop, Previous, Next, Shuffle, Repeat, Lyrics, Expanded Basic Track Info  
http://{host}:{port}/controls | Control routes  
http://{host}:{port}/controls/<control> | Controls that don't require an argument  
http://{host}:{port}/controls/<control>/<arg> | Controls that do require arguments  

## Endpoints
In case you want to access any track data
/get_track_info | GET, returns JSON => trackTitle: str, artist: str, playState: bool -- str, shuffle: bool,
                       repeat: int -- [0, 1, 2], album: str, year: str

/album_art | GET, returns IMG => WEBP

/favicon.ico | GET, returns IMG => ICO

/placeholder.png | GET, returns IMG => PNG

/lyrics | GET, returns JSON => lyrics: str

# Gallery 
