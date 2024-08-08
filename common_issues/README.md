# Common Issues

## Table of Contents

- [Common Issues](#common-issues)
  - [Table of Contents](#table-of-contents)
  - [Command + Tab does not work consistently on MacOS](#command--tab-does-not-work-consistently-on-macos)
  - [Close all SSH sessions](#close-all-ssh-sessions)
  - [Disk Usage command](#disk-usage-command)
  - [chown bad substitution](#chown-bad-substitution)
  - [Docker Disk Space](#docker-disk-space)
  - [ModuleNotFoundError: No module named 'distutils'](#modulenotfounderror-no-module-named-distutils)
  - [Apple Devices](#apple-devices)
    - [Sync Messages iPhone and Mac](#sync-messages-iphone-and-mac)
    - [Activating Universal Clipboard (Copy and Paste between devices)](#activating-universal-clipboard-copy-and-paste-between-devices)

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

Useful command:

```bash
docker system df
```

## ModuleNotFoundError: No module named 'distutils'

```bash
pip install setuptools
```

## Apple Devices

### Sync Messages iPhone and Mac

> On your iPhone, go to **Settings > Messages**. Tap Text **Message Forwarding**.

**Note**: If you don't see Text Message Forwarding, make sure you're signed in to iMessage using the same Apple ID on both your iPhone and your Mac.

### Activating Universal Clipboard (Copy and Paste between devices)

To activate Universal Clipboard, follow these simple steps:

- Make sure your devices are signed into the **same iCloud** account and have both **Bluetooth** and **Wi-Fi** enabled.

- On your Mac, go to System **Settings -> General** and select “Allow Handoff between this Mac and your iCloud devices.”

- For iPhone and iPad, go to **Settings -> General** -> AirPlay & Handoff and enable Handoff.
