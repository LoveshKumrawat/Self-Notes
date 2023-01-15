# **SSH Connection b/w 2 diffrent host within a same Network**
<br>

> **Install SSH**

	sudo apt install ssh
---
> **Enable & Start SSH service in the Target Host**

	sudo systemctl enable ssh
	sudo systemctl start ssh
---
> **Connect from the Source Host**

	ssh <username>@<hostIP>

> **With the Target Host credentials**

- *Username*

		whoami

- *Host IP*

		hostname -I
---