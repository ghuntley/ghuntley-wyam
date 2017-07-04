---
Title: pbcopy & pbpaste released for Windows
Published: 2016/01/20
Tags:
  - osx
  - windows
  - console
  - clipboard
  - pasteboard
  - pbcopy
  - pbpaste
---

Your favourite OSX command line clipboard manipulation libraries pbcopy and pbpaste were ported over to Windows last night. They are two console applications that pipe the clipboard into/out of STDIN/STDOUT

* pbcopy copies the standard input and places it in the clipboard.
* pbpaste copies the data from the clipboard and writes it to the standard output.

## Installation

Installation is done via [Chocolatey](https://chocolatey.org/packages/pasteboard):

```shell
cinst pasteboard
```

## Usage

To copy your SSH key to the clipboard:

```shell
cd .ssh
type id_rsa.pub | pbcopy
```

To write the contents of your clipboard to a file:

```shell
cd C:\tmp
pbpaste > output.txt
```
