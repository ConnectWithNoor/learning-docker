# Use the official image of node from the docker hub
FROM node:19.6-alpine

# Navigate to the /app directory in the container
WORKDIR /app

# Pass the environment variable to the container
ENV PORT 3000
ENV NODE_ENV development

#COPY the package.json and package.lock.json files into the container at /app.
#We only copy these files first because they are less likely to change than the rest of the files and doesn't invalidate the cache, if we copy whole directory, it will invalidate the cache and will take more time to build the image

COPY package*.json ./

# Install the dependencies from the package.json file
RUN npm install

# Now we can copy the rest of the files in local system into the container app directory, it is better to do the step here since the major time taking part of install packages are already done.
COPY ./src .

# Expose the port 3000 to the outside world. This command doesn't change anything on the docker side, it acts as a documentation for the developer to know which port to expose
EXPOSE 3000

# run the app from the package.json script, this is the command that will run inside docker terminal
CMD [ "npm", "run", "dev" ]