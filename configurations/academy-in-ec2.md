# Academy in EC2

## Cheatsheet

```text
docker exec -it $(docker ps -a | grep api- | awk '{print $1}') /bin/sh
python manage.py migrate

cd /var/academy
git pull
docker-compose -f docker-compose.production.yml up --force-recreate --build -d

sudo docker rmi $(sudo docker images -f "dangling=true" -q)
```

##  How to migrate db and set env variables in API app ?

 **get inside the container**

grab the container id using `docker ps`, then go inside the container

```text
docker exec -it f600 /bin/sh 
```

Where `f600` are the first 4 chars of the container id.

* One-liner command \(no need for searching\)

```text
docker exec -it $(docker ps -a | grep api- | awk '{print $1}') /bin/sh
```

##  **Migrate database**

```text
python manage.py migrate
```

##  **Create an admin user**

```text
echo "from django.contrib.auth.models import User; User.objects.create_superuser('admin', 'admin@example.com', 'admin')" | python manage.py shell
```

##  **Seed database**

`populate` command is followed by \[users\] \[lessons\_per\_module\] \[modules\_per\_workshop\] \[workshops\]

```text
python manage.py populate 10 4 3 2
```

This will create:

* 10 random users
* 4 lessons per module
* 3 modules per workshop
* 2 workshops

##  **Setting env variables**

You can set env variables by modifying `environment` section in `docker-compose.production.yml` file.

* Dont forgets
  * Don't forget to do a rebuild after changing any environment variable.
  * SPA app has its own env vars inside the files `/src/spa/.env.production`.

##  **Setting secrets**

To create those files, just `vim <file-name>` will do.

* Postgresql secrets are in `secrets.db.env` file.
* Django API app secrets are in `secrets.api.env` file.
* If you change any secret related to the db, you will need to execute `rm -rf /var/academy-db` to delete the academy-db mounted folder

##  **Inside the container**

`export` will set an evn variable inside your container.

```text
export var=key
```

You can check your environment variables by

```text
printenv
```

##  Clean up space

You can delete docker dangling images by:

```text
sudo docker rmi $(sudo docker images -f "dangling=true" -q)
```

