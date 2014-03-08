Q crop image
A convert -crop 40x30+40+30  original.png new.png

Q Set up elixir
A git clone <elixir repository>
A make clean test #compile all useful bin scripts

Q convert doc,xsl to txt
A catdoc http://www.wagner.pp.ru/~vitus/software/catdoc/
A http://tika.apache.org with API

Q Convert asciidoc to HTML 
A a2x -f xhtml -D out <asciidoc file>

Q Extract part of video
A avconv -ss 00:32:15 -t 00:00:48 -i long-video.mp4 -codec copy funny-clip.mp4

Q xfce4 loses title bars, workspace , how to fix it ?
A run xfwm4 from a terminal

Q add pacakge from new apt repository
A sudo add-apt-repository ppa:igraph/ppa
A sudo apt-get update

Q mutt for gmail 
A http://lifehacker.com/5574557/how-to-use-the-fast-and-powerful-mutt-email-client-with-gmail
A http://www.jlime.com/wiki/documentation/user/general/howtos/gmail_mutt 
A http://www.techrepublic.com/blog/opensource/my-number-one-reason-to-use-mutt-managing-multiple-profiles/3113
A http://shreevatsa.wordpress.com/2007/07/31/using-gmail-with-mutt-the-minimal-way/

Q mutt shortcuts
A m : compose message
A Control-t : auto-complete email  http://bouliiii.blogspot.it/2012/02/mutt-and-auto-complete.html
A http://sheet.shiar.nl/mutt

Q pretty-print JSON
A cat <some json> | python -m json.tool

Q How to get desktop resolution ? 
A xwininfo -root | grep -A1 Width 

Q Sound troubleshooting
A https://help.ubuntu.com/community/SoundTroubleshootingProcedure

Q screenshot with ImageMagick 
A import -window root -resize 500 AnotherScreenshot.png

Q photo collage with ImageMagick
A montage x{y,y1,y2,y3}.jpg -border 5 -bordercolor darkyellow -geometry +2+2 collage.jpg

Q Upper case all vowels of a file
A sed 'y/aeiou/AEIOU/' <somefile>

T :Sex will open a file explorer in a split window

Q Install netflix ?
A http://www.jeremymorgan.com/tutorials/linux/how-to-netflix-ubuntu-linux/

Q extract specific format with youtube-dl ?
A youtube-dl -F <url> ;list all format
A youtube-dl -f 17 <url> ; download format 17
S http://gerard.geekandfree.org/blog/2012/12/03/youtube-dl-ou-lalternative-au-plugin-flash-pour-telecharger-/

Q extract audio of youtube-dl
A youtube-dl -t --extract-audio --format-audio

Q list largest ubuntu packages
A sed -ne '/^Package: \(.*\)/{s//\1/;h;};/^Installed-Size: \(.*\)/{s//\1/;G;s/\n/ /;p;}' /var/lib/dpkg/status | sort -rn | head
A dpkg-query -Wf '${Installed-Size}\t${Package}\t${Section}\n' | sort -rn

Q rotate image
A convert -rotate 90 orig.jpg new.jpg
A rotation clockwise

Q how to reconfigure package
A sudo dpkg-reconfigure resolvconf

Q How to set up wifi manually
A nmcli nm wifi on
A nmcli nm status

Q how to manually access wifi network ?
A ifup wlan0
A iwlist wlan0 scan
A iwconfig wlan0 mode managed
A iwconfig wlan0 channel 11
A iwconfig wlan0 essid networkname

Q list running services
A  initctl list

Q run update package manager
A update-manager

Q tmux shortcuts
A all key binding : ^b ?
A split pane horizontally /vertically : ^b " / ^b %
A change pane : ^b o
A create window : ^b c
A change window . ^b n / ^b p



Q How to save text into clipboard from command line ?
A head bishop/README.md | xclip -sel clip
A uptime | xclip  : X selection
A xclip -o >textfile.txt

Q clean up disk
A sudo apt-get autoclean
A sudo apt-get clean
A sudo apt-get autoremove
A sudo apt-get remove --purge linux-image-X.X.XX-XX-generic

Q List all debian packages installed
A dpkg --get-selections

Q List files of debian package
A dpkg -L <package name>

Q Mount USB drive
A sudo mount -t vfat /dev/sdb1 /media/external -o uid=1000,gid=1000,utf8,dmask=027,fmask=137

Q Check Ubuntu version
A cat /etc/issue
A cat /etc/lsb-release (more details)
A lsb_release -a

Q Check linux kernel version
A  uname -a

Q How to loop for each word of variable ?
A args="java haskell"
A for i in `echo $args`
A do
A   echo "---> "$i
A done
T bash

Q How to test if variable not empty ?
A if [ -n "$VAR" ]; then
T bash
