## NAME

	filltag - tool for read/write tags and rename flac, ogg and mp3 files.

## SYNOPSIS

	- Show tags:
	```filltag -i file1 [file2 file3 ...]```

	- Fill tags:
	```filltag [-a 'Artist'] [-b 'Album'] [-y year] [-g genre] [-n track number] [-N total tracks] [-t 'Song title'|-A] file1 [file2 file3 ...]```

	- Recode tags:
	```filltag -R file1 [file2 file3 ...]```

	- Rename files:
	```filltag -r [-T 'template'] file 1 [file 2 file 3 ...]```

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
	```filltag -rA -a 'Behemoth' -b 'Grom' -y 1996 -g 'Black Metal' *.mp3```

	- rename files with template:
	```filltag -r -T '\$num - \$artist - \$title (\$album, \$year)' *```
	
## AUTHOR
	[Akaky Chertyhansky](akakychert@gmail.com)
