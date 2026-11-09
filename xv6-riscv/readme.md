<!--toc:start-->
- [What's this?](#whats-this)
- [Where to start?](#where-to-start)
- [Resources](#resources)
<!--toc:end-->

# What's this?

Xv6 is an educational operating system maintained by MIT. The first version of
this OS was made for the x86 architecture. After a while, the team decided to
deprecate that version in favor of a newer one made for the RISC-V architecture
instead.

Projects in this directory are modified versions of their x86 counterparts,
rewritten with the RISC-V version in mind.

# Where to start?

The first thing you need to know is a bit of RISC-V assembly. Without this
knowledge, these projects will feel completely perplexing. I strongly suggest
going through [this great tutorial](https://easyriscv.dram.page/#memory) by
dramforever, since it covers basically everything you need to get started with
something like RISC-V.

Then you can start by reading through the
[installation guide](/xv6-riscv/install-xv6.md). Once you're done with that
part, go through the projects one by one. Here's a list of the available
projects for xv6-riscv:

Wish you luck in your kernel hacking journey!

# Resources

Whenever you need to go deeper on something RISC-V related, turn to the
[official documents](https://docs.riscv.org/reference/home/). Use the
*Unprivileged ISA* document for unprivileged instructions and the
*Privileged ISA* document for privileged ones. Since xv6 is an operating
system, it does use some privileged instructions, but not so many that it
becomes overwhelming.

To learn more about xv6 itself and its architecture, you're welcome to read
[the official book](https://mit-pdos.github.io/xv6-riscv-book/) online. It's
a great way to go down the rabbit hole of this operating system, and I highly
encourage you to give it a chance!
