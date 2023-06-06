# Emacs User Manual

## Table of Contents

- [Emacs User Manual](#emacs-user-manual)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Installation](#installation)
  - [Basic Concepts](#basic-concepts)
  - [Basic Commands](#basic-commands)
    - [Buffers and Windows](#buffers-and-windows)
    - [Search and Replace](#search-and-replace)
    - [Editing Modes](#editing-modes)
  - [Customizing Emacs](#customizing-emacs)
  - [Packages and Extensions](#packages-and-extensions)
  - [Tips and Tricks](#tips-and-tricks)
    - [Troubleshooting](#troubleshooting)
  - [Resources](#resources)

## Introduction

Emacs is a powerful and extensible text editor designed for efficient text editing.

It is available for many platforms, including Windows, Linux, macOS, and more.

Emacs offers numerous features and can be extended using the Emacs Lisp programming language.

## Installation

Depending on your operating system, follow the steps below to install Emacs:

|Distro|cmd|
|---|---:|
|**Linux (Debian-based distributions)** |  `sudo apt-get install emacs`|
|**Linux (Red Hat-based distributions)** |  `sudo yum install emacs`|
|**macOS (using Homebrew)** |  `brew install emacs`|
|**Windows** | [Download the installer] |

## Basic Concepts

Emacs operates primarily using keystrokes and commands. Some essential concepts include:

|Concept|Definition|
|---|---|
|**Commands** |  Functions that perform various operations|
|**Keybindings** |  Keyboard shortcuts associated with commands|
|**Buffers** |  Instances of files or data being edited|
|**Windows** |  Display areas for buffers|

## Basic Commands

|Command|Outcome|
|---|---|
|`Ctrl-x` + `Ctrl-f`| Open a file (Find file)|
|`Ctrl-x` + `Ctrl-s`| Save the current buffer (Save buffer)|
|`Ctrl-x` + `Ctrl-c`| Quit Emacs (Exit)|
|`Ctrl-g`| Cancel the current command|
|`Ctrl-x` + `u`| Undo last change (Undo)|

**NOTE** |  `Ctrl-x` means "*press the `Ctrl` key and the `x` key simultaneously*."

### Buffers and Windows

|Command|Outcome|
|---|---|
|`Ctrl-x` + `b`| Switch to a different buffer|
|`Ctrl-x` + `k`| Kill (close) the current buffer|
|`Ctrl-x` + `2`| Split the window horizontally|
|`Ctrl-x` + `3`| Split the window vertically|
|`Ctrl-x` + `1`| Close all windows except the current one|
|`Ctrl-x` + `o`| Move to the next window|

### Search and Replace

|Command|Outcome|
|---|---|
|`Ctrl-s` | Incremental search forward|
|`Ctrl-r` | Incremental search backward|
|`Ctrl-Alt-%` | Query replace (search and replace with prompting)|
|`Alt-x` **replace-string** | Replace all occurrences of a string without prompting|

**NOTE**: `Alt-x` means "*press the Meta (or `Alt`) key and the `x` key simultaneously*."

### Editing Modes

Emacs provides various modes for different file types and tasks.

1. Modes can be
   - **major** (one per buffer)
   - **minor** (multiple per buffer).

Some popular major modes include:

|Command|Outcome|
|---|---|
|`text-mode` |  Plain text editing|
|`prog-mode` |  Programming language editing|
|`org-mode` |  Notes, planning, and project management|

**NOTE**: To activate a specific mode, type `Alt-x` **mode-name** (e.g., `Alt-x` *org-mode*).

## Customizing Emacs

To customize Emacs, create an `init.el` file in your Emacs user directory (typically `~/.emacs.d/`). This file contains Emacs Lisp code that is executed when Emacs starts. Some common customizations include:

|Command|Outcome|
|---|---|
|**Set font size** | `(set-face-attribute 'default nil: height 120')`|
|**Enable line numbers** | `(global-display-line-numbers-mode 1)`|
|**Set default indentation width** | `(setq-default indent-tabs-mode nil)` `(setq-default tab-width 4)`|

## Packages and Extensions

Emacs supports packages and extensions to enhance its functionality. Emacs includes a built-in package manager, which can be accessed using `Alt-x list-packages`. To install a package, follow these steps:

1. Open the package list: `Alt-x` *list-packages*
2. Find the package you want to install
3. Press `i` to mark the package for installation
4. Press `x` to execute the installation
5. You can also add external package repositories to your `init.el` file.
   1. To add the MELPA repository:

    ```elisp
    (require 'package)
    (add-to-list 'package-archives
                '("melpa" . "https://melpa.org/packages/") t)
    (package-initialize)
    ```

## Tips and Tricks

Learn Emacs Lisp to extend and customize Emacs

- Use `Alt-x` `apropos` to search for commands and functions related to a keyword
- Familiarize yourself with Emacs' built-in help system
  - `Ctrl-h` "**followed by a key or command**"
- Practice Emacs with interactive tutorials, such as:
  - `Alt-x` `help-with-tutorial`

### Troubleshooting

1. If Emacs behaves unexpectedly, check your `init.el` file for errors or conflicts
2. Consult the Emacs documentation (`Ctrl-h` + `r`) or online resources for assistance
3. Search for or ask questions on forums, such as Stack Overflow or Emacs Reddit community

## Resources

[EMACS website] \
[EMACS wiki] \
[Stack Exchange] \
[Reddit] \
[Mastering Emacs]

[EMACS website]: <https://www.gnu.org/software/emacs/> "Official Emacs website"
[EMACS wiki]: <https://www.emacswiki.org/> "Emacs Wiki"
[Stack Exchange]: <https://emacs.stackexchange.com/> "Emacs Stack Exchange"
[Reddit]: <https://www.reddit.com/r/emacs/> "Emacs Reddit community"
[Mastering Emacs]: <https://www.masteringemacs.org/> "Mastering Emacs (book)"
[Download the installer]: <https://www.gnu.org/software/emacs/download.html> "Download the installer for Windows"
