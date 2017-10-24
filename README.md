## Automated build and deploy pipeline 
###### for the deeone image recognition container, found here:
```
https://hub.docker.com/r/deeone/tensorflow-object-detection/tags/
```
Note that you will need version 1.2.1-py3 of this image pulled locally before you build:
```
$ docker pull deeone/tensorflow-object-detection:1.2.1-py3
```
Then, run the Dockerfile (you must be in the base dir of this cloned repo) as such: 
```
$ docker build . -t joydeep/tensorflow:1.0.0
```
The build will take a few minutes to clone the repo, and it will be placed in /notebooks/models of the final build of the container.

Finally, to run the container, type (make sure run.sh has +x permissions):
```
$ ./run.sh 
```
The jupyter notebook will be exposed on port 8889 of the docker host, and can be accessed at:
```
http://localhost:8889
```
Note that you will need to copy and paste the token ID from the terminal which instantiated the container with the run.sh script. The token will look like:
```
token=95656385c1159df81bf7b1a03bd21ab3fb746f65940cb421
```
Just copy the numbers/letters after the equals sign and enter them into the jupyter login prompt within your browser.

To enter (via root bash shell) the container after it starts, type:
```
$ docker exec -it joydeep_imagaiServer_1 bash
```
