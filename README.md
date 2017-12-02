Small script to help merge history between terminals.

# Setup

```
cd ~/workspace
git clone https://github.com/xinzweb/bash_history.git
```

Update the `/.bashrc` file to `source ~/workspace/bash_history/merge_history`.

# Usage

`merge_history` need to be called from all the terminals in order to merge
their histories.

# Details

The history will be merged, and duplicates will be removed when calling
`merge_history`, and also the `~/.bash_history` file will be updated with the
merged history.

The local history after calling the `merge_history` still keep the same order,
however the new command from the other terminals will be added to the very top
of the history as the oldest command. This will try to avoid new commands
disturb the existing order of local history. If new commands from other
terminals are used in this terminal, then the order will be updated again.

If the `.bashrc` already have settings `shopt -s histappend`, then as
the session ends all the history will be append to the `./bash_history`, and
next `merge_history` will remove duplicates again if there is any.
