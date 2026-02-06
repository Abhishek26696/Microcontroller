//Create a Project Folder
<br>
<br>
main.c
<br>
Dockerfile
<br>
<br>
//Create a Dockerfile
<br>
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
<br>
//Build Docker Image
<br>
<br>
docker build -t my-c-app .
<br>
<br>
//checking Image
<br>
<br>
docker images
<br>
//Run Docker Image
<br>
<br>
docker run my-c-app
<br>
<br>
//Login to dockerhub
<br>
<br>
docker login
<br>
<br>
//Tag Image with dockerhub username
<br>
<br>
docker tag my-c-app yourusername/my-c-app:latest
<br>
//Push Image to Docker hub
<br>
<br>
docker push yourusername/my-c-app:latest
<br>
<br>
//Pull and Run from Anywhere
<br>
<br>
docker pull yourusername/my-c-app:latest
<br>
docker run -it --rm yourusername/my-c-app:latest

        
