# Docker

I will talk about ---->
------------------


what is docker ?

what is container ?

what is virtualization ?

what is hypervisor ?


Difference between containerization vs virtualization ?

who is Docker for ?

What is docker image ?

What is a docker container ?

What is docker registry ?

What is docker client ?

What is a docker deomen ?

What is a docker namespace ?

---------------------------------------------------------------------------------------------------------------------------------------------

If we have been developping software for a While you have probably come across this situation ->where your application works on your development machine but doesnt somewhere else !! -->

Can you think of three reasons why this happens ??


The reasons is :
---------------

1: one or more files missing.

2: if the target machine running a different version of software that your application needs, lets say your application needs node version 14
but the target machine is running node version 9.

3: and this can happen if the configuration settings like environment variables are different across these machines.

So Docker comes to the rescue -->

We can easly package up our application with everything it needs and run it anywhere on any machine with docker, so if your application needs a given version of node and MongoDb all of these will be included in your applications package, now we can take this package and run it in any machine that runs Docker so if it works on your development machine is's definitely going to work on your test and production machines.

-->If someone joins your team they dont have to spend half a day or setting up a new machine to run your application they dont have to install and configure all these dependencies, they simpley tell docker to bring up your application and docker it self will automatically downloand and run these dependencies inside an isolated environement called a container.

and this is the beauty of Docker this isolated environment allows multiple applications use different version of some software side by side,
so one application may use node version 14 and another application may use node version 9, both these application can run side by side on the same machine without messing each other so this how docker allows us to consistently run an application on different machines.

There is one more benefit --> When we are done with this application and dont want to work on it anymore, we can remove this application and all its dependencies in one go, without Docker as we work on different projects our development machine gets cluttered with so many libraries and tools that are used by different applications and then after a while we dont know if we can remove one or more of this tools because we are always afraid that we are would miss up with some appication so with docker we dont have to worry about this because each application runs with its dependencies inside an isolated enviroment so we can safely remove an application with all its dependencies to clean up our machine.

is not that great!!

yes 

---------------------------------------------------------------------------------------------------------------------------------------------


What is Docker :
--------------

Docker is an open source platform that enables developers to build, deploy, run, update and manage containers—standardized, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.


(Docker is a platform for building , running and shipping applications)


<img width="668" alt="Screen Shot 2023-02-02 at 11 00 25 AM" src="https://user-images.githubusercontent.com/87101785/216293831-46b228de-6f4c-4bfa-a7ba-f2b855ab0b6e.png">



An application running in a container is isolated from the rest of the system and from other containers

---> every application that will run in every container it will be isolate from others (other containers) it will be like that every application run in different operationg system  (but this is wrong  because we have one operating system at that time)

--> we can run a lot of containers in just one operator system by using Docker.

(Multiple docker containers can be run on the single operating system simultaneously you can manage those containers with docker )

--> Docker is a container management service.


What is container :
-------------------


A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.

(container is an isolated environment for running an application).

one of the questions that often comes up is how are containers different from virtual machines or VM ?

What is the differences between containers and virtual machines ? 

so the differences is : -->

Virtual machine is an abstraction of machine (physical machine), for example we can have a Mac and on this Mac we can run two virtual machines
one running window and the other running linux by using a tool called hypervisor.

with virtual machine we can run applications in isolation so inside a physical machine we can have two virtual machine each running a completely different application and each applicaton has exact dependencies it needs, so application one may use node version 14 and MongoDb version4 while application two may use node version 9 and MongoDb version 3 all this are running on the same machine but in different isolated environments that is one of the benifits of virtual machines but there are a numbers of problems :--> virtual machines are slow to start....

containers also give us the same kind of isolation so we can run multiple applications in isolation but they are more lightweight they dont need a full operating system in fact all containers on a single machine share the operating system of the host that means we need to license patch and monitor a single operating system, also because the operating system has already started on the host a container can start up pretty quickly and also this container dont need a slice of the hardware resources on the host so we dont need to give  a specific number of CPU cores or a slice of memory or disk space so on a single host we can run tens or even hundreds of containers side by side .









--> A way to package application with all the necessary dependencies and configuration, so our application will be portable, easly shared and moved arroud.

Where do containers lives:
--------------------------


Must be some kind of storage for this containers, so that you can share them and move them arround!


