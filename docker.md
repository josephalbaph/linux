Install Docker
```
sudo apt install docker.io
```
Create the docker group.
```
sudo groupadd docker
```
Add your user to the docker group.
```
sudo usermod -aG docker ${USER}
```


https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket
