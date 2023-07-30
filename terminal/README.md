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

## Docker Auto-Complete issue (ZSH)

```bash
sudo mkdir -p /usr/local/share/zsh/site-functions/
sudo ln -s /Applications/Docker.app/Contents/Resources/etc/docker.zsh-completion /usr/local/share/zsh/site-functions/_docker
sudo ln -s /Applications/Docker.app/Contents/Resources/etc/docker-compose.zsh-completion /usr/local/share/zsh/site-functions/_docker-compose
# optional: sudo ln -s /Applications/Docker.app/Contents/Resources/etc/docker-machine.zsh-completion /usr/local/share/zsh/site-functions/_docker-machine
echo "autoload -Uz compinit; compinit" >> .zshrc
```

and then `source ~/.zshrc`.
