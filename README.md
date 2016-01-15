# syntastic-hbstidy

[![Upstream][upstreamBadge]][upstreamLink]

[Syntastic] checker for tidy, specifically for Handlebars templates.

## Description

This plugin basically strips out the handlebars contents before passing the
contents to tidy. It is based (and 90% of the code) is the same as the HTML
tidy [Syntastic] checker.

There are also a few new HTML attributes and elements allowed (Microdata
itemprops, angular ng-attrs, and Facebook `<fb:xml>` elements).

## Installation

This plugin requires [Syntastic] installed.

It also requires the `tidy` binary (install `tidy-html5` via homebrew, or any
`tidy` via your OS package manager).

Install the plugin as usual, e.g. using vim-plug:

```viml
Plug 'davidosomething/syntastic-hbstidy'
```

Then, enable it for your handlebars filetype in your vimrc:

```viml
" Map some filetypes, e.g. turn off html checkers on handlebars (I'm using my
" hbstidy instead of html tidy)
let g:syntastic_filetype_map = {
      \   'html.handlebars': 'handlebars',
      \ }

" Use these checkers (handlebars is a different checker, not required for the
" hbstidy plugin)
let g:syntastic_handlebars_checkers  = ['handlebars', 'hbstidy']
```

## Configuration

All the same options as the HTML tidy syntax checker apply, just replace
`html_tidy` with `handlebars_hbstidy` for all settings variables.  
Refer to the [syntastic wiki entry for tidy].


[upstreamBadge]: https://img.shields.io/badge/upstream-GitHub-lightgrey.svg
[upstreamLink]:  https://github.com/davidosomething/syntastic-hbstidy
[Syntastic]: https://github.com/scrooloose/syntastic
[syntastic wiki entry for tidy]: https://github.com/scrooloose/syntastic/wiki/HTML%3A---tidy
