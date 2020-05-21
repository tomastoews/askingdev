# askingdev

Hello,

This is a little project I started many months ago.
I want it to become a minimal, simple, free, and open source Q&A platform.
Askingdev is primarily targeted towards web developers, but of course, anyone can use it.
I don't expect askingdev to become a well-known website or to gain thousands of users.
It's totally fine if askingdev stays a small website forever.

The reason why I started creating askingdev, is that it has been a wish for a long time to create a project like this and I want to contribute to the open source community. In January 2019 I began using GNU/Linux as my desktop operating system, and I love it now. Today I use it only. I appreciate the work that the open source community has done in the past decades. That's also a reason why I decided to publish askingdev as an open source project. I don't know everything about open source, but I plan on reading more about it. 
I am a person who prefers to do something for the passion and to help others instead of the money.

## The features:
There aren't mind-blowing features yet, but for the beginning that's acceptable.

- Create questions
- Create answers (optionally quote other's answers)
- Categorize questions into rooms
- Add a question to your bookmarks
- Mark an answer as helpful
- Give users a star as an appreciation (I'm not quite sure about this feature. What do you think?)
- Add related information to your user profile. (optional) Such as:
  - What programming languages do you use
  - What tech stack do you use
  - What frameworks do you use
  - What operating system do you use
  - A link to your portfolio/GitHub-page
- Add a profile picture to your user profile

## The ecosystem/architecture/infrastructure
Askingdev could just consist of a frontend, a database, and one giant backend application.
For a very small application, this design is fine.
But as my work on the backend progressed, I realized that it might be a better idea to split up the backend application into several microservices to make it modular and better maintainable.
If a critical error occurred in a big backend application, the entire application would just crash.
That's something I don't want to happen. Also, for example, if one part of a running application needs to be updated, the entire application would need to be restarted. When using microservices, then only one updated microservice needs to be restarted. That also results in improved stability. Therefore I would like the backend to consist of microservices

## These are the used technologies so far:
### Backend:

#### Node.js
- Node.js is a runtime environment for executing JavaScript files and building JavaScript applications.
- Website: https://nodejs.org/en/docs/

#### Express.js
- Express.js is a lightweight framework for Node.js.
- Website: https://expressjs.com/

#### Mongoose
- Mongoose is a MongoDB object modeling, validating, and querying library for Node.js.
- Website: https://mongoosejs.com/

### Database:

#### MongoDB
- MongoDB is a document-oriented database that stores its data in the JSON-format.
- Website: https://www.mongodb.com/

### Frontend:

#### Vue.js
- Vue.js is a JavaScript framework for building Single Page Applications (SPAs).
- Website: https://vuejs.org/

#### Nuxt.js
- Nuxt.js is a framework to render Vue.js SPAs on the server side. (Server-side rendering -> SSR)
- Website: https://nuxtjs.org/

#### Vuetify
- Vuetify is a UI-Framework for Vue.js that implements the Material Design very well.
- Website: https://vuetifyjs.com/

I chose this tech stack because that is what I am most familiar with.

### Tools:

### Docker
- Docker is a containerization software to run an application along with its dependencies isolated in its environment.
- I use it here to run all parts of askingdev's ecosystem inside Docker containers to make the local development easy.
- You may have Node.js 8 installed, but askingdev requires 12.16. To avoid such conflicts, I decided to use this approach.
- Website: https://www.docker.com/

## Deployment (Development, Testing, Staging, and Production)
As far as deployment goes, I plan to use Docker for containerization and K3s (a lightweight version of Kubernetes) for container orchestration.
- K3s: https://k3s.io/
- Documentation: https://rancher.com/docs/k3s/latest/en/

## Contribution
If you would like to contribute to the askingdev project, thank you very much!

I use GNU/Linux. And therefore all scripts in this project are Bash scripts.
If you use Windows, you can install Git Bash to be able to run Bash scripts:
- https://git-scm.com/downloads

The only software you need to install is Docker.
- Download: https://hub.docker.com/editions/community/docker-ce-desktop-windows/
- A tutorial: https://docs.docker.com/docker-for-windows/install/
- Docker is used to run all parts of askingdev inside isolated conainers that communicate with each other.

### Run askingdev locally
1. Make sure you are inside the root direcory of the project. The run:
```bash 
docker-compose up --build
```
This will download all required docker images from DockerHub and then builds all containers on your system.
2. After that you can run tha command without the `--buid` flag:
```bash 
docker-compose up
```

### You don't know what Docker is? No problem! Here are good tutorials to get you started:
- https://docker-curriculum.com/
- https://docs.docker.com/get-started/

[ This README file is not finished yet. ]
