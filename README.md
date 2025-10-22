# tmuxpinner
Display a spinner in tmux window title.


## Installation
Put it in to a folder that is in your `PATH`, e.g. `~/bin`.


## Dependencies
Currently only `sh`.

Better use `bash` or `zsh`, I'm not very sure if the script is POSIX compatible.


## Configuration
In your `.tmux.conf`,

1.  Don't use `-w` for both `window-status-current-format` and `window-status-format`

    -   Because tmuxpinner uses them to override `-g` one.

2.  Use `#{@spinner}` as the placeholder in the options above, e.g.

    ```tmux
    # ~/.tmux.conf
    set -g window-status-format "...#{@spinner}..."
    set -g window-status-current-format "...#{@spinner}..."
    ```

## Usage
Display a spinner indefinitely:
```console
$ tmuxpinner
```

Run a command and display a spinner until the command ends:
```console
$ tmuxpinner sleep 5
```


# TODO

*   Add `status-left` and `status-right`

*   `-w`/`--wait` for Linux

*   Properly backup `-w` `window-status-format` and `window-status-current-format`

*   Out-of-box usage by using `#W` as placeholder if `#{@spinner}` not found

*   Customizable animation frames

    -   Multi-width patterns

*   Robust teardown mechanism
