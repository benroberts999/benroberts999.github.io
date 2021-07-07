---
usemathjax: true
layout: post
title: "Ubuntu (bash) on Windows 10"
permalink: /posts/ubuntuonwindows
comments: true
---

You can now run ubuntu bash straight from windows 10. For many, this may be a better option that trying to dual boot or run a full virtual machine. It's command-line only (though it does allow screen-forwarding), and gives reasonably full linux functionality without the resource-hog of a full virtual machine, and without the pain or hassle of dual booting.
This post just has a couple of extra steps/tips that helped me make this a much more usable feature.

It only works on 64 bit OS Windows 10, build 14393.0 or newer (you can check this in Settings). If you run any version of 64 bit Windows 10, you should at least be able to update to the required newer versions.
If you run 32-bit Win10 but have an x64 architecture (not x86, again, you can check this in Settings), then you can upgrade to 64-bit Win10, but it requires a full re-installation of the OS (see here).

If your pc is compatible, bash can be installed with these basic steps:

 1. Turn-on "Developer Mode" (Settings> Update & Security > For developers > Developer Mode). Windows will now download some updates, wait for it to finish. You may then need to restart the computer.

 2. Enable the Windows Subsystem for Linux feature (Turn Windows features on or off > Windows Subsystem for Linux (beta)). Restart the pc.

 3. Open cmd prompt and type: `bash`. Follow the prompts to download and install ubuntu bash

 4. Run bash from the start menu shortcut. The first time you do this follow the prompts to create a new user account. And then you're done.

The official site and installation guide can be found here: <https://msdn.microsoft.com/commandline/wsl/about>

The Windows Subsystem for Linux is still a beta*, and they warn that many things may not work, however, everything I can think of for normal applications seem to work perfectly well, including:

 * install and use git without any issues

* compile c, c++, fortran, python etc. including external libraries

* use apt-get to install/manage programs and update the system

* share files between windows/ubuntu (see below)

* ssh into remote servers

* even use graphical programs with screen forwarding (see below)

**edit** As of August 2017, no longer beta! (see here)

For an updated post, including info on compiling and running c++ from windows, see:
 * <{{ site.baseurl }}/posts/2018/11/wsl-coding-windows-ubuntu>

### Turn off that **beep**ing bell!

Because whoever designed this is a beeping sadist, it comes with an in-built "everything's OK" alarm, and beeps at you every time you do anything.

1) Turn off bell for terminal. Edit the inputrc file:
`$ sudo vim /etc/inputrc`
and add the following line:
`set bell-style none`

2) Even after that, vim still beeps every time you press 'esc'... yeah..

To fix this, edit the hidden vimrc file (which may not already exist):
  `$ vim ~/.vimrc`
and add the following line:
  `set visualbell`
credit to palmsugar, to whom I now owe my sanity: https://redd.it/4vz3sr


### Display forwarding (using GUI programs):

It doesn't seem like it's technically supported, but you can actually use display forwarding to let you use graphical interface for certain programs.

To do this, you need an X server that runs on windows, the common choice is Xming:
https://sourceforge.net/projects/xming/
Once downloaded, run the Xming .exe, you should see the icon in the task bar. This is the same as if you were diplay forwarding using ssh (with putty, for example). That's all we need from the windows side.


Now, we need to tell bash to forward graphical display with the command:
  `$ export DISPLAY=:0`
and that's it, it should work now.

This might be useful if don't like using vim. For example, you can instead install and use a 'normal' text editor like gedit:
  ```
  $ sudo apt-get install gedit
  $ gedit &
  ```
which essentially works as per normal (the optional '&' symbol lets gedit run in the background). You'll see a lot of error messages in the terminal window, but it seems everything works fine. All the error messages are a little annoying, so I usually use a separate terminal window for opening gedit (or whatever), in which case everything works perfectly, and looks nice too.

