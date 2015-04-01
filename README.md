rop-tool v2.0
====

A tool to help you writing binary exploits


### OPTIONS

```
rop-tool v2.0
Help you to make binary exploits.

Usage: rop-tool <cmd> [OPTIONS]

Commands :
   gadget      Search gadgets
   search      Search on binary
   help        Print help
   version     Print version

Try "rop-tool help <cmd>" for more informations about a command.

```

#### GADGET COMMAND

```
Usage : rop-tool gadget [OPTIONS] [FILENAME]

OPTIONS:
  --arch, -A               Select an architecture (in raw mode only)
  --all, -a                Print all gadgets
  --bad, -B           [b]  Specify bad chars in address
  --depth, -d         [d]  Specify the depth for gadget searching (default is 5)
  --flavor, -f        [f]  Select a flavor (att or intel)
  --help, -h               Print this help message
  --no-color, -n           Don't colorize output
  --raw, -r                Open file in raw mode (don't considere any file format)
```

#### SEARCH COMMAND

```
Usage : rop-tool search [OPTIONS] [FILENAME]

OPTIONS:
  --all-string, -a    [n]  Search all printable strings of at least [n] caracteres. (default is 6)
  --byte, -b          [b]  Search the byte [b] in binary
  --bad, -B           [b]  Specify bad chars in address
  --dword, -d         [d]  Search the dword [d] in binary
  --help, -h               Print this help message
  --no-color, -n           Don't colorize output
  --qword, -q         [q]  Search the qword [q] in binary
  --raw, -r                Open file in raw mode (don't considere any file format)
  --split-string, -s  [s]  Search a string "splited" in memory (which is not contiguous in memory)
  --string, -S        [s]  Search a string (a byte sequence) in binary
  --word, -w          [w]  Search the word [w] in binary
```


### FEATURES
* String searching, Gadget searching
* Colored output
* Intel and AT&T flavor
* Support of ELF and PE binary format
* Support of big and little endian
* Support of x86 and x86_64 architecture


### EXAMPLES

Basic gadget searching

* rop-tool g ./program 

Display all gadgets with AT&T syntax

* rop-tool g ./program -f att -a

Search in RAW file (not supported format)

* rop-tool g ./program -r

Search a "splitted" string in the binary

* rop-tool s ./program -s "/bin/sh"

Search all strings in binary

* rop-tool s ./program -a

### SCREENSHOTS

```
rop-tool gadget /bin/ls
```

![ScreenShot](https://t0x0sh.org/repo/rop-tool/screens/screen1.png)

```
rop-tool search /bin/ls -a
```

![ScreenShot](https://t0x0sh.org/repo/rop-tool/screens/screen2.png)

```
rop-tool search /bin/ls -s "/bin/sh\x00"
```

![ScreenShot](https://t0x0sh.org/repo/rop-tool/screens/screen3.png)

```
rop-tool search /bin/ls -w 0x90
```

![ScreenShot](https://t0x0sh.org/repo/rop-tool/screens/screen4.png)


### DEPENDENCIES
- [capstone](http://capstone-engine.org/)

### RELEASES
- https://t0x0sh.org/repo/rop-tool/releases/

### LICENSE
- GPLv3 license : http://www.gnu.org/licenses/gpl-3.0.txt

### AUTHOR
Tosh 

tosh -at- t0x0sh ~dot~ org

