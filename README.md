# How-to-Docker-image-restore
How to Docker image backup and restore

### 1. Container To Image

firset of all, check the Container currently running.
![docker ps](https://user-images.githubusercontent.com/51101183/58443540-6b95c680-812d-11e9-9ed5-f6ce3e1ebe1c.PNG)

named 'test_01'

and put the code at command line:

sudo docker commit -p [CONTAINER ID] [NAME]

"""
sudo docker commit -o test_01
"""
