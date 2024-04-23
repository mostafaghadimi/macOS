# Common Issues

## Command + Tab does not work consistently on MacOS

Your Dock will disappear for a second and then reappear but open apps will *not* be affected.

```bash
killall Dock
```

## Close all SSH sessions

Killing all the SSH server processes

```bash
pkill -f ssh
```

## Disk Usage command

The correspondig command `du -h --max-depth=1` in MacOS is the following:


```bash
du -h -d 1
```


## chown bad substitution

```bash
sudo chown -R $USER:staff <directory_name>
```

[Why does echo “$USER:staff” throw zsh: bad substitution?](https://superuser.com/questions/1633756/why-does-echo-userstaff-throw-zsh-bad-substitution)

```bash
sudo chown -R $USER:"staff" <directory_name>
```

## Docker Disk Space 

> E: You don't have enough free space in /var/cache/apt/archives/.

**Solution**:

Upgrade the disk size or execute `docker system prune -f` command:

```bash
Dashboard -> Settings -> Resources 
```

