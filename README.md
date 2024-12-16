# LearnK8s
a note to myself that record my journey to learn k8s using azure and github cicd

## Day 1: Setup Azure 
With copilot, azure is so much ez to use.

Probably shouldnt have started this first. cause the free credit is only valid for 30 days. . .

To setup everythings and make sure it work, i would create a react template and use this to test the function of k8s and github CI/CD pipeline. 

1. Develop Application
- anyway, i created this repo. I create a default template app using npx create-react-app.

```bash
npx create-react-app template
cd template
```

2. Create Docker Image 
- Next, I create a Dockerfile to build the image. 
this is the first time i try docker and what i learn is that "Docker builds images by reading the instructions from a Dockerfile." duh

```Dockerfile
FROM node:14-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

- this define the node js version, create a working directory, copy the package.json and install the dependencies, copy the rest of the files, expose the port 3000 and run the app. simple

- then i build and test the image in my local machine

```bash
docker build -t template .
docker run -p 3000:3000 template
```

- very strighforward.

thats it for today