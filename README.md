Select the instance with Ubuntu Image:
Sudo su (To log with root account)
apt-get update 
apt install docker.io (installation of docker)
systemctl start docker (start the docker services)
systemctl enable docker 
systemctl status docker (To the running services of docker)
Clone the repository Git clone https://github.com/Khaira11/getting-started-app.git
Cd getting-started-app 
Create the docker file with following instructions
Vi Dockerfile   ( press  I to edit the file)
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install -–production
CMD [“node”, “src/index.js”]
EXPOSE 3000
:wq
docker build –t todo-app . (create the docker image)
docker images (It will show the image we have created)
docker run -d -p 3000:3000 todo-app (To create the container from the image)
docker ps (To see the running contianers)
PublicIP:3000 (It will display the image as below)
http://localhost:3000 (if you want to see the output on localhost)
