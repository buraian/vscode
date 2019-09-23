# Visual Studio Code Settings Sync

## Important Files

### The Settings Folder
```
~/.config/code
```

### VS Code Settings Folder
```
~/Library/Application Support/Code/User
```

### The Symbolic Link
```
~/Library/Application Support/Code/User -> ~/.config/code/User
```

## Tasks

- [Setup Git Repo For Sync](#setup-git-repo-for-sync)
- [Export Plugin List](#export-plugin-list)
- [Install Plugins](#install-plugins)

### Setup Git Repo For Sync

Install Visual Studio Code.

Move settings folder for Git sync

```shell
$ mkdir -p ~/.config/code
$ mv -v ~/Library/Application\ Support/Code/User ~/.config/code/User
```

Create Symlink

```shell
$ ln -s ~/.config/code/User ~/Library/Application\ Support/Code/User
```

Setup Git Repo

```shell
$ cd ~/.config/code
$ git remote add origin https://github.com/buraian/vscode.git
```

Pull from remote and overwrite any local files.

### Export Plugin List

```shell
$ code --list-extensions > extensions.list
```

### Install Plugins

```shell
$ cat extensions.list | xargs -L 1 code --install-extension
```

[Note: Make sure `code` is available to `PATH`.](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line)
