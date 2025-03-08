# docker build -t my-react-app .
    [this command is used to build the docker image for current folder]
    -t - stands for "tag.".my-react-app is the name of the image that will be created.
    my-react-app - builded image name.
    . - for pointing current directory

# docker run -p 5173:5173 my-react-app
    run - for runing the image
    -p - used for mapping image port to local port    

# docker run -p 3000:3000 -v "$(pwd):/app" -v /app/node_modules -e WATCHPACK_POLLING=true my-react-app  
    -v stands for volume mount. keep track of local change
    $(pwd) is a shell command that returns the current working directory.
    /app is the path inside the container where the volume will be mounted.
    -v /app/node_modules: we are creating new volume for node modules.
    -v /app/node_modules: This volume mount ensures that the node_modules directory inside the container (/app/node_modules) is not overwritten by the host machine's node_modules directory.
    -e - environment variable
    -e WATCHPACK_POLLING=true - for nodemon

# docker tag my-react-app toolbox546/my-react-app
    The docker tag command is used to create a new tag for an existing Docker image
syntax: docker tag <source-image> <target-image>

# docker push toolbox546/my-react-app
  This will upload the image to the Docker Hub account toolbox546 under the my-react-app tag.

                         