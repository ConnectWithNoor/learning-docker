**Assuming that this directory contains a basic golang application, and we want to dockerize it.**

1. Create a Dockerfile in the root of the project directory.
2. Golang is a compiled language, so we need to compile the application isnide the docker image and then we can run the binary.
3. Run the `docker build -t api-golang:0 .` command to build the image. -t is the name given to the image, and 0 is the tag/version number.

4. The tutorial has a `multi-stage build`, which is a good practice to keep the image size small. The first stage is to build the application, and the second stage is to run the application.

5. **This Dockerfile might not work before I didn't check it with the go application. so it's better to visit the tutorial `(root readme)` at 1:50:00 to learn about the multi-stage.**
