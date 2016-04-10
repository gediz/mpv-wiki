The following code snippets go in `~/.zshrc` unless otherwise specified.

# File extensions

The Zsh completion that ships with mpv currently has a hard-coded list of filename extensions that it completes by default, which does not include all possible files that mpv can play. If you want to add extensions to the list, use something like this (adds .jpg and .png files):

    zstyle ':completion:*:complete:mpv:*' file-patterns '*.(#i)(jpg|jpeg|png)(-.) %p:globbed-files *(-/):directories' '*:all-files'

If you want to use *only* your specified extensions, ignoring the ones that come with the script, use something like this instead:

    zstyle ':completion:*:complete:mpv:*' file-patterns '*.(#i)(jpg|jpeg|png)(-.) *(-/):directories' '*:all-files'

See [Issue #2273](https://github.com/mpv-player/mpv/issues/2273) for a discussion on what the defaults should be. Input is wanted.

# URLs

Older versions of the completion script (before v0.17.0) suggest URL prefixes by default, most of which aren't useful to the average user and tend to get in the way. Recent versions suppress these by default unless no files match what you've typed. To get this behaviour in an older version, you can use this:

    zstyle ':completion:*:*:mpv:*' tag-order '!urls'

To get the old behaviour (URLs completed along with files) in a newer version, use:

    zstyle ':completion:*:*:mpv:*' tag-order

Or, you can set `tag-order` to whatever custom order you might want. The default URL suppression only happens if it isn't defined at all.

If you want URLs completed at the same time as files, but grouped by type (i.e. all the files first, then all the URLs), you can use this, in addition to the `tag-order` style:

    zstyle ':completion:*:*:mpv:*' group-name ''

If you want to blacklist certain URL prefixes, you can do this:

    zstyle ':completion:*:*:mpv:*' ignored-patterns '(memory|md5|whatever-else)://'

You'll also need to reset `tag-order` (see above) if you want the remaining prefixes to be displayed alongside files. It will work with or without grouping by type. If you want a whitelist instead of a blacklist, you'll have to set up custom tags. If you figure it out, feel free to post it here.