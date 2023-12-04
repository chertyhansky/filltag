[![Bash](https://img.shields.io/badge/Shell-464646?logo=zsh)](https://git.savannah.gnu.org/cgit/bash.git)

## NAME

filltag - tool for read/write tags and rename flac, ogg and mp3 files.

## SYNOPSIS

- Show tags:
```sh
filltag -i file1 [file2 file3 ...]
```

- Fill tags:
```sh
filltag [-a 'Artist'] [-b 'Album'] [-y year] [-g genre] [-n track number] [-N total tracks] [-t 'Song title'|-A] file1 [file2 file3 ...]
```

- Recode tags:
```sh
filltag -R file1 [file2 file3 ...]
```

- Rename files:
```sh
filltag -r [-T 'template'] file 1 [file 2 file 3 ...]
```

## OPTIONS

-i
	Show tags.

-a 'Artist'
-b 'Album'
-y year
-g 'Genre'
-t 'Song title'
	Fill the apropriate fields. If more then wone file specified, the
	same tags will be written to all these files.

-A
	Ask the song title for each file.

-n number
	Track number. If more then one file specified, number will growing
	up by 1 for each file. If not specified, files will be numbered
	from 1 in sort order.

-N number
	Total tracks number. If not specified, number of files will be
	written.

-O
	Only rename files, do not fill empty tags.

-R
	Recode tags from CP1251 to utf-8.

-S
	Transliterate tags (only works with MP3 and UTF-8 tags)

-r
	Rename files (filling empty tags).

-T 'template'
	Template for renaming files. Contains:
		\$num - number of files;
		\$totnum - total number of files;
		\$artist - artist;
		\$album - album;
		\$genre - genre;
		\$year - year;
		\$title - song title.
	If template not specified, then used '\$num - \$title'.

-h
	Show this help message.

## EXAMPLES
- fill tags of mp3 files and rename it:
```sh
filltag -rA -a 'Behemoth' -b 'Grom' -y 1996 -g 'Black Metal' *.mp3
```

- rename files with template:
```sh
filltag -r -T '\$num - \$artist - \$title (\$album, \$year)' *
```

## DEPENDENCIES
- mid3v2 (from python-mutagen package) for mp3 files
- vorbiscomment (from vorbis-tools package) for ogg files
- metaflac (from flac package) for flac files
	
## AUTHOR
Karnaukhov P.N. aka Akaky Chertyhansky (akakychert@gmail.com)

## LICENSE
GNU General Public License v3.0 or later
