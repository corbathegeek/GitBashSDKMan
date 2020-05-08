# GitBashSDKMan
How to get SDKMan working on Git Bash

## Intro
I wanted to install [Leiningen](https://leiningen.org) on my Windoze 10 workstation and knew from my Linux experiences that SDKMan was an easy way to install [Leiningen](https://leiningen.org) (and lots of other cool software).

If you don't know about SDKMan, check it out at [SDKMan Home Page](https://sdkman.io/).

## Instructions
### Install 'zip'
Believe it or not, Git Bash does *not* include a copy of command line *zip*. There is a copy of *unzip*, but **no** *zip*. Go figure...

Download the GnuWin binary from this site:

    https://sourceforge.net/projects/gnuwin32/files/zip/3.0/

and unzip it. I downloaded **zip-3.0-bin.zip**. It will be the full source and binary directories (i.e., bin, contrib, man & manifest) that are unzipped.

Copy just the **'zip.exe'** file from the 'bin' directory from zip-3.0-bin.zip to **/c/Program\ Files/Git/usr/bin/**.

Voila!

### Modify the Install Script
**Spoiler alert:** As written, the install script:
```bash
curl -s "https://get.sdkman.io" | bash
```
won't work under Git Bash. The problem is that ${HOME} is /home/userID under Git Bash. You have to change it to a $HOME that makes sense under Git Bash.  Specifically, you're going to have to do a global replace:
```shell
${HOME}/ --> /c/Users/yourID/
```
So, to do that, let's download a copy of the script:
```bash
curl -s "https://get.sdkman.io" > ~/bin/installSDKMan.sh
```
change the script to executable
```bash
chmod +x ~/bin/installSDKMan.sh
```
And do the global replace using your favorite editor.

## Modify the sdkman-init.sh Script

Now do the same $HOME modifications to the .sdkman/bin/sdkman-init.sh script.

## Now, Run the Install Script

Try it out. Worked for me.

