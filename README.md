# expo-module-windows-starter
contains files and instructions for how to create native modules with expo modules in Windows OS as by default it is not made available for windows. Using linux container on docker.

# Start #
-- choose where you want to start the expo project (make sure docker has access to this directory)
-- In terminal cd into your destination folder, make sure it has docker by typing the command `docker` (if it shows a long list of commands all good)
```
mkdir folderName
cd folderName 
```
-- make a docker-compose.yml file inside your created folder and add the following content :
```
version: '3.8'
services:
  expo-dev:
    image: node:22-alpine
    volumes:
      - .:/workspace
    working_dir: /workspace
    stdin_open: true
    tty: true
```

