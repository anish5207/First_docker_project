# IIEC RISE DOCKER PROJECT 2020
This repository is made up for docker project using this you can configure a infrastructure for wordpress and mysql. 

# Docker :
Docker is one of the revolutionary technologies based on the containerization technology created by Solomon Hykes officially released on 7th March 2013. It is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy it as one package. By doing so, thanks to the container, the developer can rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code. Docker is designed to benefit both developers and system administrators, making it a part of many DevOps (developers + operations) toolchains. For developers, it means that they can focus on writing code without worrying about the system that it will ultimately be running on. It also allows them to get a head start by using one of thousands of programs already designed to run in a Docker container as a part of their application. For operations staff, Docker gives flexibility and potentially reduces the number of systems needed because of its small footprint and lower overhead.

# Introduction:

This infrastructure contains a complete setup for wordpress with mysql server inside the docker container.
WordPress is an online, open source website creation tool written in PHP. But in non-geek speak, it’s probably the easiest and most powerful blogging and website content management system 

# What is the need of docker ??

   * When normally we do this it takes a lots of time to set up the environment for these servers , for installation            ,configuration & many more!!
   * So, you can launch whole environment in just one click & can focuse on developing part except these things.
   * you can also share your environment with your team mates by just cloning the container & by creating a image from          it.
# Software Requirements:

   * Following are the pre-requisites to set-up the infrastructure: *
1. I am using RedHat Enterprise Linux on top of Windows using Oracle Virtual Box. also I have also installed Docker Software in it. 
   To start docker services permanently ```systemctl enable docker```.
2. We need to install the docker-compose software inorder to use it. To install docker- compose, follow the steps: * *Go to google --> In the search box search ```docker compose rpm``` --> Choose `Install Docker compose` --> Based on the base OS select whether Mac, Windows or Linux etc. --> Copy the command and paste it in the terminal of the base OS.
3. Pull the images from [docker image registry](hub.docker.com)
 - Pulling MySQL Image: Use `docker pull mysql:5.7` to download **MySQL version 5.7** image. I have used version 5.7 as it is considered the most compatible version with RHEL 8.
 - Pulling Wordpress Image: Use `docker pull wordpress:5.1.1-php7.3-apache` to download  **wordpress:5.1.1-php7.3-apache** image. I have used this version as it comes with php and apache server. 
 

 


# Steps:

 * Step 1:

    * Clone this repository or download it in your computer .
    * The directory structure should be like this:
        mycompose:-
           ```
             docker-compose.yml
           ```
           (and can be other files) 

  * Step 2:

     * check the version of docker-compose by this command:
            ``` docker-compose version ```
     * Now you should be in mycompose directory because in this directory we have our docker-compose.yml file .
        Now run this command :
             ```docker-compose up -d ```
     *  All the services will be run in background inside the docker containers.(because we used detach option in                 command).
   
   * Step 3:

      * check ip address of your system by ifconfig command.
      * It will give you many ip address but you have to concern about system's main network card.
      * for Example : `192.168.40.130` this is your system's id.

   * Step 4:

      * Go in your browser type this url in order to access web pages from web server: `http://192.168.40.130:5000/`#(It                 will give you index file which is written in php.)
      * Now for accessing phpmyadmin for managing mysql database write this url: `http://192.168.40.130:8000/`
      * Note : `here 5000 & 8000 are port no.` that should be free in your system if they are not then you can change by                 going inside the `docker-compose.yml` file. 
     

# References:

   ## I learnt this technology totall free of cost in YouTube.Under IIEC-RISE 1.0 Campaign

Youtube link (https://www.youtube.com/playlist?list=PLAi9X1uG6jZ30QGz7FZ55A27jPeY8EwkE)
