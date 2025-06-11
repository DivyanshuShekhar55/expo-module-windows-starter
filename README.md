# expo-module-windows-starter
contains files and instructions for how to create native modules with expo modules in Windows OS as by default it is not made available for windows. Using linux container on docker.

## Start ##
-- choose where you want to start the expo project (make sure docker has access to this directory)
-- In terminal cd into your destination folder, make sure it has docker by typing the command `docker` (if it shows a long list of commands all good)
```
mkdir folderName
cd folderName
```

## Using Docker To Create A Linux Container ##
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
-- run the container
```
docker-compose run expo-dev sh
```

## Add The Dependencies ##
-- run the following commands one by one :
```
cd /workspace
npm install -g @expo/cli
npm install -g create-expo-module
npx create-expo-module@latest --local
```

--The command will prompt you for:
    Module name
    Package name
    Description
    Author information
    Whether to include example app

-- exit and close the container once done

## Starting The Container Next Time ##