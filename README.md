# qvmx

Some helper scripts for [Qubes OS](https://qubes-os.org) to provide TUIs for annoying operations.

### Prerequisites

These scripts use [`gum`](https://github.com/charmbracelet/gum) heavily. Go get the bin (in a dispvm) and pop that into dom0 and its `PATH` however you prefer.

**⚠️ Obviously, installing binaries in dom0 is a big security consideration. Do so at your own peril.**

### Installing the scripts

- Download or clone this repo
- Copy them into dom0 using: <br/>
(Assuming the repo is cloned into `/home/user/qvmx`)
    - `sudo qvm-run $vm 'cat /home/user/qvmx/dom0/qvmx-copy-screenshot' > /tmp/qvmx-copy-screenshot`
    - `sudo qvm-run $vm 'cat /home/user/qvmx/dom0/qvmx-prune-lvm' > /tmp/qvmx-prune-lvm`
    - `chmod +x /tmp/qvmx-*`
    - `sudo mv /tmp/qvmx-* /usr/local/bin`

## Scripts

### `qvmx-copy-screenshot`

Provides a nice TUI that moves the most recent _n_ screenshots from `~/Pictures/Screenshots/` to `~/Pictures/` in a qube of your choice.

### `qvmx-prune-lvm`

Removes LVM volumes marked `-backup` (by default ignoring any qubes with `-matrix` in their name, but this is optional).

The TUI confirms a few times, since this is destructive as hell.