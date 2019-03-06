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
    * [Play](#play)
    * [Playlists](#playlists)
    * [Volume](#volume)
    * [Other](#other)
* [Configuration](#configuration)
* [F.A.Q.](#faq)

## Dependencies

- [mpg321](http://mpg321.sourceforge.net/)
- amixer
- awk
- kill
- killall
- locate
- pgrep
- readlink
- sed

## Usage

```
q -- quit

k -- go up
j -- go down
l -- go to child dir
h -- go to parent dir

g -- go to top
G -- go to bottom

enter -- go to child dir
backspace -- go to parent dir

` -- go to playlists
~ -- go home ($MUSIC_DIRECTORY)

[1-9] -- favorites

. -- toggle hidden files

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

a -- play all songs in directory
s -- shuffle all songs in directory
S -- shuffle all songs in $MUSIC_DIRECTORY
```

### Playlists

*playlists are saved to $MUSIC_DIRECTORY/.playlists*

*playlists are saved as 'somename.list'*

```
space -- mark file for playlist
enter -- play marked files

c -- clear marked selection
x -- clear marked selection

COMMANDS

:add -- add marked files to playlist
:del -- delete a playlist
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

### Commands

```
: -- command line

:q -- quit
:add -- add marked files to playlist
:del -- delete a playlist
```

### Other

```
r -- redraw screen
R -- restart program (This is intended for testing purposes only and will not work without updating the path in 'key()')

COMMANDS

:debug -- trace
:debug-x -- trace executables
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

if `;` (locate) is not working, the most likely cause is a non existant path in locate's databse (eg. a song was moved/deleted). Try updating mlocate.db by running the following in your terminal:

```
$sudo updatedb
```

locate should now be working fine!
