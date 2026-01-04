# musicrypt
a set of scripts to manage a local music collection

1. alcflac: simply converts alac codec files to flac files, does so in ~/Music/ by default but can be changed using --dir "~/new-folder/", -v shows a live log of whats happening, its relativly quick and the only dependency is ffmpeg
2. m3u82m3u: converts .n3u8 playlist files to n3u files, mainly for mpd this just looks in "~/Music/" and converts, same --dir and -v commands apply
