# **Kubernetes**
<br>

> **k3s Installation**
```sh
curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION='v1.23.8+k3s1' sh -
```
---

> **Kube Config File Setup**
```sh
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
```
---

> **MiniKube Installation**
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube_latest_amd64.deb
sudo dpkg -i minikube_latest_amd64.deb
```

- **MiniKube's kubectl setup**

	```sh
	snap install kubectl --classic
	```

	- If required add path of kubectl `/snap/bin`

		```sh
		sudo gedit /etc/environment
		```
---