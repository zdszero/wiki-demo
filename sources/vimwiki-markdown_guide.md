% vimwiki-markdown guide

![vimwiki-markdown](../docs/images/image_2023-07-16-21-17-55.png)

## Introduction

vimwiki-markdown is a simple, easy-to-use vim plugin which is intended to help
you organize your notes in markdown with hierarchy structure and convert your
notes to a static html site using pandoc.

Here is a demo site and an introduction video

## Quick Start

1. Install this plugin (use vim-plug for example): `Plug 'zdszero/vimwiki-markdown'`
2. Copy the following suggested settings to your `.vimrc`.
3. Open vim and enter `<leader>ww` to open vimwiki's root index file.
4. Input stuff stuff, save the change, then enter `<leader>wb` to open
the generated html file in your browser.

## Settings

__options and mappings__

suggested setting and keymaps as follows:

```vim
let g:wiki_config = {
  \ 'home': '/home/zds/Wiki',  " home directory to put wiki
  \ 'markdown_dir': 'sources', " directory to put the markdown files
  \ 'html_dir': 'docs',        " directory to put the html files
  \ 'template_path': 'templates/github.html', " template file used by pandoc to generate html
  \}
let g:wiki_preview_browser = 'google-chrome-stable'
let g:wiki_generate_toc = 1

" open wiki home index
nnoremap <leader>ww <Plug>WikiIndex
" create or follow a markdown link
nnoremap <leader>wn <Plug>WikiCreateFollowLink
" create or follow a subdirectory index link
nnoremap <leader>wn <Plug>WikiCreateFollowDirectory
" goto parent directory's index
nnoremap <leader>wp <Plug>WikiGotoParent
" delete current link
nnoremap <leader>wd <Plug>WikiDeleteLink
" rename current link
nnoremap <leader>wr <Plug>WikiRenameLink
" convert current markdown into html
nnoremap <leader>wh <Plug>Wiki2HTML
" convert all changed markdowns into htmls
nnoremap <leader>wH <Plug>WikiAll2HTML
" convert current markdown into html and browse html in browser
nnoremap <leader>wb <Plug>Wiki2HTMLBrowse
" open current markdown's corresponding html
nnoremap <leader>wo <Plug>WikiOpenHTML
" paste image in vimwiki's image directory and 
nnoremap <leader>wi <Plug>WikiPasteImage
```

__commands__

- `:WikiAll2HTML`: convert all changed markdown files to htmls
- `:WikiAll2HTML!`: convert all markdown files to htmls

read `:help vimwiki-markdown` for more details

## Comparison with vimwiki

- vimwiki-markdown is inpired by vimwiki and share the same philosophy to take notes.
- vimwiki-markdown is simpler than vimwiki and only focus on markdown format.
And it can be used with other vim markdown plugins without conflict.
- vimwiki-markdown relies on pandoc to generate html files while vimwiki doesn't.
So you need to [install pandoc](https://pandoc.org/installing.html) before using vimwiki-markdown.
From this perspective, vimwiki-markdown is heavier than vimwiki.

## License

MIT
