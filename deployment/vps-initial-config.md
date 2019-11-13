# VPS Initial Config

## **Connect to Server \(SSH\)**

If you are on Windows, you can use `Git Bash` to follow along:

```text
ssh -i ssh_key.pem ubuntu@ec123.us-east-2.amazonaws.com
```

* `ssh_key.pem` is the SSH key file required to connect to the server.
* `ubuntu` is the username.
* `ec123.us-east-2.amazonaws.com` is the server DNS.

Then be the root user:

```text
sudo -i
```

\(I will assume you know what you're doing on your server, and you will use create a specific user with the right permissions. [You can watch this video for more info](https://www.youtube.com/watch?v=LbJK48gvXcA&index=4&t=0s&list=PLQlWzK5tU-gDyxC1JTpyC2avvJlt3hrIh)\)

## Install Docker

This will install git as well:

```text
wget -qO- https://get.docker.com/ | sh
```

## **Install docker-compose**

You should see the docker-compose version after running these commands

```bash
apt install curl
curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
docker-compose --version
```



