# IceWm-Setup
This contains my IceWM 1.4.2 configuration files. 
I have installed IceWM on Manjaroa XFCE. You can install Icewm on any distribution by building the source. I have followd the method given in the "Linux from scratch" web site. It is straigh forward and easy. I have copied it below-

IceWM Dependencies:
 1. X Window System 
 2. gdk-pixbuf-2.36.11 
 
 Download tha tar ball from  https://github.com/bbidulock/icewm/releases/download/1.4.2/icewm-1.4.2.tar.bz2
 
 Type the following commands in terminal
 
./configure --prefix=/usr                     \
            --sysconfdir=/etc                 \
            --docdir=/usr/share/doc/icewm-1.4.2 && make

Now as root user 
make install &&  rm /usr/share/xsessions/icewm.desktop

If IceWM is the only Window Manager you want to use, you can start it with an .xinitrc file in your home folder. Be sure to backup your current .xinitrc before proceeding.

echo icewm-session > ~/.xinitrc

The copy the default configuration files to /home/user/.icewm ( I have uploaded mine in this)
mkdir -v ~/.icewm                                       &&
cp -v /usr/share/icewm/keys ~/.icewm/keys               &&
cp -v /usr/share/icewm/menu ~/.icewm/menu               &&
cp -v /usr/share/icewm/preferences ~/.icewm/preferences &&
cp -v /usr/share/icewm/toolbar ~/.icewm/toolbar         &&
cp -v /usr/share/icewm/winoptions ~/.icewm/winoptions

Create a stratu file and add the required programs

Dont forget to run chmod +x /home/user/.icewm/startup

Recommeded additional softwares
1.Xfce4-power Manger ( Add in startup) --Power management
2. nm-applet -networkstatus indicator
3.Idesk (Configuration file is added with this) --desktop icons
4.sakura (conf file added) -minimal terminal
5.Volwheel

I have added Xsession file for better font rendering on laptop which can be used for any desktop environement. After update run
xrdb merge /home/user/.Xsession 

Some Java applications on Icewm may not give best font renedering. So I have uploaded an environment file which will correct font render. For more refer Arch wiki on Java. Add the content of the environment file to /etc/environment. 
