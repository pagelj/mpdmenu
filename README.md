Simple dmenu frontend for MPD.

# Main changes to source

Forked from [https://github.com/cdown/mpdmenu](https://github.com/cdown/mpdmenu).

I added some features that the source does not support but that I wanted to have:

- support to search for either artist or composer, as I have a lot of classical music and organize it with the composer tag
- by default, `mpdmenu` shows all the tracks in my `mpd` database with artist/composer, album and title information. I can then search through all tracks using `dmenu` and directly add the found track
- filter by artist/composer and/or album with `dmenu` entries, rather than `mpdmenu` command line arguments (like [https://github.com/BenWillemsen/mpdmenu](https://github.com/BenWillemsen/mpdmenu) and forks)
- control clearing the playlist with a `dmenu` entry

Simple tasks like playback I handle with keybindings to `mpc` calls. For all the more complicated tasks, like jumping to a certain time stamp etc., I use a `mpd` musicplayer interface, in my case `ncmpcpp`

# Arguments

Pass `mpdmenu` arguments first, followed by any `dmenu` arguments. They are separated by `::`. For example:

```
    mpdmenu -p :: -sb '#000000'
```

`-l` is library mode (default), which descends artists and albums. `-p` is
playlist mode, which selects a track from the current playlist.
