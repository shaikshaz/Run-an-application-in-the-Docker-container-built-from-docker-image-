# Run-an-application-in-the-Docker-container-built-from-docker-image
SITUATION: Create and submit a docker file which would have worked docker build and it should a docker images which we could test out.
![image](https://github.com/shaikshaz/Run-an-application-in-the-Docker-container-built-from-docker-image-/assets/154241222/cb917b2d-57e0-4608-95d3-c94ac7a47bdf)

TASK: Here the task to create an image for a python flask application with app.py and requirements.txt for dependencies and to build and run the container image with the port number 3000.Push the image to the docker hub.

ACTION: Make a Docker file directory. Then start with the base image.
1. Use python runtime and create start the base image using python-alphine3.15 which is the lighter version.
FROM python:3-alphine3.15

2.Then set a working directory to /app 
WORKDIR /app

3.Copy the local contents into the directory /app
COPY ./app

4.Install dependencies like flask ,PIP from requirements.txt and run 
RUN pip install -r requirements.txt

5.Expose the app to the port 3000 
EXPOSE 3000

6.To run the base files in the working directory which is index.py as entry point 
CMD python ./index.py 

After setting up the image and the file we need to build the container on the image byrunning few command in the terminal. Where -t is tag which is my user’s name from docker hub shaziashaik1 and my given name.
=>. means its working in the current directory 
=>docker build  -t shaziashaik1/hey-python-flask: latest .
=>Run the app in the detach mode -d and expose to port 3000
=>docker container run -d -p 3000:3000 shaziashaik1/hey-python-flask: latest
=>the output is a container with its ID number.
Requirements: python 3.12 ,Flask

RESULT: Then check the output of the image hello world on the given port number 3000. 
Docker ps -a -To list out the container attributes or details.
Once the container is created in the docker hub, then run the index.py app in the localhost:3000