Also, you can view pdf files (using, e.g., evince: $ sudo apt-get install evince)


As another example, we can use the plotting program gnuplot. Note, you have to have gnuplot-x11 installed, not just the standard gnuplot:
  `$ sudo apt-get install gnuplot-x11`

After installing, start gnuplot and try plotting sin(x):
```
  $ gnuplot
  gnuplot> plot sin(x)
```
Official gnuplot page: http://www.gnuplot.info/ however, you'll probably have more luck finding working examples on forums by googling specific questions.

### File sharing

You can access all your windows files directly from bash, located in /mnt/c/ (if your windows drive is called c). Be very careful here.. all the windows files are visible. I don't know if rm -rf will work here or not, but I'm not going to test it.

It's probably a better idea to create a sharing folder. For example, you might create a folder called "BashWindowsShare" on your windows desktop, and the create a symbolic link to it in your ubuntu home directory:
```
  $ ln -s /mnt/c/Users/WinUSERNAME/Desktop/BashWindowsShare/ ./
```
You can now easily/safely share files between ubuntu and windows. Note, that copying into/out of symbolic links is a little strange. It works best if you use "rsync -K" instead of "cp", and do this from outside of the symlink, since the relative drive paths seem to be relative to windows when you do this from inside the symlink. Also, it works better if you only use this for sharing (i.e., don't edit files inside the drive), since the file permissions are a little strange. Generally, the best option is instead to use a service like git/gitHub.

You can also access the all ubuntu files directly from within windows, they are located in the (hidden) \AppData\Local\lxss\ directory:
```
  C:\Users\WinUSERNAME\AppData\Local\lxss\home\UbUSERNAME
```
where WinUSERNAME is your windows username, and UbUSERNAME is your ubuntu username. Obviously, don't mess with the other files in the \lxss\ directory if you don't want to break things.
Note: this is actually listed as a "not supported" feature, which means it is not particularly safe. I'd avoid doing this as much as possible. Note: you can always use external sharing tools via the web, which is probably a better option in most cases (sftp works, you can use gitHub, probably dropBox works too etc.)

### Other funny/annoying 'features' and fixes:

Copy/paste First, make sure 'quick edit' is turned on (it is by default): right click on the task bar > properties/defaults > Edit Options > QuickEdit Mode.
To copy text from the terminal, just highlight it and right-click. To paste, just right click into the terminal window. Note: cntrl+c is the linux command for 'kill process' - if you're running a program and accidentally cntrl+c, you'll force the program to stop.

### "Unable to resolve host" error with sudo

 Whenever you run a command with sudo, it spits out an error saying "sudo: unable to resolve host". This doesn't seem to cause any problems, but takes an extra second or two, and is a little annoying. I found a solution here: http://iamnotmyself.com/2016/07/13/windows-subsystem-for-linux-error-unable-to-resolve-host-2/

Essentially, to fix it, you need to add a line to the /etc/hosts file corresponding to your hostname.
Check your hostname by calling:
```
  $ cat /etc/hostname
```
Your hostname is not your username, it is probably your windows PC name - in my case it is "BEN-XPS13WIN10", but will be different for you. Then, edit the following file
`  $ sudo vim /etc/hosts`

It should already have an entry: 127.0.0.1 localhost just below this, add the new entry 127.0.0.1 YOUR-HOSTNAME (replace 'YOUR-HOSTNAME' with that from the /etc/hostname file). Perhaps your address will be different from mine (127.0.0.1), you should make the hostname address match the existing one for localhost

### Strange directory highlighting

By default, new directories are shown with green background highlighting. The reason is that new directories are created with 'drwxrwxrwx' permissions, instead of the more usual 'drwxrwxr-x'. This isn't a big problem, but if it bugs you, you can change it back by typing
  `$ chmod 775 directoryName/`
where 'directoryName' is the name of the directory you want to change.
(See, e.g., http://www.elated.com/articles/understanding-permissions/)
