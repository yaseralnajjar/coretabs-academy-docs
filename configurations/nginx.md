# Nginx

##  Why nginx

As you noticed, to access the app, you need to specify the port, thus using a full-fledged reverse proxy server like nginx is ideal in this case, [more info about nginx and installing it in this video.](https://www.youtube.com/watch?v=ng5DsxYp-Bk&list=PLQlWzK5tU-gDyxC1JTpyC2avvJlt3hrIh&index=7)

`apt install nginx`

##  **Configure nginx**

Edit the `/etc/nginx/sites-enabled/default` file

```text
vim /etc/nginx/sites-enabled/default
```

Add the proper rules, use your domain name instead of `domain_name`

```text
server {
      listen 80;
      listen [::]:80;

      server_name demos.coretabs.net;

      location /server {
              proxy_pass http://0.0.0.0:8002/;
      }

      location / {
              root /var/live-demos/statics;
              try_files $uri $uri/ /index.html;
      }
}


server {
      listen 80;
      listen [::]:80;

      index index.html index.htm index.nginx-debian.html;

      server_name forums.coretabs.net;
  	
  	location / {
              proxy_pass http://0.0.0.0:4000/;
              proxy_set_header Host $http_host;
              proxy_http_version 1.1;
              proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      }
}

server {
        listen 80;
        listen [::]:80;

        server_name www.coretabs.net coretabs.net;

        location / {
              proxy_pass http://0.0.0.0:8001/;
        }
}

server {
        listen 80;
        listen [::]:80;

        server_name api.coretabs.net;
		
        location / {
              proxy_pass http://0.0.0.0:8000;
              proxy_set_header Host $http_host;
              proxy_http_version 1.1;
              proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }

        location /media {
              alias /var/academy-media;
      }
}
```

##  **Test nginx**

```text
nginx -t
```

Success output

```text
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful
```

##  **Restart nginx**

```text
systemctl restart nginx
```

Now you can configure your DNS CNAME records to reach:

* API: api.domain\_name.com
* SPA: domain\_name.com

