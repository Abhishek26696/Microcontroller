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

//CODE IS PUSHED TO GITHUB
<br>
//Create a Project Folder
<br>
hello.c
<br>
//Run the Program
<br>
gcc hello.c
<br>
./a.out 
<br>
//Initializing the Git
<br>
git init
<br>
//Check Status
<br>
git status
<br>
//Add files to Git
<br>
git add .
<br>
//Commit your code
<br>
git commit -m "Initial commit - C program"
<br>
//Connect local repo to Github repo
<br>
Go to->Github->your repository->Code button
<br>
Copy the HTTPS URL (example)
<br>
https://github.com/username/repository-name.git
<br>
Now link it
<br>
git remote add origin https://github.com/username/repository-name.git
<br>
Verify
<br>
git remote -v
<br>
//Push code to Github
<br>
git branch -M main
<br>
git push -u origin main

        
