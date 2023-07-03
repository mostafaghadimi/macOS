# Terminal

## Sharing History between sessions in terminal

Put the following line in `.zshrc`. [src](https://askubuntu.com/questions/23630/how-do-you-share-history-between-terminals-in-zsh)
```bash
setopt share_history
```

and then `source ~/.zshrc`.

## Copy STDOUT content to the clipboard

Simply run the following command (pbcopy):

```bash
cat myfile.txt | pbcopy
```
and it can be pasted using `pbpaste` command.

```bash
pbpaste  # the output will be the content of myfile.txt
```
