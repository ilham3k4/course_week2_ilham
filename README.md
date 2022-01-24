# Summary of Complete Intro to Linux and CLI
Summary of Complete intro to Linux and CLI by Brian Holt. The goal of this class :
- Participant would end up comfortable with the command line and Linux
- Participant will learn a bunch of tips and tricks as well as learn additional depth on things they already knew

# Linux
### UNIX
Linux is considered a Unix-like operating system which basically means that Linux derives heavy inspiration from Unix without actually conforming to be a full Unix operating system. macOS and FreeBSD would be two more examples of a Unix-like operating system.

![GitHub Light](https://btholt.github.io/complete-intro-to-linux-and-the-cli/static/17bba82d8a4f4795b3c8f7283a0a15ea/c2d13/linux_timeline.png)
### Linux
Linux isn't directly Unix, just directly inspired by it, and incorporates many of its ideas and interfaces into it. It was created in 1991 by Linus Torvalds who is still an influential figure today and still runs the Linux project. He created Linux because at the time there was no single free, open-source reimplementation of the Unix operating system (the BSD kernel wasn't yet available yet) so he wrote his own kernel which became known as the Linux kernel.
### Why Linux
1. it's free.
2. It's very well maintained.
3. It runs just about anywhere.
4. Most of the the things you need already exist for it.
5. The knowledgebase for Linux is enormous.
# The CLI
### Anatomy of a CLI Command
CLI is often called a REPL, a Read Evaluate Print Loop. It's basically an interactive way of programming where you're writing one line of code at a time, feeding data in and out of little programs. Using commands here, you can navigate around you computer, read and write data, make network calls, and all sorts of other stuff. Basically most anything you can do with a desktop you can do with a command line, just a little less obvious how to do it.

The way a REPL works is that you send one command at a time and the shell runs the command and returns to you a result. During the course of running that one command, it may print some things out. And you can, using some rudimentary programming syntax, write a line that runs multiple times (or, another way of saying "runs multiple times" is looping.) That's it! That's whole concept of what we're going to learning today.
### Shells and Emulators
a shell is almost certainly called bash (Bourne Again Shell), It's by far the most common shell and is over 30 years old. the most common of which are zsh, ash, PowerShell, and cmd.exe.
### File System
The way bash works is that you are always in a folder somewhere on your computer. 

Our first command we're going to run in your computer is `pwd`. So type `pwd` and hit enter. This will send the command `pwd` to the shell which will evaluate that and print out the answer.

`pwd` is a little program that tells you the current path of where you are in the file system. `pwd` stands for present working directory. It's basically like asking the computer "where am I right now?". The `/` represents a level of nesting inside of another folder. The root directory is at `/`. For most programs, you can try `pwd --help` and it'll usually spit out some brief instructions of how to use the program.
### Arguments / Parameters
In the case of `cd`, we're passing data into `cd` to tell it how to run. If we run `cd ..`, the `..` is an argument or parameter. Not all programs need parameters or sometimes they're optional. Let's look at `pwd`: it never needs any arguments. Or `ls` which has optional arguments. If you say `ls`, it's the same as saying `ls ..` The `.` in this case means "this directory". `which` will tell you the path to where the program you're running is. Arguments are just bits of information you give to a program, frequently they're paths to files or folders but they can often be other things.
### Flags
`--help` which is a flag but this commands can take all sorts of flags to customize how they'll act. Like parameters, they're bits of information that change how the command works. Many programs allow you to be lazy and combine flags together. In this case, we can say `ls -la` and that's the same as `ls -a -l` (order doesn't matter either.) This is usually true but it depends on the individual command you're running.

You can pass parameters to flag too. If we type `ls --ignore snap` it will not output snap. This can also be written as `ls --ignore=snap` to make it clearer what that ignore is referring to. We can also say `ls -I snap` for the shorthand. Lastly if we wanted to do an ls on the `/home` directory and not show the ubuntu folder, we could type `ls --ignore ubuntu /home`. In this particular case, the order is important. Immediately after ignore, the part you're trying to ignore is passed, then the last parameters to `ls` as a whole is passed. This is why some people like that equals. `ls --ignore=ubuntu /home` is very clear.
# Editors
### nano
nano is an old open source text editor that itself was an evolution from a previous text editor called pico. Pico was the text editor of the command-line email client Pine that people grew to love so much that they used it for everything. Because Pine was licensed in such a way that Debian wouldn't include it with its distro, Chris Allegretta re-implemented under the name TIP (Tip Isn't Pico, computer scientists love recursive acronyms) it eventually was renamed to nano.

Due its tiny size, light weight, and permissive license, nano is included on just about every Linux/Unix-like OS and is frequently the default text editor, even on tiny little embedded devices where even vim is too much. As such, it's a good tool to have your tool belt if you need to do some light text editing.
![GitHub Light](https://btholt.github.io/complete-intro-to-linux-and-the-cli/static/7c2c5569f855f6137bba414f9577cd48/afa26/nano.png)
### vim
The genesis of the ideas that went into vim started with an editor called ed (said ee-dee) which itself was inspired by a previous editor called qed. ed was developed by Ken Thompson at Bell Labs in 1969. It is a line-oriented editor and I have no clue how to use it. It's actually rather well known for being pretty user unfriendly. In spite of this, it's still available on most Unix-like systems including Ubuntu and macOS. If you do start it, just know it's CTRL+D a few times to quit it. It's important to note that ed was created in a time where memory was precious, screens were tiny and sometimes just one line at a time, and modems were measured in bits, not even kilobits. It arose at a time when it fit its constraints.

vim has multiple modes you can put the editor into. By default we are in command mode. So if you start typing, nothing will appear and you may actually accidentally trigger some commands. If you want to kick the editor into insert mode, just hit `i`. You should see `-- INSERT --` at the bottom to let you know you can type now. I'm going to put `vim test`. at the bottom of the file. Once I'm done writing and want to head back to command mode, you can hit Esc. You'll see the `-- INSERT --` disappear.

vim has an absolute myriad of commands and I'm not going to get into it. A good example is that here in command mode, you can use H to move the cursor left, j goes down, k goes up, and l goes right (the arrow keys work too but vim masters try to not take their fingers off the home row keys.) If I highlight a character and hit x, it'll delete that character. If I move my cursor to a line and type `:d` it'll delete the whole line. If I type `:d3` it'll delete three lines. There are so, so many and you just have to learn them.

If you do desire to go in-depth on vim, you can do one of two things. One is to type `:help tutor` from the command mode and it'll start the tutor. A more fun way is vim adventures which is a fun game to learn the keys.
![GitHub Light](https://s.yimg.com/uu/api/res/1.2/FHOZT3ho7HV7HJiqnOO85w--~B/Zmk9ZmlsbDtoPTQ0MTt3PTY3NTthcHBpZD15dGFjaHlvbg--/https://s.yimg.com/uu/api/res/1.2/BFH48vOvKgtQpO7v.IDCSA--~B/aD0zOTI7dz02MDA7YXBwaWQ9eXRhY2h5b24-/https://www.blogcdn.com/www.engadget.com/media/2012/06/vimtitle.jpg.cf.webp)

# Files, Pipes, and Permissions
