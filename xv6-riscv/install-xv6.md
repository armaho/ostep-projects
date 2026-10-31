<!--toc:start-->
- [Install Notes](#install-notes)
  - [The xv6 Source Code](#the-xv6-source-code)
  - [Tools](#tools)
    - [QEMU](#qemu)
    - [RISC-V compiler toolchain](#risc-v-compiler-toolchain)
  - [Building xv6](#building-xv6)
<!--toc:end-->

# Install Notes

To get xv6 up and running on your machine, you'll need a few tools
installed. Here, we'll walk you through what you need to do.

## The xv6 Source Code

To obtain the xv6 source code, just clone it from GitHub:

```sh
prompt> git clone https://github.com/mit-pdos/xv6-riscv.git
Cloning into 'xv6-riscv'...
remote: Enumerating objects: 8375, done.
remote: Counting objects: 100% (73/73), done.
remote: Compressing objects: 100% (46/46), done.
remote: Total 8375 (delta 45), reused 27 (delta 27), pack-reused 8302 (from 3)
Receiving objects: 100% (8375/8375), 17.70 MiB | 5.65 MiB/s, done.
Resolving deltas: 100% (4609/4609), done.
```

There! You've now completed the easiest part.

## Tools

Install the necessary tools by following
[this guide](https://pdos.csail.mit.edu/6.828/2026/tools.html). Note that you
don't have to install Athena.

Here's the role each of these tools plays in your workflow as a kernel hacker:

### QEMU

The first piece of software you need to play around with xv6 is the
[`qemu`](https://www.qemu.org/) machine emulation environment.

To learn more about what emulation is, read [this
page](https://en.wikipedia.org/wiki/Emulator). The short story is that an
emulator is just another computer program, but one that is a realistic
facsimile of a particular computer system. In this case, we'll use `qemu` to
pretend we are running a RISC-V computer system; on this pretend RISC-V system,
we'll boot our xv6 kernel.

Now you might ask: why not just run xv6 on a real machine? First of all, how
would you even get a RISC-V machine?! And besides that, running xv6 natively
would make running and debugging xv6 slower and more painful. With a realistic
emulator like `qemu`, you can run your kernel quickly without the pain of
rebooting the actual system you are using. Further, if you make a mistake, your
entire machine doesn't lock up; only the emulator does, and you can exit or
kill it. It just makes your life much easier than doing the real thing.

### RISC-V compiler toolchain

The compiler on your computer can translate code for your own machine's
architecture. Unless you're coding on a RISC-V machine (which you're probably
not), that's not what we want. We want our code to be compiled for a RISC-V
machine, which is the one QEMU is simulating. That's where we need a
cross-compiler.

To read more about cross-compilers and why we need them, see
[this page](https://wiki.osdev.org/GCC_Cross-Compiler#Introduction).

## Building xv6

Go to the directory in which you've cloned xv6:

```sh
prompt> cd xv6-riscv
```

Hopefully, with all the necessary tools installed, you should be able to build
xv6 easily. Just run `make qemu`:

```sh
prompt> make qemu
```

You should now see a bunch of logs appearing, and when the compiler is done,
you should be greeted by a `$` staring at you:

```
xv6 kernel is booting

hart 2 starting
hart 1 starting
init: starting sh
$
```

This is xv6's shell waiting for your command. You've done it! Run `ls` in xv6
to see this OS in action:

```sh
$ ls
.              1 1 1024
..             1 1 1024
README         2 2 2441
cat            2 3 38176
echo           2 4 36960
forktest       2 5 18256
grep           2 6 41720
init           2 7 37344
kill           2 8 36888
ln             2 9 36680
ls             2 10 40304
mkdir          2 11 36944
rm             2 12 36936
sh             2 13 60888
stressfs       2 14 37792
usertests      2 15 209600
grind          2 16 53432
wc             2 17 39208
zombie         2 18 36208
logstress      2 19 38960
forphan        2 20 37712
dorphan        2 21 37160
sync           2 22 36304
console        3 23 0
```

Now it's time to go do the projects!
