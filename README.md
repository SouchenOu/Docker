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






What is Docker :
--------------

Docker is an open source platform that enables developers to build, deploy, run, update and manage containers—standardized, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.


<img width="668" alt="Screen Shot 2023-02-02 at 11 00 25 AM" src="https://user-images.githubusercontent.com/87101785/216293831-46b228de-6f4c-4bfa-a7ba-f2b855ab0b6e.png">



An application running in a container is isolated from the rest of the system and from other containers

---> every application that will run in every container it will be isolate from others (other containers) it will be like that every application run in different operationg system  (but this is wrong  because we have one operating system at that time)

--> we can run a lot of containers in just one operator system by using docker.

(Multiple docker containers can be run on the single operating system simultaneously you can manage those containers with docker )

--> Docker is a container management service.


What is container :
-------------------


A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.


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



Some ressources:
------------------

https://www.youtube.com/watch?v=DFyPl2cZM2g&list=PLX1bW_GeBRhDkTf_jbdvBbkHs2LCWVeXZ&index=2
