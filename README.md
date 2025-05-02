# File System CLI

## Table of Contents

* [Overview](#overview)
* [Usage](#usage)
* [Commands](#commands)

  * [Navigation Commands](#navigation-commands)

    * [`pwd`](#pwd--print-working-directory)
    * [`ls`](#ls--list-directory-contents)
    * [`cd`](#cd--change-directory)
  * [Management Commands](#management-commands)

    * [`mkdir`](#mkdir--make-directory)
    * [`rm`](#rm--remove-file-or-directory)
    * [`cp`](#cp--copy-files-and-directories)
    * [`mv`](#mv--move-or-rename-files-and-directories)
    * [`touch`](#touch--create-new-file)
    * [`upload`](#upload--upload-new-file)
    * [`download`](#download--download-file)
  * [Display Commands](#display-commands)

    * [`cat`](#cat--display-file-content)

---

## Overview

**File System CLI** is a console application that provides a command-line interface for interacting with Azure File Shares using familiar Linux-style commands. It allows you to perform basic file system operations such as navigating directories, managing files and folders, and viewing file contents.

This tool is especially useful for developers, system administrators, and DevOps engineers who prefer terminal-based workflows when working with Azure File Shares. Instead of navigating through the Azure portal, you can now perform day-to-day file operations directly from your terminal, speeding up tasks and improving productivity.

The application is written in C# and designed with usability and clarity in mind. It mirrors many common Linux command names and behaviors but is adapted to work with Azure’s cloud-based file storage. While the commands are inspired by Linux, they are not identical and may offer limited functionality. Refer to this documentation for details on usage and supported features.

This CLI also supports credential management and is designed to simplify working with remote Azure storage while providing helpful error messages and feedback for each command.

---

## Usage

Upon the first launch, the CLI will prompt you to enter your Azure File Share credentials. These credentials are required to access your cloud storage and can be modified later using the `change-credentials` command.

Once valid credentials are provided, the File System CLI will launch and you can start issuing commands.

---

## Commands

### Navigation Commands

#### `pwd` – Print Working Directory

Prints the full path of the current working directory.

#### `ls` – List Directory Contents

Lists all files and directories in the current working directory.

#### `cd` – Change Directory

Changes the current working directory.

* `<path-to-directory>`: Full or relative path to the target directory. A `/` at the beginning indicates an absolute path. Use `..` to navigate up one level.

---

### Management Commands

#### `mkdir` – Make Directory

Creates one or more directories in the current working directory. Subdirectories will be created if necessary.

* `<directory-name>`: Name of the directory to be created.

#### `rm` – Remove File or Directory

Deletes the specified file or directory (including its contents).

* `<file-or-directory-name>`: Relative path of the file or directory to delete.

#### `cp` – Copy Files and Directories

Copies a file or directory from the source to the destination path.

* `<source>`: Relative path of the source file or directory.
* `<destination>`: Relative path for the copy target.

#### `mv` – Move or Rename Files and Directories

Moves or renames files or directories.

* `<source>`: Relative path of the file or directory to move.
* `<destination>`: Target path. If it starts with `/`, it is treated as an absolute path.

**Examples:**

* `mv old_filename new_filename` — Rename a file.
* `mv filename /directory/new_directory` — Move a file to a new location.
* `mv filename subdirectory` — Move a file into a subdirectory.

#### `touch` – Create New File

Creates a new file in the current working directory.

* `<filename>`: Relative path of the file to be created.

#### `upload` – Upload New File

Uploads a file from the local machine to the Azure File Share.

* `<destination-filename>`: Target file path in Azure storage.
* `<source-file-path>`: Path of the local file to upload.

#### `download` – Download File

Downloads a file from Azure File Share to the local file system.

* `<source-filename>`: Path of the file in Azure storage.
* `<destination-file-path>`: Target path on the local machine.

---

### Display Commands

#### `cat` – Display File Content

Displays the contents of the specified file.

* `<filename>`: Relative path of the file to display.

---

For any issues or questions, please open an issue in this repository.
