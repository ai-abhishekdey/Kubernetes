# Getting Started:
```
sudo su
sudo apt-get update
sudo apt-get install curl
```
## Install kubectl 

* Download the latest release with the command:
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

```
* Validate the binary

```
 curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```

* Validate the kubectl binary against the checksum file:

```
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```

* Install kubectl

```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

* Test to ensure the version you installed is up-to-date:

```
kubectl version --client
```
## Install Kind

```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/latest/kind-linux-amd64
chmod +x kind
sudo mv kind /usr/local/bin/kind
```

* Check kind version

```
kind version
```

## References:

1. https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux

2. https://www.youtube.com/watch?v=7FK_4quGX7M

3. https://www.youtube.com/watch?v=AJEaIQV-tts
