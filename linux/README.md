# Upgrading TTY
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

# [General](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/general.md)
# [Enumeration](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/enumeration.md)
# [Local File Inclusion](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/local%20file%20inclusion.md)
# [Networking](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/networking.md)
# [Characters not allowed](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/characters%20not%20allowed.md)
# [Exploitation](https://github.com/PinkDraconian/InfoSecCheatSheets/blob/master/linux/exploitation.md)
