# md5tools

Various utility scripts dealing with MD5 checksums.

For now, it only includes **md5dirs**

## md5dirs

Create separate .md5 checksums files in every directory

## INSTALL

### On MacOS

It can be installed with [Homebrew](https://brew.sh). This will install the latest version directly from github:

    brew install --HEAD mivk/tap/md5tools

### On Linux (or Mac without Homebrew)

There is no package yet, but it can be installed by copy/pasting these few lines:

    repo="mivk/md5tools"; script=md5dirs

    curl -L https://raw.githubusercontent.com/$repo/main/$script | tee $script
    chmod +x $script

If it was already installed, you can compare the new version to the installed version before overwriting it:

    meld $(which $script) $script
    # or
    diff $(which $script) $script

Finally:

    mv -v $script /usr/local/bin
    # or
    sudo mv -v $script /usr/local/bin/

And check the version with

    md5dirs -V

## See also
md5dirs man page: https://github.com/mivk/md5tools/blob/main/md5dirs.1.md

