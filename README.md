# Python-Docker-Boilerplate

This is a sample containerized python-flask application. This can be used as boierplate for creating scalable application. 

## Installation

This project contain Makefile, that contains the instructions start and stop in order to start the docker container for this application and stop it. Other then the dockerfiles the important part is hotreloading, that is provided by uwsgi, and the changes are detected by watchman. 

In order to start this app run following command. 

```bash
make start
```

This command will start to kick off docker-compose up -d command. It will build images for the app and nginx. It will be started in container on port 80 and this port is mapped on host OS port 80. After that it will start listening for any change in given directory, and once any change is detected, it will run command touch `uwsgi-reload`.   

In order to stop the containers run following command.

```bash
make stop
```

This command will stop the containers. 

## Installation of watchman and watchman-make

For the file changes to be detected this uses watchman. In order to install watchman visit [Watchman](https://facebook.github.io/watchman/docs/install.html)

If the watchman is not installed using brew then in that case you have to also download file [watchman-make](https://github.com/facebook/watchman/blob/master/python/bin/watchman-make) and place it in /usr/local/bin, and run following command

```bash
sudo chmod 755 /usr/local/bin/watchman-make
```

This will change the permissions in order to make it executable.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](https://choosealicense.com/licenses/mit/)