- container live in a container repositories

- many companies have there own private repositories where they host or where they store all the containers, to share it between teams..

- there is a public repository for docker (docker hub)

- In docker hub you can find any application container that you want



What is virtualisation :
------------------------

OS virtualization is the use of software to allow a piece of hardware to run multiple operating system images at the same time.

(Having more than one operating system in one server..)


How does virtualisation work ?
------------------------------

Hypervisors take your physical resources (Processor, Ram, Hard disk) and divide them up so that virtual environement can use them .


virtualisation vs containerization :
-----------------------------------


<img width="891" alt="Screen Shot 2023-02-02 at 1 14 42 PM" src="https://user-images.githubusercontent.com/87101785/216323145-623a6ea9-f8d1-4b21-91a9-8d2078c6a009.png">


<img width="891" alt="Screen Shot 2023-02-02 at 1 24 10 PM" src="https://user-images.githubusercontent.com/87101785/216324331-a67c91c0-a061-4064-9ebb-352a00cdd8f2.png">

What is a docker image ?
-----------------------

An image is a read only template with instructions for creating a docker container. you may build, an image which is based on the ubuntu image and sqlServer.

Container :
-----------

container is an image that is running (When i install an application in docker it will be a container )

What is registry :
-----------------

A docker registry stores docker images. docker hub is a public registry that anyone can use 

What is client :
--------------

When you use commande such as docker run, the client send this command to docker 



<img width="891" alt="Screen Shot 2023-02-02 at 1 24 10 PM" src="https://user-images.githubusercontent.com/87101785/216330743-7b321b97-da15-4c04-b97d-5279df946e1e.png">

What is namespaces:
-------------------

Docker uses a technology called namespaces to provide the isolated workspace called the container.When you run a container docker creates a set of namespaces for that container.This namespace provide a layer of isolation.Each aspect of a container runs in a seperate namespace and its access is limited to that namespace.



Docker architecture:
-------------------

-->Lets talk about the architecture of Docker to understand how it works !

Docker uses a client server architecture so it has client component that talks to a server component using a restful API(API – or application programming interface – is a connection between computers or computer programmes and its superpower lies in its ability to allow two different applications to talk to each other.), the server also called the docker engine sits on the background and takes care of building and running docker containers, but technically a container is just a process like other processes running on your computer but it is special kind of process which we are going to talk about soon .

so now as i told you unlike virtual machines containers dont contain a full-blown operating system instead all containers on a host share the operating system of the host, now more accurately all this containers share the kernel of the host (a kernel is the core of an operating system it is like an engine of a care, it is the part that manages all applications as well as hardware resources like memory and CPU).

every operating system has its own kernel and this kernel has different API that is why we can not run a windows application on linux because under the hood this application needs to talk to the kernel of the underlying operating system (that means on a linux machine we can only run linux containers because this containers need linux, on a windows machine however we can run both windows and linux containers because windows 10 is  now shipped with a custom built linux kernel this is in addition to the windows kernel than is always been in windows it is not a replacement soo with this linux kernel now we can run linux applications natively on windows so on windows we can run both linux and windows containers. Our windows containers share the windows kernel and our linux containers share the linux kernel. ) 

What about mac os ?

Mac os has its own kernel which is different from linux and windows kernels and this kernel does not have native support for containers applications so Docker on map uses a lightweight linux virtual machine to run linux containers.





After installing Docker 

Lets talk about your development workflow when using Docker -->

so to start off we take an application it doesnt matter what kind of application it is or how it is built, we take that application and dockerize it which means we make a small change so that it can be run by Docker , How ??!

we just add a dockerFile to it .

A DockerFile is a a plain text file that includes instructions that docker uses to package up this application into an image, this image contain everything our application needs to run (typically a cut down operating system a runtime environment like node or python, it is also contain application files, environment variables ). So we create a Docker file and give it Docker for packagig our application into an image.

Once we have an image we tell docker to start a container using that image so a container as i told you is just a process but it is a speacial kind of process because it has own file system which is provided by the image so our application gets loaded inside a container and this is how we run our application locally on our machine .


How to write a Docker file :
---------------------------

we write instructions for packaging our application 

---> we start from a baseImage this baseImage has a bunch of files we are going to take this files and add additional files to it (for example node image ,debian, alpine ) --> how do i know these names ?  ---> This images are officially published on docker hub


