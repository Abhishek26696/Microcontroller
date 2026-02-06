//Create a Project Folder
<br>
main.c
<br>
Dockerfile
<br>
//Create a Dockerfile
<br>
FROM gcc:latest
<br>
WORKDIR /app
<br>
COPY main.c .
<br>
RUN gcc main.c -o myapp
<br>
CMD ["./myapp"]
<br>
//Build Docker Image
<br>
docker build -t my-c-app .
<br>
//checking Image
<br>
docker images
<br>
//Run Docker Image
<br>
docker run my-c-app
<br>
//Login to dockerhub
<br>
docker login
<br>
//Tag Image with dockerhub username
<br>
docker tag my-c-app yourusername/my-c-app:latest
<br>
//Push Image to Docker hub
<br>
docker push yourusername/my-c-app:latest
<br>
//Pull and Run from Anywhere
<br>
docker pull yourusername/my-c-app:latest
<br>
docker run -it --rm yourusername/my-c-app:latest

        
