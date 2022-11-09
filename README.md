# med

This project is motivated by the desire for a simpler way to create and edit text files from the command line.

The name `med` is a reference to [ed](https://en.wikipedia.org/wiki/Ed_(text_editor)), the classic UNIX editor, but with full cursor movement like in [vi](https://en.wikipedia.org/wiki/Vi).

I want a text editor that is "invisible", that is, it appears as if there is no program at all, that is simply invoked and, whatever you type is your file, similar to typing `cat > file.txt`, but with the ability to move the cursor around and edit multiline files.

I'm considering writing it 3 different ways:

1. Using the [Ncurses](https://en.wikipedia.org/wiki/Ncurses) library like Vim uses. Probably the most reasonable choice.

2. In pure C, by emitting VT100 escape codes like the [kilo editor](https://github.com/antirez/kilo). Since I'm already quite familiar with the code it may be easier for me than learning curses. It's also pretty cool that it doesn't use any external libraries.

3. Doing it all in Bash with `tput`. Seems ridiculous, but may actually be the most simple way and fits the use case rather well... since the whole point is to look like you're never leaving your Bash workflow, might as well not ever leave it!

## Coming back to this 4 years later:

The answer is none of the above. Use [JLine](https://github.com/jline/jline3), like [Rebel Readline](https://github.com/bhauman/rebel-readline/). It's probably the only practical way to make it work across platforms. 4 years ago I didn't care about that, but Microsoft actually seems to be playing very nicely so Windows has become almost usable!

But the even more practical reason is so we can build upon all of Bruce's amazing work.
