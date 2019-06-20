# CarStore Project

1. Download Docker from the [official website](https://www.docker.com) and after that install the docker.
3. Download the docker-compose.yml file and code folder from this github repository.
4. Create a folder and place the docker-compose.yml file in that folder.
5. Open Command Prompt and go inside the folder with the docker-compose.yml file and after that run the following command:
```
docker-compose up -d
```
**Open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.**

6. Place the code folder in your container with this command: 
```
docker cp code <container name bitnami>:/opt/bitnami/magento/htdocs/app
```
7. Enter in your cointainer: 
```
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

6. Open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.
7. Run the following command in Command Prompt to get the id of the containers: docker ps
8. Run the following commands in Command Prompt in the following order: 
9. Command: docker cp <the full path of the code folder> <container id >:/opt/bitnami/magento/htdocs/app 
10. Run the following command to get inside the container: docker exec -it <container id> /bin/bash/
11. cd /opt/bitnami/magento/htdocs/
12. bin/magento setup:upgrade
13. unlink ./app/etc
14. cp -r /bitnami/magento/htdocs/app/etc app/etc
15. bin/magento module:enable Dejan_NovModul
16. bin/magento setup:di:compile 
17. bin/magento setup:static-content:deploy -f
18. bin/magento setup:upgrade
19. bin/magento setup:di:compile
20. Open the following link in your web browser: http://localhost/dejan/index/index/
