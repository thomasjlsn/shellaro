# Shellaro

A terminal music player written in bash, based on [fff](https://github.com/dylanaraps/fff)

- quick navigation
- play a song, play all, or shuffle with a single keypress
- vim keybindings
- directory shortcuts
- search with tab completion
- volume controls

## Dependencies

- bash
- [mpg321](http://mpg321.sourceforge.net/)
- pgrep

## Usage

```
k -- go up
j -- go down
h -- go to parent dir
l -- go to child dir / play song

g -- go to top
G -- go to bottom

a -- play all songs in directory
s -- shuffle all songs in directory
S -- shuffle all songs in $MUSIC_DIRECTORY

p -- pause / play

u -- vol + 5%
d -- vol - 5%
v -- set volume (0 - 100)
m -- toggle mute / unmute

/ -- search
~ -- go home ($MUSIC_DIRECTORY)

[1-9] -- favorites

K -- kill mpg321
R -- redraw screen (eg. killall causes errors sometimes, leaving a message on the screen, 'R' will force redraw the screen to get rid of the message until I find a proper solution)

q -- quit, :q also works
```

## Non Vim-like alternatives

```
up -- go up
down -- go down
left -- go to parent dir
right -- go to child dir / play song

enter -- go to child dir / play song
backspace -- go to parent dir

+ -- vol + 5%
- -- vol - 5%
= -- set volume (0 - 100)
```

## Configuring Shellaro

**$MUSIC_DIRECTORY** is the base directory that Shellaro uses (this assumes you have all your music contained within a single directory)

the **$SHELLARO_FAV** variables are used to set the paths for directory shortcuts which use the 1-9 keys

## Where did the name come from?

Shellaro is a combinaton of "shell" (in reference to bash) & "[Collaro](https://en.wikipedia.org/wiki/Collaro)" (an old phonograph manufacturer)