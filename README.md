# How-to-Docker-image-restore
How to Docker image backup and restore.('CLI' environmental standard)


***
### 1. Commit Container To Image

firset of all, check the Container currently running.
![docker ps](https://user-images.githubusercontent.com/51101183/58443540-6b95c680-812d-11e9-9ed5-f6ce3e1ebe1c.PNG)

We'll commit the container named __'test_01'__.

and put the code in the command line:


```docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]```[^1]

```
$ sudo docker commit test_01 test_har:0.0
```
(If you do not include the __tag__, it will be marked as __'latest'__)


You can see that the image is created in this way
![sudo docker commit](https://user-images.githubusercontent.com/51101183/58444244-45265a00-8132-11e9-9f0e-8686b8622b6c.PNG)



***
### 2. Save The Image

Now let's save the __test_har:0.0__ image to __.tar file__.

put the code in the command line:

```docker image save [OPTIONS] IMAGE [IMAGE...]```[^2]

```
sudo docker save -o test_har_0_0.tar test_har:0.0
```
(The option __'-o'__ is same as __'--output'__. It means specify file name to save.)

You can see that a file called __'test_har_0_0.tar'__ is created in the directory.
![docker save](https://user-images.githubusercontent.com/51101183/58445600-35117900-8138-11e9-8ff7-afd4d3e2473d.PNG)



***
### 3. Restore

Now let's make sure that the extracted __'test_har_0_0.tar'__ file can be restored to the image again.

put the cod in the command line:

```docker load [OPTIONS]```[^3]

```sudo docker -i test_har_0.0.tar```
(The option __'-i'__ is the same as __'--input'__. It means read from tar archive file.) 

When you enter the code, you will get a message that the image 'test_har: 0.0' has been created.
![docker load](https://user-images.githubusercontent.com/51101183/58445183-a4866900-8136-11e9-85eb-b4c719cfecd5.PNG)

If you enter ```sudo docker images```, 
you can see the image created in the image status as below.
![after loaded docker images](https://user-images.githubusercontent.com/51101183/58445404-7e14fd80-8137-11e9-961b-b309c71fac26.PNG)

Docker Documents: [Docker Documents](https://docs.docker.com/reference/)

[^1]: <https://docs.docker.com/engine/reference/commandline/commit/>
[^2]: <https://docs.docker.com/engine/reference/commandline/save/>
[^3]: <https://docs.docker.com/engine/reference/commandline/load/>



