The following code snippets go in `~/.zshrc` unless otherwise specified.

# File extensions

Older versions of the completion that ships with mpv had a hard-coded list of filename extensions that it completes by default, which did not include all possible files that mpv can play. More recent versions will complete all files by default.

If you want to complete only certain file extensions, use something like this:

    zstyle ':completion:*:*:mpv:*' file-patterns '*.(#i)(flv|mp4|webm|mkv|wmv|mov|avi|mp3|ogg|wma|flac|wav|aiff|m4a|m4b|m4v|gif|ifo)(-.) *(-/):directories' '*:all-files'

It will fall back to completing all files if no files with the given extensions are present or match what you've typed.

If you're using an older version of the completion script, and you want to add some file extensions in addition to the ones the script completes by default, you can do this (adds .jpg and .png files):

    zstyle ':completion:*:*:mpv:*' file-patterns '*.(#i)(jpg|jpeg|png)(-.) %p:globbed-files *(-/):directories' '*:all-files'

If you want to use *only* your specified extensions, ignoring the ones that come with the script, use the form that's further up the page without the globbed-files part.

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