# ecasound chainsetup
my ecasound chainsetup for easy cli audio multitracking.

## install

```
$ git clone https://github.com/torsbos/ecasound.git 
$ cd eca && mkdir rec mix
```

## usage

to record track 1:

```
$ rec rec/1.mp3
```

to record track 2, and start multitracking:

```
$ ecasound -c -s rec2*
```

this will enter the interactive mode.
you might need to enter:

```
> setpos 0
```

to reset the playhead 

to record, type:

```
> t
```

you can repeat this as many times as you wish.
the file will be overwritten, meaning only the last recording is saved.

to exit, type:

```
> s
```

now you have two tracks, residing in the `eca/rec` folder

to record track 3, repeat previous steps but replace `rec2*` with `rec3*`

this goes for track 4 aswell.

(you could theoretically add as many tracks as your system can handle,
for now i have added 4 tracks).

to mix down to one file and play:

```
$ ecasound -s mix.* && play mix/*
```

## tips

make aliases for recording and mixing. for example:

```
$ alias er='ecasound -c -s' 
$ alias em='ecasound -s mix.* && play mix/*' 
```
recording then becomes:

```
$ er rec2*
```

and mixing down with playback simply becomes:

```
$ em
```

## dependencies
`ecasound`

`sox` 

`pipewire-jack`
