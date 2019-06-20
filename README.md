# CarStore Project

1. Download Docker from the [official website](https://www.docker.com) and after that install the docker.
3. Download the docker-compose.yml file and code folder from this github repository.
4. Create a folder and place the docker-compose.yml file in that folder.
5. Open Command Prompt and go inside the folder with the docker-compose.yml file and after that open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.:
```
docker-compose up -d
```
6. Place the code folder in your container with this command: 
```
docker cp code <container name bitnami>:/opt/bitnami/magento/htdocs/app
```
7. Enter in your cointainer. First, you have to get the name of the container: 
```
docker ps
docker exec -it <container name bitnami> bas
```
8. Go inside the /htdocs/ folder:
```
cd /opt/bitnami/magento/htdocs/
```
9.Unlink /app/etc:
```
unlink ./app/etc
cp -r /bitnami/magento/htdocs/app/etc app/etc
```
10. Enable the module
```
bin/magento module:enable Dejan_NovModul
bin/magento setup:upgrade
bin/magento setup:di:compile
```
11. **Open [this link](http://localhost/dejan/index/index/) to view the result.**

