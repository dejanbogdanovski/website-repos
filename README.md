Download Docker from the official website https://www.docker.com
Install Docker.
Download the docker-compose.yml file and code folder from this github repository.
Create a folder and place the docker-compose.yml file in that folder.
Open Command Prompt and go inside the folder with the docker-compose.yml file and after that run the following command: docker-compose up -d
Open localhost on your web browser and wait for the installation of Magento, if the installation is completed successfully, Magento luma home page will appear.
Run the following command in Command Prompt to get the id of the containers: docker ps
Run the following commands in Command Prompt in the following order: 
Command: docker cp <the full path of the code folder> <container id >:/opt/bitnami/magento/htdocs/app 
Run the following command to get inside the container: docker exec -it <container id> /bin/bash/
Command: cd /opt/bitnami/magento/htdocs/
Command: bin/magento setup:upgrade
Command: unlink ./app/etc
Command: cp -r /bitnami/magento/htdocs/app/etc app/etc
Command: bin/magento module:enable Dejan_NovModul
Command: bin/magento setup:di:compile 
Command: bin/magento setup:static-content:deploy -f
Command: bin/magento setup:upgrade
Command: bin/magento setup:di:compile
Open the following link in your web browser: http://localhost/dejan/index/index/
