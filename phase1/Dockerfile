FROM node
WORKDIR /app
# make the editable files below..for better performance, we can copy the package.json and package-lock.json files first and run npm install before copying the rest of the files. This way, if there are no changes to the dependencies, Docker will use the cached layer and skip the npm install step.
# * is used to copy all files that match the pattern. In this case, it copies all files that start with "package" and end with ".json".
COPY package*.json .
#COPY package-lock.json package-lock.json
RUN npm install
#COPY index.js index.js
# COPY . . is used to copy all files and directories from the current directory (on the host machine) to the working directory (in the container). This is useful for copying source code, configuration files, and other assets needed for the application to run.
COPY . .
CMD ["node", "index.js"]
