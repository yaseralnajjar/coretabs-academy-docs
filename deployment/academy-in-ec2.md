# Deployment on VPS

## Docker

### What is Docker ?

If you do NOT know what Docker is, it is better to watch this first:

[https://www.youtube.com/watch?v=YFl2mCHdv24  
](https://www.youtube.com/watch?v=YFl2mCHdv24

)

### What is docker-compose ?

docker-compose is a tool to orchestrate multiple apps in a simple manner, this guide walks you through the basics of docker-compose:

[https://www.youtube.com/watch?v=Qw9zlE3t8Ko](https://www.youtube.com/watch?v=Qw9zlE3t8Ko)

### What folders should we have after the deployment ?

Running `ls /var/` should give you:

```text
academy  academy-media  discourse  live-demos  academy-db  
```

## Deploy the Academy

### **Grabbing the academy**

The academy repository is located at: [https://github.com/Alhakem/coretabs-academy](https://github.com/Alhakem/coretabs-academy)

You can use `git clone` to download the repository:

```text
git clone https://github.com/Alhakem/coretabs-academy /var/academy
```

You will need then to go into the clone repository directory:

```text
cd /var/academy/
```

### **Adding secrets**

[Please refer to configuring the academy docs here](/yaseralnajjar/coretabs-academy-docs/blob/master/configurations/academy_ec2.md), to know more about the secrets files.

### **Running the academy**

Simply pull the repository, then run docker-compose on docker-compose.production.yml:

```text
docker-compose -f docker-compose.production.yml up -d
```

You can check the status of the containers by:

```text
docker ps
```

Sample output:

```text
CONTAINER ID        IMAGE                 COMMAND                  CREATED             STATUS              PORTS
f60081a9e110        academy_app           "sh -c 'gunicorn --b…"   7 days ago          Up 7 days           0.0.0.0:8000->8000/tcp                        coretabs_academy_django_api
2adf3943b44a        academy_spa           "sh -c 'yarn start'"     7 days ago          Up 7 days           0.0.0.0:8001->3000/tcp                        coretabs_academy_spa
ddbbfd15dce1        postgres              "docker-entrypoint.s…"   7 days ago          Up 7 days           0.0.0.0:5432->5432/tcp                        postgres
```

You will need to open `8000` and `8001` ports in your inbound rules \(in your server security settings\).

So, you will have:

* API url: [http://ec123.us-east-2.amazonaws.com:8000](http://ec123.us-east-2.amazonaws.com:8000)
* SPA url: [http://ec123.us-east-2.amazonaws.com:8001](http://ec123.us-east-2.amazonaws.com:8001)
* DB connection string: `postgres://app_user:MySup3rPassword!@ec123.us-east-2.compute.com:5432/app_db`

### Updating the academy

**What if I wanna update/rebuild the image and the container ?**

Just add the required flags:

* force-recreate: recreate the container
* build: build the image

```text
cd /var/academy
git pull
docker-compose -f docker-compose.production.yml up --force-recreate --build -d
```

