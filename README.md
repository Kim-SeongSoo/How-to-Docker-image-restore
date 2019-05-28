# How-to-Docker-image-restore
How to Docker image backup and restore

### 1. Commit Container To Image

firset of all, check the Container currently running.
![docker ps](https://user-images.githubusercontent.com/51101183/58443540-6b95c680-812d-11e9-9ed5-f6ce3e1ebe1c.PNG)

named 'test_01'

and put the code in the command line:

sudo docker commit [CONTAINER NAME] [COMMITED NAME:TAG] (If you do not include the *tag*, it will be marked as *'latest'*)

'
$ sudo docker commit test_01 test_har:0.0
'

You can see that the image is created in this way
![sudo docker commit](https://user-images.githubusercontent.com/51101183/58444244-45265a00-8132-11e9-9f0e-8686b8622b6c.PNG)


### 2. Save The Image

Now let's save the test_har:0.0 image to *tar file*.

put the code in the command line:

sudo docker image save [OPTIONS] IMAGE [IMAGE...] (The option '-o' means 'output')

'''
sudo docker save -o test_har_0_0.tar test_har:0.0
'''

You can see that a file called 'test_har_0_0.tar' is created in the directory.
![docker save](https://user-images.githubusercontent.com/51101183/58444742-87509b00-8134-11e9-8ee6-157ee9bb67dc.PNG)





