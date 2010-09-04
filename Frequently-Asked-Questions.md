## What is a terminal emulator?

A terminal emulator is a program that makes your Android phone act like an old fashioned computer terminal. It is useful for accessing the Linux command line shell that is built into every Android phone. This lets you run various Linux command line utilities.

If you don't know what all that means, and why it's cool, then this probably isn't the program for you. (Sorry!)

## What sort of games does this emulator play?
Sorry, this is a terminal emulator, not a game emulator. It has nothing to do with games.

## Why does the Android Terminal Emulator request Internet and SD Card write permissions?
By itself, the Android Terminal Emulator doesn't access the Internet or write to the SD Card. However, many users of Android Terminal Emulator want to run command line programs, such as "ssh" or "cp" that need to access the Internet and/or write to the sd card.

The way Linux (and therefore Android) works, a child process inherits the permissions of the parent. Android Terminal Emulator requests the Internet and SD Card write permissions so that the command-line programs that it runs can have access to the Internet and can write to the SD Card.

If giving these permissions to the terminal emulator makes you uncomfortable, you could always download the source code and compile your own version. (Edit the AndroidManifest?.xml file to remove the INTERNET and WRITE_EXTERNAL_STORAGE permissions.)

## Why don't the Arrow Keys / DPAD / Trackball work ?
They do work, sort of. They send the proper escape sequences for VT-100 terminal arrow keys. What's missing is that the default Android shell does not recognize these escape sequences. I've fixed this in the Android source code, so future, post-2.2 versions of Android will work correctly. But that doesn't help people with current versions of Android.

In the meantime, if you wish, you could install an alternate shell, such as the one in Busybox, which recognizes the arrow escape sequences sent by the terminal emulator.

## Why don't you include a telnet or ssh client?
That's a good question! I guess I really ought to. Maybe one of these days I'll get around to it. In the meantime, you can install Busybox, which comes with both a telnet client and a ssh client.

## Could you make tab completion work?
Similar to the "Arrow Keys" question above, Linux tab completion is the job of the shell, not the terminal emulator. The built-in Android shell application does not provide tab completion. You can turn on tab completion by installing an alternate shell, such as the one that comes with Busybox.

## What is Busybox?
Busybox is a collection of Linux utility programs that is designed to be run on small Linux devices, such as your Android phone.

## Where can I get Busybox for my Android Phone?
Do a web search for "Android Busybox" and read through the results.

## Do I need root access to install and use Busybox?
I don't know. Certainly all the guides on the web seem to assume that you need root access.

However, it seems to me that it should be possible to install Busybox without root access if you installed it into the /data/local/bin directory. But I don't have any non-developer phones, so I haven't been able to check if this works with ordinary, non-developer phones.