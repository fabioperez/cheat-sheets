# vim

## File IO

### opening files

* [`<c-p>`](https://github.com/kien/ctrlp.vim#basic-usage) - fuzzy finder
  - `<c-f>` - go to next mode
  - `<c-v>` - open in a vertical split
  - `<c-v>` - open in an horizontal split
  - `<c-z>` - mark/unmark multiple files
  
### buffers

* `ls` - list all buffers
* `:b <tab>` - go to buffer
* `:bd` or `<space> q` - delete buffer

## Editing

### movement

#### Python

* `[[` - jump to previous class or function
* `]]` - jump to next class or function

### folding

`za` - toggle folding

### git

* [`:Gstatus`](https://github.com/tpope/vim-fugitive)
 - `-` - add/reset file
 - `p` - add/reset `-- patch` 
* `Gcommit`
* `Gblame`
* `Gdiff`

## Code style

### Python

* `<F7>` - run [flake8](https://github.com/pycqa/flake8/)
