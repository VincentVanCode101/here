# here — Run containers right **here**, effortlessly

`here` is a lightweight Docker wrapper for quickly dropping into a container with sane defaults and zero config. It's meant to be used just like any shell command.

Why the name? Because it’s literally the vibe:
> *"Hmm, here... a `node:alpine` would be nice."*  
> → `here -i node:alpine`

## Installation

You have two options to install `here`:

### Option 1: Use `install.sh` to create a system-wide symlink

This will link the `here` script into a standard system location like `/usr/local/bin` or `/opt/homebrew/bin`.

```bash
./install.sh
```

### Option 2: Add the repo to your PATH manually

If you'd rather avoid symlinking:

```bash
export PATH="$PATH:/path/to/this/repo/here"
```

You can also make this permanent by adding it to your shell config (e.g. .bashrc, .zshrc).


## Basic usage
The simplest way to use here is without any config file, only with parameter.
```shell
here -i <docker image name>
```
This will spawn a single Docker container without any additions and default settings like workdir and current user ID
(see `here -h` for more information)


### Usage Examples

```bash
here -i alpine echo hi              # Runs a quick command
here -i alpine                      # Opens shell (sh)
here -i ubuntu                     # Opens shell (bash)
here -i ubuntu -r bash             # Run as root
here -i node:alpine node           # Starts Node.js REPL
here -i ubuntu -u 1000:1000 bash   # Run with specific UID:GID
here -i alpine -w /app ls          # Custom workdir
```