<img width="1227" alt="Screen Shot 2023-02-08 at 10 51 29 AM" src="https://user-images.githubusercontent.com/87101785/217495487-c6d0b03b-5367-4f73-89a3-e592c7179991.png">

if you go to hub.docker.com you can see the official node image do docker hub is a registry for docker images

if you see at docker hub you will see that there are multiple node images, these node images are built on top of different distributions of linux, so linux has different distributions or different flavors used for different purposes-->  now here we can specify a tag using ":" to specify which linux distribution we want to use  here i will use alpine which is a very small linux distribution, so the size of the image that we are going to downdoad and build on top of is going to be very small 



The first line in every docker files is { From : (image name) } --> whatever image you are building you want to base it on other image, in our case we have a javascript application so we are gonna need node image to run our application, so we are gonna need node inside of our container so that you can run your node application instead of basing it on a linux alpine or some other lower image  


<img width="1108" alt="Screen Shot 2023-02-14 at 3 12 32 PM" src="https://user-images.githubusercontent.com/87101785/218763197-e2c4ed3c-4534-4667-a97a-ff0790194ce5.png">


we can anso use RUN for exampla (RUN mkdir -p /home/app ), so using run basically you can execute any kind  of linux command, so you see make directory is a linux commande that creacts /home/app directory, this directory is gonna live inside of the container, so when i start a container from this image this  (/home/app) directory will be created inside of the container and not on my laptop or on the host 


--------Dockerfile---------------------------------------------

FROM node:alpine

---------------------------------------------------------------



--> then we need to copy our application or program files, for that we usethe copy instruction or copy command we are going to copy all the files in the current directory  by writing (copy .) into the app directory that is (/app) into that image so that image has a file system and in that file system we are going to create directory called app


-------Dockerfile-------------------------------------------

FROM node:alpine

COPY . /app

------------------------------------------------------------

--> finally we are going to use the command instruction to execute a command (what commande should be execute here !??)
we will execute our application 

-------Dockerfile-------------------------------------------

FROM node:alpine

COPY . /app_dir

CMD node /app_dir/app.js

------------------------------------------------------------


we can use WORKDIR to specify our app directory 

so when we use WORKDIR instruction all the following instructions assume that we are currently inside the app directory 


-------Dockerfile-------------------------------------------

FROM node:alpine

COPY . /app_dir

WORKDIR  /app_dir

CMD node  app.js

------------------------------------------------------------


--> to tell docker to package our application so we write in the terminal -->  docker build -t app .

so now you might be expecting an image file inside the current directory (you will not find that image in your app directory because the image is not stored there, in fact an image is not a single file --> for how docker store this image is very complicated and we dont have to worry about it )

--> to say all the images on that computer we type    ---> docker images.   | or docker image ls 

This image contains alpine linux node and our application form 

so now we can run this image on any computer running docker 

--> so to run your application by using docker we type --> run app (app is the name of your image )


--> I can go ahead and publish this image to docker hub so anyone can use this image


<img width="948" alt="Screen Shot 2023-02-08 at 11 43 57 AM" src="https://user-images.githubusercontent.com/87101785/217507734-9f10e027-6712-4889-a88a-164feaeeb5e8.png">


now we  can take this image and run it on any computers 

Lets do some tests 

1: search for play with docker -->

<img width="1123" alt="Screen Shot 2023-02-08 at 11 46 03 AM" src="https://user-images.githubusercontent.com/87101785/217508287-d045be6c-e4fa-4d6d-bac0-10f2a75bca6c.png">

2: start a virtual machine :


This virtual machine has an operating system which is linux


<img width="1238" alt="Screen Shot 2023-02-08 at 11 47 08 AM" src="https://user-images.githubusercontent.com/87101785/217508478-0ad2033a-1faf-45f1-8560-ac99c6d1e5e7.png">


if you tape node (you will see that node command not found ) so node is note installed here

<img width="721" alt="Screen Shot 2023-02-08 at 11 49 16 AM" src="https://user-images.githubusercontent.com/87101785/217508873-e98990de-3aeb-48a5-bc2e-a4a8587454ea.png">

but because we have docker in that machine so we can pull and run the image that i published on docker hub 


