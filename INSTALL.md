# 1. Install docker 
  https://docs.docker.com/engine/install/ubuntu/

1.1 uninstall older dockers
```
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

## 1.2  update package source
### Add Docker's official GPG key:
```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```
### Add the repository to Apt sources:
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

## 1.3 install docker
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## 1.4 verify installation

```sudo docker run hello-world```


# 2. Install mailtrain
## 2.1 Checkout our modified version
```
git clone https://github.com/regnen/mailtrain.git

git checkout -b CSV_Date --track origin/CSV_Date
```

## 2.2 start docker containers  

```sudo docker compose -f docker-compose-local.yml up -d```


# 3. Install nginx for https

https://lists.cloudokyo.dev
https://mailtrain.cloudokyo.dev
https://sbox-mailtrain.cloudokyo.dev