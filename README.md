# GitBashSDKMan
How to get SDKMan working on Git Bash on Windows 10

## Intro
I wanted to install [Leiningen](https://leiningen.org) on my Windows 10 workstation and knew from my Linux experiences that SDKMan was an easy way to install [Leiningen](https://leiningen.org) (and lots of other cool software).

If you don't know about SDKMan, check it out at [SDKMan Home Page](https://sdkman.io/).

## Instructions
### Install 'zip'
Believe it or not, Git Bash does *not* include a copy of command line *zip*. There is a copy of *unzip*, but **no** *zip*. Go figure...

Download the GnuWin binary from this site:

    https://sourceforge.net/projects/gnuwin32/files/zip/3.0/

and unzip it. I downloaded **zip-3.0-bin.zip**. It will be the full source and binary directories (i.e., bin, contrib, man & manifest) that are unzipped.

Copy just the **'zip.exe'** file from the 'bin' directory from zip-3.0-bin.zip to **/c/Program\ Files/Git/usr/bin/**.

Voila!

### Run Install Script
**NOW** you can run the install script:
```bash
curl -s "https://get.sdkman.io" | bash
```

Try it out. Worked for me.
