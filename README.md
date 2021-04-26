# Docker Registry Server


## Features

* Docker Registry
* SSL

## Setup

1. Clone the project
   ```bash
   $ git clone https://github.com/imagine10255/docker-registry-server
   ```
   
2. Verify SSL (https://www.sslforfree.com/)
    ```bash
    $ docker-compose up verify
    ```
   
3. Get verify file in `./verify-public` and verify in `sslforfree`
4. Close the verify web service
    ```bash
    $ docker-compose down
    ```

5. Get ssl file in `./ssl` and run
    ```bash
    $ cat certificate.crt ca_bundle.crt >> _certificate.crt
    ```
   
6. Create the your auth login verify in `./auth/htpasswd`
    ```bash
    $ docker run --entrypoint htpasswd registry:2.7.0 -Bbn your_account your_password > ./auth/htpasswd
    ```   
   

7. Start Docker Registry Server
    ```bash
    $ docker-compose up -d server
    ```

## Login

```bash
$ docker login https://your_domain:8443
```

> typing account, password then show success!

You can push the docker image in your registry


