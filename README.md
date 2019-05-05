# med

This project is motivated by the desire for a simpler way to create and edit text files from the command line.

The name `med` is a reference to [ed](https://en.wikipedia.org/wiki/Ed_(text_editor)), the classic UNIX editor, but with full cursor movement like in [vi](https://en.wikipedia.org/wiki/Vi).

I want a text editor that is "invisible", that is, it appears as if there is no program at all, that is simply invoked and, whatever you type is your file, similar to typing `cat > file.txt`, but with the ability to move the cursor around and edit multiline files.

I'm considering writing it 3 different ways:

1. Using the [Ncurses](https://en.wikipedia.org/wiki/Ncurses) library like Vim uses. Probably the most reasonable choice.

2. In pure C, by emitting VT100 escape codes like the [kilo editor](https://github.com/antirez/kilo). Since I'm already quite familiar with the code it may be easier for me than learning curses. It's also pretty cool that it doesn't use any external libraries.

3. Doing it all in Bash with `tput`. Seems ridiculous, but may actually be the most simple way.