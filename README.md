### Firstly check if you are installed on your machine python, pip and docker, if don't have install install these from:
https://docs.docker.com/engine/install/ubuntu/ <br />
https://linuxize.com/post/how-to-install-python-3-7-on-ubuntu-18-04/ <br />
https://www.serverlab.ca/scripting-programming/install-python-pip-on-ubuntu-19-04/

### Install the git package
sudo apt install git

### After installed above dependencies, check the versions
docker --version <br />
python --version <br />
pip -V / pip3 -V

### Check the docker status
sudo systemctl status docker

### Check docker images/containers
sudo docker images <br />
sudo docker ps -a

### Clone this repository on your local machine
git clone https://github.com/mihaivirlan/docker-hello-world.git <br />

### Check on your computer if repository was cloned
ls -l

### Move in new cloned repository
cd /path_to_inside_your_new_cloned_repo

### Install pymondo dependency
sudo pip3 install pymongo

### Run mongo image if you've it locally, otherwise mongo image will be pulled from docker hub
sudo docker run --rm -d -p 27017:27017 mongo ("--rm" argument will remove the container when you'll stopped it) <br />
sudo docker images <br />
sudo docker ps (and after execute this command you should see that the mongo container run on the port 27017)

### Run the code from app.py file, for this you must open the folder in visual studio code editor for example, move into app.py file and click the button named Run Python File in Terminal, which should be in the top right in VSC editor

After that, you should see on the command output something like: <br />
"{'_id': '4a511d37-0f15-47b8-80cd-732b6ca94caf', 'payload': 'f534de81-b9c6-4a97-ae33-dddfb1263217', 'field2': '1610448825'} <br />

This means that data is inserted in your mondo database after each run from the app.py file <br />
more exactly, after each manually run from app.py, in mongo db will be writed/inserted another 5 objects, <br />
and so on every run.

### Finally, stop/remove the container/image
sudo docker stop CONTAINER_ID <br />
sudo docker ps -a <br />

sudo docker images <br />
sudo docker rmi mongo <br />
sudo docker images <br />

To remove all images, run: <br />
sudo docker rmi $(docker images -q)


