The following code snippets go in `~/.zshrc` unless otherwise specified.

# File extensions

The Zsh completion that ships with mpv currently has a hard-coded list of filename extensions that it completes by default, which does not include all possible files that mpv can play. If you want to add extensions to the list, use something like this (adds .jpg and .png files):

    zstyle ':completion:*:complete:mpv:*' file-patterns '*.(#i)(jpg|jpeg|png)(-.) %p:globbed-files *(-/):directories' '*:all-files'

If you want to use *only* your specified extensions, ignoring the ones that come with the script, use something like this instead:

    zstyle ':completion:*:complete:mpv:*' file-patterns '*.(#i)(jpg|jpeg|png)(-.) *(-/):directories' '*:all-files'

See [Issue #2273](https://github.com/mpv-player/mpv/issues/2273) for a discussion on what the defaults should be. Input is wanted.

# URLs

The current completion script suggests URL prefixes by default, most of which aren't useful to the average user and tend to get in the way. To disable them completely, unless no files match:

    zstyle ':completion:*:complete:mpv:*' tag-order '!urls'