<img width="710" alt="Screen Shot 2023-02-08 at 11 50 55 AM" src="https://user-images.githubusercontent.com/87101785/217509223-9b58095e-df78-4cc4-8dd9-00af1603abf2.png">

--> to pull the project from docker hub tape --> docker pull codewithmosh/hello-docker (this is the image that create for that project project )


<img width="710" alt="Screen Shot 2023-02-08 at 11 53 58 AM" src="https://user-images.githubusercontent.com/87101785/217509891-da4eca0b-ee2c-4f46-af74-8e6931879b76.png">


Alright docker download this imag, we can verify by tapping --> docker image ls 

<img width="710" alt="Screen Shot 2023-02-08 at 11 55 18 AM" src="https://user-images.githubusercontent.com/87101785/217510214-dfcd34df-e1b0-4bec-9ded-689c1dc956e1.png">


the image add with success 

so now we can run this application exactly the same way we run it in my machine --> docker run codewithmosh/hello-docker


<img width="710" alt="Screen Shot 2023-02-08 at 11 57 38 AM" src="https://user-images.githubusercontent.com/87101785/217510764-a0933d96-b7f2-4c03-af14-8c75b1c8387e.png">


Linux_command (Linux distrubution)
------------------------------------------
Why linux?

Docker is build on basic Linux concepts .

How we can run debian for this machine

we go to docker hun and search fo debian 

In the terminal insteas of runnning docker debian i am going to run docker run ubuntu, now if you have this image locally docker is going to start a container with this image otherwise, is going to pul this image behind the scene and then start a container 

--> commande :   docker run debian 

what will happen after that ?

Docker started a container but because we didnt intract with this container the container stopped 

If you tape --> docker ps -a we can see the stopped containers


<img width="711" alt="Screen Shot 2023-02-10 at 9 57 18 AM" src="https://user-images.githubusercontent.com/87101785/218047916-8589d44b-a42e-4556-92d8-de56a254f62c.png">


so to start a container with interact with it we have to tape --> docker run -it. (so we going to start a container in the interactive mode, and in this container we going to load the debian image which we have locally )


<img width="625" alt="Screen Shot 2023-02-10 at 10 01 11 AM" src="https://user-images.githubusercontent.com/87101785/218048759-ab4ef588-bec1-4bb2-8bc2-8c75759c15e7.png">

Good now what we have here is called a shell --> a shell is a program that takes our commands and passes them to the operating system for execution

Docker file:
------------

Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. This page describes the commands you can use in a Dockerfile.


Docker compose:
---------------
We will talk about docker compose to 

Running Multi-container applications :

🌱1: installing docker compose :


<img width="625" alt="Screen Shot 2023-02-10 at 10 16 59 AM" src="https://user-images.githubusercontent.com/87101785/218052289-a64d359c-62d9-4eaf-a54b-5210478d87ee.png">


As we see here in Mac we alrighdy have a docker-compose, but if you are using Linux there is spesific instructions to follow to install docker-compose.


🌱2: What is docker compose:

Docker compose is a tool for defining and running multi-container Docker applications by using YAML language  (YAML is Yet Another Markup Language)

What is the different between Docker and Docker compose ?

-> Docker , deal with just one container .

->Docker compose didnt deal with just one container (2 or 3 or maybe 10 .. as you like)


🌱3: Docker Compose | Build WordPress with MySQL :

Firstly we create docker-compose.yml file


<img width="981" alt="Screen Shot 2023-02-10 at 10 58 43 AM" src="https://user-images.githubusercontent.com/87101785/218061925-ac496b95-1b8f-4f25-80e1-927735d7777b.png">



we should write the version of the compose docker file 

<img width="466" alt="Screen Shot 2023-02-10 at 11 00 22 AM" src="https://user-images.githubusercontent.com/87101785/218062364-bd3e3e71-4505-4cf0-9ea2-1018f95d204b.png">


   💬 First container description : --> mysql

Then we write services--> that means containers 

first we give a name to our container --> (I choose to name it --> mysql_database)

then put the name of the image here i want (mysql) image

then i add option (restart : always) I told  the Docker if this container close for some reason so do restart )

then enviroment (MYSQL_ROOT_PASSWORD : (write a password) |  MYSQL_DATABASE: wp_db | MYSQL_USER : wp_user | MYSQL_PASSWORD : (write a password))

