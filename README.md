# SAC

This is a repository where you can download binary distributions of the
SAC/BRIS (also known as Mac SAC) for computers running MacOS.  If you are
not running MacOS, you need to compile SAC yourself by installing it from
source.  An automated script to do this can be found
[here](https://members.elsi.jp/~george/dobuild.sh); this is a shell script
that downloads, patches and compiles the source code based on educated guesses
about your system.

SAC/BRIS is based on the 10.6d source code, updated to equivalent functionality
as 10.6f, and extended from there.  It is compatible with IRIS's SAC (except
for any bugs) but does not contain IRIS's recent extensions to query metadata
via SAC and download data.  (These features will be added in a future release.)
SAC/BRIS is documented in the book, *The Seismic Analysis Code* (Cambridge
University Press).

# Downloading

Downloads are in the form of a MacOS disk image (folder) that you can mount
and look inside of.  Generally, you will find an MacOS package to install and
a separate uninstall app.  The `pkgutil --pkgs` command on MacOS will list the 
packages that you have installed.  SAC is called, `uk.ac.bris.gly.sac`.  The
uninstall app will uninstall SAC and, optionally, all record of having ever
had it installed.  After you install, you can close and throw away the disk
image.  You can download it again later to get the uninstall app if you decide
to get rid of SAC.

MacOS has evolved through the years through different releases (Panther,
Tiger, Leopard, ..., Big Sur, Monterey) and on different hardware
(Motorola, PowerPC 32 and 64 bit, Intel 32 and 64 bit, and Apple (ARM)).
Your download choice depends on the OS release and hardware you're running
on, which, if you're unfamiliar with it, you can get from the `About this Mac`
Apple menu item, and from the `uname -a` command.

## Versions and Options

There are also some features that you might or might not want.  The main choice
you have is whether you prefer to use X graphics or native Mac graphics.  If
you want to have an pure Mac system, you can opt out of needing to install X and
download the *no X* variant.

SAC implicitly has parallel processing built into it.  For example, if you
want to filter data, then the filtering command acts on all traces in SAC
memory simultaneously.  Internally, SAC will take advantage of any multiple 
CPUs on your machine to handle the processing for each trace, speeding up the
processing.  If you *don't* want to have SAC monopolize all the processing
power of your system, don't download a version marked *parallel*.

Not all choices are available for all OS/hardware combinations.  If you
crave one, we can build one to suit *provided* we have a system with that
OS/hardware combination.  Otherwise, build it yourself from source.

## Contemporary versions

| SAC/BRIS Release | 11.6 | 10.6- | 10.5-10.4 |
| ---------------- | -----| ----- | --------- |
| [grh-116](https://members.elsi.jp/~george/sac-bugs.html#grh115) | M1 X+mac | | |
| | | | |
| [grh-115](https://members.elsi.jp/~george/sac-bugs.html#grh115) | | [Intel X+mac](https://members.elsi.jp/~george/MacSAC-grh115-10.9i.dmg) | |
| | | | |
| [grh-114](https://members.elsi.jp/~george/sac-bugs.html#grh114) | | [Intel X+mac](https://members.elsi.jp/~george/MacSAC-grh114-10.9i.dmg) | |
| | | | |
| [grh-113](https://members.elsi.jp/~george/sac-bugs.html#grh113) | | [Intel X+mac](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh113-10.9i.dmg) | |
| | | | |
| [grh-112](https://members.elsi.jp/~george/sac-bugs.html#grh112) | | [Intel X+mac](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh112-10.9i.dmg) | |
| | | | |
| [grh-111](https://members.elsi.jp/~george/sac-bugs.html#grh111) | | [Intel X+mac](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh111-10.9j.dmg) | |
| | | | |
| [grh-110](https://members.elsi.jp/~george/sac-bugs.html#grh110) | | | [Intel X+mac parallel](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh110-10.6jP.dmg) [Intel X+mac](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh110-10.6i.dmg) | [Intel X+mac](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh110-10.4i.dmg) [PPC   X+mac](http://www1.gly.bris.ac.uk/MacSAC/MacSAC-grh110-10.4p.dmg) |


### Glossary
* Intel - Intel hardware.
* X+mac - Support for both X11 graphics and native Mac graphics.
* mac - Support for native Mac graphics ONLY. This means that you do NOT have to have X11 installed on your Mac in order to run SAC.
* X - Support for X11 graphics only.
* parallel - Support for parallel trace operations with OpenMP; sequential
operations on traces, otherwise.  OpenMP support provided within the SAC
libraries and neither gfortran nor OpenMP need be installed on your computer --
at least that's the idea, so if OpenMP features don't work, report it as a bug!
