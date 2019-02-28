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

## Dependencies

- amixer
- bash
- [mpg321](http://mpg321.sourceforge.net/)
- pgrep

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

q -- quit, :q also works

a -- play all songs in directory
s -- shuffle all songs in directory
S -- shuffle all songs in $MUSIC_DIRECTORY
```

### Playlists

```
space -- mark file for playlist
enter -- play playlist

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

## Configuring Shellaro

**$MUSIC_DIRECTORY** is the base directory that Shellaro uses (this assumes you have all your music contained within a single directory)

the **$SHELLARO_FAV** variables are used to set the paths for directory shortcuts which use the 1-9 keys

## Where did the name come from?

Shellaro is a combinaton of "shell" (in reference to bash) & "[Collaro](https://en.wikipedia.org/wiki/Collaro)" (an old phonograph manufacturer)
