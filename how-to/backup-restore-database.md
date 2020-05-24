# Backup/Restore Database

### Clean-up Previous Backup

```text
sudo -i
    
rm -f /var/academy-db/my_new_academy.sql.gz
rm -f /home/ec2-user/my_new_academy.sql.gz
docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh
rm -f /var/lib/postgresql/data/my_new_academy.sql.gz
```

###  Backup database

Inside the postgres container you simply run `pg_dump` like this

```text
docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh
pg_dump --username=academy_user --dbname=academy_db --schema=public -T public.pg_* --file=/var/lib/postgresql/data/my_new_academy.sql.gz --no-owner --no-privileges --verbose --compress=4
exit
cp /var/academy-db/my_new_academy.sql.gz /home/ec2-user/my_new_academy.sql.gz
```

Then copy the file via `scp`, **run this command in your local machine**  

```text
rm ./my_new_academy.sql.gz
scp -i myssh.pem ec2-user@SERVERIP:/home/ec2-user/my_new_academy.sql.gz .
sha1sum my_new_academy.sql.gz
```

### Restore database

First copy the dumb into the server

```text
scp -i myssh.pem ./my_new_academy.sql.gz ec2-user@SERVERIP:/home/ec2-user/my_new_academy.sql.gz
```

Then get into the server via ssh

```text
eb.exe ssh staging
```

And restore the db

```text
sudo -i
cp /home/ec2-user/my_new_academy.sql.gz /var/academy-db/my_new_academy.sql.gz
sha1sum /var/academy-db/my_new_academy.sql.gz
# make sure you have same hash here

docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh

dropdb -U academy_user academy_db
createdb -U academy_user academy_db --template=template0 --owner=academy_user
gunzip /var/lib/postgresql/data/my_new_academy.sql.gz
psql --username=academy_user --dbname=academy_db --single-transaction --variable=ON_ERROR_STOP=1 < /var/lib/postgresql/data/my_new_academy.sql
```

## Further Read

### Getting into the db

```text
docker exec -it $(docker ps -a | grep db- | awk '{print $1}') /bin/sh
psql academy_db -U academy_user
```

Exit by running `\q`

