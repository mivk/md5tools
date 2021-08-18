% md5dirs(1) August 2021

NAME
====

**md5dirs** - Create .md5 checksums files in every subdirectory

SYNOPSIS
========

**md5dirs** \[options ...] /some/directory

**md5dirs** \[**-h**|**-V**]

DESCRIPTION
===========

`md5dirs` creates separate MD5 checksums files in the folder given as argument, and in any of it's subfolders. Every subfolder gets it's own checksums file which references only files in the current folder, not those in other subfolders.

`md5dirs` **excludes** a number of files and folders which are normally not wanted:

* hidden directories (like ".Trashes", ".Spotlight-V100", etc.)
* MacOS ".DS_Store" files and resource forks (files starting with "._") and .
* **DCP** directories and all it's subdirectories. These are identified by the existence of a file named "ASSETMAP" or "ASSETMAP.xml"
* Directories which already contain a file with the wanted .md5 file name. By default, that name is "checksums.md5", unless you changed it with the **-f** option.

OPTIONS
=======

-h

:   Prints brief usage information.

-f Filename

: Specify the wanted filename for checksums files. The default is "checksums.md5". The ".md5" extension is added automatically if missing.
Example for Cinémathèque Suisse: **-f cs-md5** will create files named "cs-md5.md5".

-n

:  No action (dry_run). Don't actually calculate md5. Only select the files and calculate the total size, then show what would be done.

-d

:   Debug (can be repeated)

-V

: Show version and exit


EXAMPLES
=========
    md5dirs /my/folder

Create files named "cs-md5.md5" :

    md5dirs -f cs-md5 /my/folder

