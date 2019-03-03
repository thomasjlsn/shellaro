# Shellaro

A terminal music player written in bash, based on [fff](https://github.com/dylanaraps/fff)

- quick navigation
- vim keybindings
- play a song, play all, or shuffle all with a single keypress
- pause / play
- custom playlists
- directory shortcuts
- search with tab completion
- volume controls
- find & auto play (eg. Searching 'stopme' would match & auto-play DontStopMeNow.mp3. Searching 'oor' would match and play everything in 'TheDoors' directory)

## Table of Contents

* [Dependencies](#dependencies)
* [Usage](#usage)
    * [Navigation](#navigation)
    * [Play](#play)
    * [Playlists](#playlists)
    * [Volume](#volume)
* [Configuration](#configuration)
* [F.A.Q.](#faq)

## Dependencies

- [mpg321](http://mpg321.sourceforge.net/)
- amixer
- awk
- bash
- grep
- pgrep
- readlink
- sed

## Usage

### Navigation

```
k -- go up
j -- go down
l -- go to child dir
h -- go to parent dir

g -- go to top
G -- go to bottom

enter -- go to child dir
backspace -- go to parent dir

` -- go home ($MUSIC_DIRECTORY)
~ -- go home ($MUSIC_DIRECTORY)

[1-9] -- favorites

/ -- search

f -- find current song

(arrow keys also work for navigation)
```

### Play

```
enter -- play song

l -- play song
right arrow -- play song

p -- pause / play
n -- next song
K -- stop (kill mpg321)

; -- find and play song

q -- quit

a -- play all songs in directory
s -- shuffle all songs in directory
S -- shuffle all songs in $MUSIC_DIRECTORY
```

### Playlists

```
space -- mark file for playlist
enter -- play playlist

c -- clear marked selection
x -- clear marked selection
```

### Volume

```
u -- vol + 5%
d -- vol - 5%

+ -- vol + 5%
- -- vol - 5%

v -- set volume [0 - 100]
= -- set volume [0 - 100]

m -- toggle mute / unmute
```

## Configuration

**$MUSIC_DIRECTORY** is the base directory that Shellaro uses (this assumes you have all your music contained within a single directory)

the **$SHORTCUT** variables are used to set the paths for directory shortcuts which use the 1-9 keys

the **$COLOR** variables can be used to change the colors of shellaro

the **$ICON** variables can be used to set pause, play, stop, mute, and mark icons

### Color values

```
text colors:
30 -- black
31 -- red
32 -- green
33 -- yellow
34 -- blue
35 -- magenta
36 -- cyan
37 -- white

background colors:
40 -- black
41 -- red
42 -- green
43 -- yellow
44 -- blue
45 -- magenta
46 -- cyan
47 -- white
```

the **$ICON\*BOLD** variables can be used to set whether or not a color will be bold, 1 for bold, 0 for normal

## F.A.Q.

### Where did the name come from?

Shellaro is a combinaton of "shell" (in reference to bash) & "[Collaro](https://en.wikipedia.org/wiki/Collaro)" (an old phonograph manufacturer)

### Help, locate doesn't work!

if `;` (locate) is not working, the most likely cause is a non existant path in locate's databse (eg. a song was moved/deleted). Try updating mlocate.db with:

```
sudo updatedb
```

locate should now be working fine!
