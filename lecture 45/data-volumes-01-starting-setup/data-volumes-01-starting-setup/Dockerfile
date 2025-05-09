FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

# The volume -v ${PWD}:/app mounts your current directory in /app,
# overwriting the node_modules folder that was created during npm install in the Dockerfile. 
# Simply add an anonymous volume to node_modules to preserve it.

# Adding a protection layer for node_modules
VOLUME [ "/app/node_modules" ]

EXPOSE 80

CMD ["node", "server.js"]

# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback -v ${PWD}:/app feedback-node:volumes