
-----------------------------

#step1

## Top Question :


### - What is Docker?

### -Why do we use Docker?

### - What is Container  & image?

### - What is the difference between docker clinet and docker server?

### - What is Elastic Search and what are its benefits?

### - What is the difference between Elasticsearch and relational databases?


--------------------------------

#step2

### after install docker 

Run the following commands

After the Docker installation is finished, you can ensure the correctness of its installation by entering the following command in the command line:

```bash
docker run hello-world
```


show container

```bash
docker ps , docker ps -a 
```



show images

```bash
docker images
```


stop 

```bash
docker stop idprogram 
```

,........
----------------------------------------

 #step3 

## install redis



```bash
sudo docker run -it redis
```

OR


```bash
sudo docker  run -it hub.hamdocker.ir/redis
```






```bash
docker exec -it  id  sh 
```

```bash
docker exec -it  id  redis-cli
```

```bash
set esm mobina
 ```

```bash
get esm 
```

```bash
docker ps -a  
```

```bash
docker exec -- help 
```

```bash
docker exec -it idcontainer  sh 
```


```bash
redis-cli
```


```bash
set XX 1234 
```


```bash
get XX
```

```bash
docker exec -it idcontainer  redis-cli
```


```bash
//ping from busybox
 sudo docker exec -it dc7ce80db389  ping 8.8.8.8

```


---------------------------------

## Elastic search


#step4 

See the link below

https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html#_stop_and_remove_the_deployment


first install docker compose 

https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

create folder elastic 

```bash
  nvim .env

```


```bash
 nvim docker-compose.yml

```

The contents of the .env

https://github.com/elastic/elasticsearch/blob/main/docs/reference/setup/install/docker/.env

The content of the docker-compose.yml

https://github.com/elastic/elasticsearch/blob/main/docs/reference/setup/install/docker/docker-compose.yml


```bash
docker-compose up -d

```


Before the above command, run the following command



```bash
sudo sysctl -w vm.max_map_count=262144

```


*****************************************************

#step5 

open a browser and navigate to [http://localhost:5601](http://localhost:5601/) to access Kibana
open a browser and navigate to [http://localhost:9200](http://localhost:9200/)to access elastic

-------------------------------------------------------



Written by Mobina Esmaeili
