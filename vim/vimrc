""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Lexi's vimrc, borrowed from many places
" Future Lexi: don't forget to brew install vim. YouCompleteMe won't work with system vim :/
"
" Shortcuts:
"   ; maps to :
"   ,a: Ag (fzf command)
"   ,b: browse tags
"   ,c: toggle comments
"   ,C: toggle block comments
"   ,e: open file in new tab
"   ,f: Files (fzf command)
"   ,g: ctags go to definition in new tab
"   ,G: ctags go to definition in new buffer
"   ,l: toggle NERDTree
"   ,h: open a shell in a new tab
"   ,k: syntax-check the current file
"   ,m: toggle mouse support
"   ,p: toggle paste mode
"   ,o: open file
"   ,s: split window
"   ,t: new tab
"   ,w: close tab
"   kj: enter normal mode and save
"   Ctrl+{h,j,k,l}: move among windows
"   ii: operate on all text at current indent level
"   ai: operate on all text plus one line up at current indent level
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
if has('python3')
  silent! python3 1
endif

" long live vim
set encoding=utf-8
set nocompatible
set shell=/bin/bash

" vundle
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
set rtp+=/usr/local/opt/fzf
call vundle#begin()
Plugin 'gmarik/Vundle.vim'

" color schemes
Plugin 'nanotech/jellybeans.vim'
Plugin 'tomasr/molokai'
Plugin 'vim-scripts/Skittles-Dark'
Plugin 'sickill/vim-monokai'
Plugin 'hukl/Smyck-Color-Scheme'
Plugin 'vim-scripts/wombat256.vim'
Plugin 'flazz/vim-colorschemes'
Plugin 'challenger-deep-theme/vim'
Plugin 'NLKNguyen/papercolor-theme'

" plugins
Plugin 'mileszs/ack.vim'
Plugin 'scrooloose/nerdtree'
Plugin 'tpope/vim-fugitive'
Plugin 'jistr/vim-nerdtree-tabs'
Plugin 'tpope/vim-repeat'
Plugin 'tpope/vim-surround'
Plugin 'tomtom/tcomment_vim'
Plugin 'vim-scripts/trailing-whitespace'
" Plugin 'vim-scripts/taglist.vim'
Plugin 'terryma/vim-multiple-cursors'
Plugin 'michaeljsmith/vim-indent-object'
Plugin 'gregsexton/gitv'
Plugin 'bling/vim-airline'
Plugin 'wincent/Command-T'
Plugin 'SirVer/ultisnips'
Plugin 'honza/vim-snippets'
Plugin 'godlygeek/tabular'
Plugin 'easymotion/vim-easymotion'
Plugin 'Valloric/YouCompleteMe'
Plugin 'xolox/vim-misc'
Plugin 'junegunn/fzf'
Plugin 'junegunn/fzf.vim'
Plugin 'tpope/vim-abolish'
" Plugin 'xolox/vim-easytags'

" syntax files
Plugin 'pangloss/vim-javascript'
Plugin 'tpope/vim-markdown'
Plugin 'voithos/vim-python-syntax'
Plugin 'kchmck/vim-coffee-script'
Plugin 'derekwyatt/vim-scala'
Plugin 'groenewege/vim-less'
Plugin 'leafgarland/typescript-vim'
Plugin 'flowtype/vim-flow'
Plugin 'mxw/vim-jsx'
Plugin 'fatih/vim-go'
Plugin 'w0rp/ale'

call vundle#end()
filetype plugin indent on

" Faster jump-to-def in go
let g:go_def_mode='godef'

let g:ycm_server_python_interpreter='/usr/local/bin/python3'

" Trigger configuration. Do not use <tab> if you use https://github.com/Valloric/YouCompleteMe.
let g:UltiSnipsExpandTrigger="<c-e>"
let g:UltiSnipsListSnippets="<c-l>"
let g:UltiSnipsJumpForwardTrigger="<c-b>"
let g:UltiSnipsJumpBackwardTrigger="<c-z>"

" If you want :UltiSnipsEdit to split your window.
let g:UltiSnipsEditSplit="vertical"

" command-t config
let g:CommandTTraverseSCM = 'pwd'

" checksyntax config
let g:checksyntax#auto_mode = 0

" taglist config
" let g:Tlist_Use_Right_Window = 1

" airline config
let g:airline_powerline_fonts = 1
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#ale#enabled = 1

" ale config
let g:ale_linters = {'go': ['gometalinter', 'gofmt']}
let g:ale_go_metalinter_options = "--fast"
let g:ale_lint_on_text_changed = "normal"
let g:ale_lint_on_insert_leave = 1
let g:ale_sign_error = '❌'
let g:ale_sign_style_error = '⁉️'
let g:ale_sign_warning = '⚠️'
let g:ale_sign_style_warning = '💩'

" easymotion config
let g:EasyMotion_smartcase = 1
map \j <Plug>(easymotion-j)
map \k <Plug>(easymotion-k)

" fzf config
let g:fzf_buffers_jump = 1
autocmd! FileType fzf
autocmd  FileType fzf set laststatus=0 noshowmode noruler
  \| autocmd BufLeave <buffer> set laststatus=2 showmode ruler
let $FZF_DEFAULT_COMMAND = 'ag -g ""'

" coffeescript config
hi link coffeeSpaceError NONE

" syntax highlighting and auto-indentation
syntax on
filetype indent on
filetype plugin on
inoremap # X<C-H>#
set ai
set si
set nu
set statusline+=%#warningmsg#
" set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*

