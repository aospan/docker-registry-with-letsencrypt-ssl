# Start local docker registry with SSL. Obtain certificate from letsencrypt automatically 

NOTE: change 'repo.jokersys.com' to your domain name in docker-compose.yml file

For starting need to run following command:

`docker-compose up`

need to wait (about 2-3 minutes while dh params generated). You will see following messages:

```
lets-nginx_1  | Generating DH parameters, 2048 bit long safe prime, generator 2
lets-nginx_1  | This is going to take a long time
...
lets-nginx_1  |  - Congratulations! Your certificate and chain have been saved at
lets-nginx_1  |    /etc/letsencrypt/live/repo.jokersys.com/fullchain.pem. Your cert
lets-nginx_1  |    will expire on 2017-01-01. To obtain a new or tweaked version of
lets-nginx_1  |    this certificate in the future, simply run certbot again. To
lets-nginx_1  |    non-interactively renew *all* of your certificates, run "certbot
lets-nginx_1  |    renew"
```

obtained certificates will be placed into './letsencrypt' folder. Docker registry files will be placed into './registry' folder.

now you can try to push any images to this docker repository with following command:

`# docker push repo.jokersys.com:5000/ubuntu`

you will see success message:
```
The push refers to a repository [repo.jokersys.com:5000/ubuntu]
0cad5e07ba33: Pushed 
48373480614b: Pushed 
055757a19384: Pushed 
c6f2b330b60c: Pushed 
c8a75145fcc4: Pushed 
latest: digest: sha256:463b797bb7cb49e6df205d51479425adbac1d122dac5922cf6bad9277fe7dfbe size: 1357
```
