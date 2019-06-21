# CarStore Project

*This is website project that is created in Magento eCommerce platform and Docker.*

To be able to see the result of this project you need to do the following basic steps:
- Download and install the **Docker.** You can download the Docker from the [official website](https://www.docker.com).
- Download the **docker-compose.yml** file and **code** folder from this github repository.

## How to setup: 
1.Create a folder and place the docker-compose.yml file in that folder. Open Command Prompt and go inside the folder with the docker-compose.yml file, then run the command bellow. After that open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.:
```
docker-compose up -d
```
2.Get the name of container:
```
docker ps
```
3.Place the code folder in your container with this command: 
```
docker cp code <container name bitnami>:/opt/bitnami/magento/htdocs/app
```
4.This command will enable you to execute commands inside the container.
```
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
7.Enable the module:
```
bin/magento module:enable Dejan_NovModul
bin/magento setup:upgrade
bin/magento setup:di:compile
```
8.After the completion of the steps above, open the link below in your browser to see the result.
```
http://localhost/dejan/index/index
```
###### Click [here](https://magento.com) for more info about **Magento eComerece platform.**
###### Click [here](https://www.docker.com/) for more info about **Docker.**

