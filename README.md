//Create a Project Folder
<br>
main.c

Dockerfile
//Create a Dockerfile
FROM gcc:latest
WORKDIR /app
COPY main.c .
RUN gcc main.c -o myapp
CMD ["./myapp"]
//Build Docker Image
docker build -t my-c-app .
//checking Image
docker images
//Run Docker Image
docker run my-c-app
//Login to dockerhub
docker login
//Tag Image with dockerhub username
docker tag my-c-app yourusername/my-c-app:latest
//Push Image to Docker hub
docker push yourusername/my-c-app:latest
//Pull and Run from Anywhere
docker pull yourusername/my-c-app:latest
docker run -it --rm yourusername/my-c-app:latest

        
