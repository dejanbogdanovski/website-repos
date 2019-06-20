# CarStore Project

*This is a website project that has certain goal.*

These are the basic things that you need to do
- Download Docker from the [official website](https://www.docker.com) and after that install the docker.
- Download the docker-compose.yml file and code folder from this github repository.

## How to setup: 
1.Create a folder and place the docker-compose.yml file in that folder.
2.Open Command Prompt and go inside the folder with the docker-compose.yml file, then run the command bellow. After that open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.:
```
docker-compose up -d
```
3.Place the code folder in your container with this command: 
```
docker cp code <container name bitnami>:/opt/bitnami/magento/htdocs/app
```
4.Enter in your cointainer. First, you have to get the name of the container: 
```
docker ps
docker exec -it <container name bitnami> bas
```
5.Go inside the /htdocs/ folder:
```
cd /opt/bitnami/magento/htdocs/
```
6.Unlink /app/etc:
```
unlink ./app/etc
cp -r /bitnami/magento/htdocs/app/etc app/etc
```
7.Enable the module
```
bin/magento module:enable Dejan_NovModul
bin/magento setup:upgrade
bin/magento setup:di:compile
```
8.**Open [this link](http://localhost/dejan/index/index/) to view the result.**

