# Use the official image of golang from the docker hub
FROM golang:1.19-buster

# Navigate to the /app directory in the container
WORKDIR /app

# Pass the environment variable to the container
ENV PORT 3000
ENV GIN_MODE development

#COPY the go.mod and go.sum file into the container at /app.
#We only copy these files first because they are less likely to change than the rest of the files and doesn't invalidate the cache, if we copy whole directory, it will invalidate the cache and will take more time to build the image

# single line -> COPY go.mod go.sum ./
COPY go.mod ./
COPY go.sum ./

# Install the dependencies from the go.mod file
RUN go mod download

# Compile the go code into an executable binary. This will create a binary called api-goland from out main.go file, since the application is build, we can save some time when building the image again (cache)
RUN go build -o api-golang

# Now we can copy the binary file in local system into the container api-golang file, it is better to do the step here since the major time taking part of install dependencies are already done.
COPY ./api-goland api-golang

# Expose the port 8080 to the outside world. This command doesn't change anything on the docker side, it acts as a documentation for the developer to know which port to expose
EXPOSE 8080

# run the app using the command
CMD [ "./api-golang" ]