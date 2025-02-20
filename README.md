# EditorConfig Vim Plugin

[![Travis Build Status](https://img.shields.io/travis/cxw42/editorconfig-vim.svg?logo=travis)](https://travis-ci.org/editorconfig/editorconfig-vim)
[![Appveyor Build Status](https://img.shields.io/appveyor/ci/cxw42/editorconfig-vim.svg?logo=appveyor)](https://ci.appveyor.com/project/cxw42/editorconfig-vim)

This is an [EditorConfig][] plugin for Vim. This plugin can be found on both
[GitHub][] and [Vim online][].

## Installation

To install this plugin, you can use one of the following ways:

- Download the [archive][] and extract it into your Vim runtime directory
  (`~/.vim` on UNIX/Linux and `$VIM_INSTALLATION_FOLDER\vimfiles` on windows).
  You should have 3 sub-directories in this runtime directory now: "autoload",
  "doc" and "plugin".

OR

- Use [pathogen][] (the git repository of this plugin is
  https://github.com/editorconfig/editorconfig-vim.git)

OR

- Use [Vundle][] by adding to your `.vimrc` Vundle plugins section:

        Plugin 'editorconfig/editorconfig-vim'

  Then remember to call `:PluginInstall`.

### No external editorconfig core library is required

Previous versions of this plugin also required a Python "core".
The core included the code to parse `.editorconfig` files.
This plugin **includes** the core, so you don't need to download the
core separately.

## Supported properties

The EditorConfig Vim plugin supports the following EditorConfig [properties][]:

* `indent_style`
* `indent_size`
* `tab_width`
* `end_of_line`
* `charset`
* `insert_final_newline` (Feature +fixendofline (available on Vim 7.4.785+) or [PreserveNoEOL][] is required for this property)
* `trim_trailing_whitespace`
* `max_line_length`
* `root` (only used by EditorConfig core)

## Recommended Options

All of the options which are supported are documented in [editorconfig.txt][]
and can be viewed by executing the following: `:help editorconfig`. You may
need to execute `:helptags ALL` so that Vim is aware of editorconfig.txt.

#### Excluded patterns.

To ensure that this plugin works well with [Tim Pope's fugitive][], use the
following patterns array:

    let g:EditorConfig_exclude_patterns = ['fugitive://.*']

If you wanted to avoid loading EditorConfig for any remote files over ssh:

    let g:EditorConfig_exclude_patterns = ['scp://.*']

Of course these two items could be combined into the following:

    let g:EditorConfig_exclude_patterns = ['fugitive://.*', 'scp://.*']

#### Disable rules

You might want to override some project-specific EditorConfig rules in global
or local vimrc in some cases, e.g., to resolve conflicts of trailing whitespace
trimming and buffer autosaving.

    let g:EditorConfig_disable_rules = ['trim_trailing_whitespace']

You are able to disable any supported EditorConfig properties.

## Bugs and Feature Requests

Feel free to submit bugs, feature requests, and other issues to the
[issue tracker][]. Be sure you have read the [contribution guideline][]!

[EditorConfig]: http://editorconfig.org
[GitHub]: https://github.com/editorconfig/editorconfig-vim
[PreserveNoEOL]: http://www.vim.org/scripts/script.php?script_id=4550
[Tim Pope's fugitive]: https://github.com/tpope/vim-fugitive
[Vim online]: http://www.vim.org/scripts/script.php?script_id=3934
[Vundle]: https://github.com/gmarik/Vundle.vim
[archive]: https://github.com/editorconfig/editorconfig-vim/archive/master.zip
[contribution guideline]: https://github.com/editorconfig/editorconfig/blob/master/CONTRIBUTING.md#submitting-an-issue
[issue tracker]: https://github.com/editorconfig/editorconfig-vim/issues
[pathogen]: https://github.com/tpope/vim-pathogen
[properties]: http://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties
[editorconfig.txt]: https://github.com/editorconfig/editorconfig-vim/blob/master/doc/editorconfig.txt
