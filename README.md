# CarStore Project

*This is website project that is created in Magento eComerece platform and Docker.*

To be able to see the result of this project you need to do the following basic steps:
- Download Docker from the [official website](https://www.docker.com) and after that install the docker.
- Download the docker-compose.yml file and code folder from this github repository.

## How to setup: 
1.Create a folder and place the docker-compose.yml file in that folder. Open Command Prompt and go inside the folder with the docker-compose.yml file, then run the command bellow. After that open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.:
```
docker-compose up -d
```
2.Place the code folder in your container with this command: 
```
docker cp code <container name bitnami>:/opt/bitnami/magento/htdocs/app
```
3.Enter in your cointainer. First, you have to get the name of the container: 
```
docker ps
docker exec -it <container name bitnami> bas
```
4.Go inside the /htdocs/ folder:
```
cd /opt/bitnami/magento/htdocs/
```
5.Unlink /app/etc:
```
unlink ./app/etc
cp -r /bitnami/magento/htdocs/app/etc app/etc
```
6.Enable the module
```
bin/magento module:enable Dejan_NovModul
bin/magento setup:upgrade
bin/magento setup:di:compile
```
7.After the completion of the steps above, open the link bellow to see the result.
```
http://localhost/dejan/index/index
```
###### Click [here](https://magento.com) for more info about **Magento eComerece platform.**
###### Click [here](https://www.docker.com/) for more info about **Docker.**