" let g:syntastic_always_populate_loc_list = 1
" let g:syntastic_auto_loc_list = 1
" let g:syntastic_check_on_open = 1
" let g:syntastic_check_on_wq = 1
" let g:syntastic_javascript_checkers = ['eslint']
" let g:syntastic_javascript_eslint_exe = '$(npm bin)/eslint'

" let g:syntastic_error_symbol = '❌'
" let g:syntastic_style_error_symbol = '⁉️'
" let g:syntastic_warning_symbol = '⚠️'
" let g:syntastic_style_warning_symbol = '💩'

" highlight link SyntasticErrorSign SignColumn
" highlight link SyntasticWarningSign SignColumn
" highlight link SyntasticStyleErrorSign SignColumn
" highlight link SyntasticStyleWarningSign SignColumn

" omg folding is the worst
set nofoldenable

" omg automatic comment insertion is the worst
autocmd FileType * setlocal formatoptions-=c formatoptions-=r formatoptions-=o

" expand tabs to 4 spaces
set shiftwidth=4
set tabstop=4
set smarttab
set expandtab

" faster tab navigation
nnoremap <S-tab> :tabprevious<CR>
nnoremap <tab> :tabnext<CR>

" always show tab line to avoid annoying resize
set showtabline=2

" searching options
set incsearch
set ignorecase
set smartcase

" disable backups
set nobackup
set nowritebackup
set noswapfile

" disable annoying beep on errors
set noerrorbells
if has('autocmd')
  autocmd GUIEnter * set vb t_vb=
endif

" font options
set background=dark
set t_Co=256
colorscheme PaperColor

" keep at least 5 lines below the cursor
set scrolloff=5

" window options
set showmode
set showcmd
set ruler
set ttyfast
set backspace=indent,eol,start
set laststatus=2

" enable mouse support
set mouse=a

" cursor
let &t_SI = "\<Esc>]50;CursorShape=1\x7"
let &t_EI = "\<Esc>]50;CursorShape=0\x7"

" word wrapping
set wrap
set linebreak
set nolist

" better tab completion on commands
set wildmenu
set wildmode=list:longest
set wildignore+=*.pyc,__pycache__

" close buffer when tab is closed
set nohidden

" ctags
" set tags=./tags,tags;

" enable autoread for changed files
set autoread

" actually autoread doesn't work lol
" Save whenever switching windows or leaving vim. This is useful when running
" the tests inside vim without having to save all files first.
au FocusLost,WinLeave * :silent! noautocmd wa

" Trigger autoread when changing buffers or coming back to vim.
au FocusGained,BufEnter * :silent! !

" better moving between windows
map <C-j> <C-W>j
map <C-k> <C-W>k
map <C-h> <C-W>h
map <C-l> <C-W>l

" shortcuts to common commands
let mapleader = ","
nnoremap <leader>a :Ag
" nnoremap <leader>b :TlistToggle<CR>
nnoremap <leader>b :Buffers<CR>
nnoremap <leader>c :TComment<CR>
nnoremap <leader>C :TCommentBlock<CR>
vnoremap <leader>c :TComment<CR>
vnoremap <leader>C :TCommentBlock<CR>
nnoremap <leader>e :tabnew<CR>:CommandT<CR>
nnoremap <leader>f :Files<CR>
nnoremap <leader>g <C-w><C-]><C-w>T
nnoremap <leader>G <C-]>
nnoremap <leader>h :tabnew<CR>:ConqueTerm bash<CR>
nnoremap <leader>l :NERDTreeTabsToggle<CR>
nnoremap <leader>k :CheckSyntax<CR>
nnoremap <leader>n :ALENextWrap<CR>
nnoremap <leader>N :ALEPreviousWrap<CR>
nnoremap <leader>o :CommandT<CR>
nnoremap <leader>p :set invpaste<CR>
nnoremap <leader>t :tabnew<CR>
nnoremap <leader>s :vsplit<CR>
nnoremap <leader>w :tabclose<CR>
nnoremap vimrc :vs $MYVIMRC<CR>
nnoremap vimre :so $MYVIMRC<CR>

map \ <Plug>(easymotion-prefix)

autocmd FileType go nmap <silent> <Leader>d <Plug>(go-def-tab)

" ; is better than :, and kj is better than ctrl-c
nnoremap ; :

" also autosave when going to insert mode
inoremap kj <Esc>:w<CR>

" more logical vertical navigation
nnoremap <silent> k gk
nnoremap <silent> j gj

" make copy/pasting nice
function! ToggleMouse()
    if &mouse == 'a'
        set mouse=r
        set nonu
    else
        set mouse=a
        set nu
    endif
endfunction
nnoremap <leader>m :call ToggleMouse()<CR>
map <leader>jt  <Esc>:%!json_xs -f json -t json-pretty<CR>

" easier macro creation
:nnoremap <Space> @q

set modifiable

" open an api file's test
" Lexi actually wrote this!
function! OpenTest()
  let t:srcPath = bufname("")
  if match(t:srcPath, "src") == -1
    echom "Could not find test for " . t:srcPath
    return
  endif

  let t:testPath = substitute(t:srcPath, "src", "test", "")
  if !filereadable(t:testPath)
    " Some of our tests are written in js
    let t:testPath = substitute(t:testPath, "coffee", "js", "")
  endif
  if !filereadable(t:testPath)
    " Sometimes the test is written in cs and the src is in js
    let t:testPath = substitute(t:testPath, "js", "coffee", "")
  endif
  if !filereadable(t:testPath)
    echom "Could not find test for " . t:srcPath
    return
  endif

  execute "vs " . t:testPath
endfunction

command! Test :call OpenTest()
