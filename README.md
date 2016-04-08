# Linux Config
Little repo to maintain the same linux configuration across multiple hosts. 

**Intended use is you fork this and be able to make your own modifications.**

## Changes you need to make

* Required: `/config/.gitconfig` needs your full name and email address
* Optional: If you want to install from a directory that isn't `.bash` you need to change the `INSTALL_DIR` variable in `/install` and update `/auto-update`

## Install
```sh
git clone your-forked-repo-url/linux-config.git .bash
```

## Auto updates

If you want the configurations to automatically update edit your cron tab like so:

```sh 
crontab -e 
```

And add the following: 

```sh
0 * * * * ~/.bash/auto-update > /tmp/seans-linux-sync.log 2>&1
```

## Functions included

### cl 
**Description:** Enters a directory and lists contents. CD + LS

**Example usage:** 
```sh
cl ~/.bash
```

### cdn
**Description:** Traverse backwards by number. Prevents you from doing cd ../../../

**Example usage:**
```sh
cdn 2
```

### extract
**Description:** Extracts any file.

**Example usage:**
```sh
extract archive.tar.bz2
```

### follow
**Description:** Follows a file. Shorter tail -f -n 600

**Example usage:**
```sh
follow /var/log/nginx/error.log
```

### lso
**Description:** Display octal file permissions

**Example usage:**
```sh
lso()
```

## Other things included

> **This is currently broken and disabled**

I've also changed .inputrc around a little to give better auto-completion for commands (in my opinion) using command history, type part of a previous command and then press up or down arrows to cycle through options.