then volumes: - mysql:/var/lib/mysql (- means that it can take multiple items)


<img width="505" alt="Screen Shot 2023-02-10 at 11 29 37 AM" src="https://user-images.githubusercontent.com/87101785/218069228-fa856070-4dc1-418e-b327-61b97ac475bf.png">

     
     💬 second container description ---> wordpress. (pss, we can find docker compose of some images  in docker hub)
     
for example wordress :

<img width="795" alt="Screen Shot 2023-02-10 at 11 36 19 AM" src="https://user-images.githubusercontent.com/87101785/218071021-8c9cd3f0-8a15-47c0-a6fe-6511c3cc0cb7.png">

     
     
We write the name of our container (wordpress)

depends_on: mysql_database option( I told the docker run second container  just if you are sure that the first container is alrighdy run (i write the name of first container))

image name 

restart: always

ports

Environment

volumes

<img width="795" alt="Screen Shot 2023-02-10 at 11 42 01 AM" src="https://user-images.githubusercontent.com/87101785/218072197-1ab9d98a-00ed-480b-8add-9ca70e9d35a4.png">






Docker Commands:
---------------



--> to see the images           -->  docker images.   or   docker image ls

--> to build image. --> docker build -t (name of your choise to your image)  . (. here means our dockerfile it is in the the current dir)

--> to run a container --> docker container run (give the id or the name  of the image  you build)

---> to see  running containers -->  docker ps

--> To remove images            -->  docker image rm (ids)

--> Get all image ids           -->  docker image ls -q


--> To remove all containers   --> docker container rm -f $(docker container ls -a -q)

--> To remove all images.      --> docker image rm -f $(docker image ls -q )


Volumes | docker :
-------------------


Volumes are the preferred mechanism for persisting data generated by and used by Docker containers

In order to understand what a Docker volume is, we first need to be clear about how the filesystem normally works in Docker. Docker images are stored as series of read-only layers. When we start a container, Docker takes the read-only image and adds a read-write layer on top. If the running container modifies an existing file, the file is copied out of the underlying read-only layer and into the top-most read-write layer where the changes are applied. The version in the read-write layer hides the underlying file, but does not destroy it -- it still exists in the underlying layer. When a Docker container is deleted, relaunching the image will start a fresh container without any of the changes made in the previously running container -- those changes are lost. Docker calls this combination of read-only layers with a read-write layer on top a Union File System.

 

In order to be able to save (persist) data and also to share data between containers, Docker came up with the concept of volumes. Quite simply, volumes are directories (or files) that are outside of the default Union File System and exist as normal directories and files on the host filesystem.





Some ressources:
------------------

https://www.youtube.com/watch?v=DFyPl2cZM2g&list=PLX1bW_GeBRhDkTf_jbdvBbkHs2LCWVeXZ&index=2

Doker vs virtual machine:

https://www.youtube.com/watch?v=5GanJdbHlAA

Create docker-compose and run multiple containers
 
https://www.youtube.com/watch?v=MYV-7ao493k

The Layman's Guide to Linux: Daemons & Init Systems

https://www.youtube.com/watch?v=ydg9KZCCPE0

Full-course Docker:

https://www.youtube.com/watch?v=pTFZFxd4hOI

https://www.youtube.com/watch?v=3c-iBn73dDE


Full-course docker compose

https://www.youtube.com/watch?v=HG6yIjZapSA


https://www.youtube.com/watch?v=YPnXtcR4AqQ&list=PLX1bW_GeBRhDkTf_jbdvBbkHs2LCWVeXZ&index=24


dockerfile:

https://www.youtube.com/watch?v=WmcdMiyqfZs

dockerEngine:

https://www.youtube.com/watch?v=eKj13PsoMNE

Docker networking

https://www.youtube.com/watch?v=bKFMS5C4CG0









---->full devops course

https://www.youtube.com/watch?v=fqMOX6JJhGo

---->A full Devops course on how to run applications in containers

https://www.youtube.com/watch?v=fqMOX6JJhGo

-->Docker full course

https://www.youtube.com/watch?v=p28piYY_wv8&list=RDCMUC2KfmYEM4KCuA1ZurravgYw&start_radio=1&rv=p28piYY_wv8&t=0

-->Docker documentation

https://docs.docker.com/get-started/


