## Creating a Docker Image
 Instructions for creating a Docker Image
 ---

 ### Create a folder
 ```
 main.c
 Dockerfile
 ```


 ### Create a Dockerfile
 ```
 FROM gcc:latest 
 WORKDIR /app
 COPY main.c .
 RUN gcc main.c -o myapp
 CMD ["./myapp"]
```

### Build a Docker Image
`  docker build -t my-c-app .  `

### Checking Image
` docker images `

### Run Docker Image
` docker run my-c-app `

### Login to dockerhub
` docker login `

### Tag Image with dockerhub username
` docker tag my-c-app yourusername/my-c-app:latest `

### Push Image to Docker hub
` docker push yourusername/my-c-app:latest `

### Pull and Run from Anywhere
```
docker pull yourusername/my-c-app:latest
docker run -it --rm yourusername/my-c-app:latest
```


## Code is pushed to Github
Instructions for pushing code to Github
---

### Create a Project Folder
` world.c `

### Run the program
```
gcc world.c
./a.out
```

### Initializing the Git
` git init `

### Check Status
` git status `

### Add files to Git
` git add . `

### Commit your code
` git commit -m "Initial commit - C program" `

### Connect local repo to Github repo
```
Go to->Github->your repository->Code button 
Copy the HTTPS URL (example)
https://github.com/username/repository-name.git
Now link it
git remote add origin https://github.com/username/repository-name.git
```

### Verify
` git remote -v `

### Push code to Github
```
git branch -M main 
git push -u origin main
```






