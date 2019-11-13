# Postgres

## Getting into the db

```text
docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh
psql academy_db -U academy_user
```

##  Backup database

Inside the postgres container you simply run `pg_dump` like this

```text
docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh
pg_dump -U academy_user -Fc academy_db > /var/lib/postgresql/data/my_new_academy.dump
```

Then copy the file via `scp`

```text
scp -i myssh.pem root@ec2-18-188-100-3.us-east-2.compute.amazonaws.com:/var/academy-db/my_new_academy.dump .
```

##  Restore database

First copy the dumb into the server

```text
scp -i myssh.pem ./my_new_academy.dump ec2-user@ec2-18-222-5-138.us-east-2.compute.amazonaws.com:/home/ec2-user/my_new_academy.dump
```

Then get into the server via ssh

```text
eb.exe ssh staging
```

And restore the db

```text
sudo -i
cp /home/ec2-user/my_new_academy.dump /var/academy-db/my_new_academy.dump

docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh

dropdb -U academy_user academy_db
createdb -U academy_user academy_db --template=template0 --owner=academy_user
pg_restore -U academy_user -d academy_db --clean /var/lib/postgresql/data/my_new_academy.dump
```

##  Migrate your db

```text
docker exec -it $(docker ps -a | grep api- | awk '{print $1}') /bin/sh
python manage.py migrate
```

