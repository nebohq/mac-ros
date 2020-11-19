# ROS on Mac

## Setup
1. Install Docker ([installation instructions here](https://docs.docker.com/docker-for-mac/install/))
2. Clone this repository
3. Open `ros.env` 
4. Change `ROS_MASTER_URI=[YOUR ROS MASTER]` to have the url of your ROS master (the format is `ROS_MASTER_URI=http://[IP or HOSTNAME]:11311`)
5. Run `docker-compose up --build`

## Running RViz
1. Run `docker-compose exec ros bash` (`docker-compose up` has to be running)
2. Run `cd ~/catkin_ws && catkin_make && source devel/setup.bash`
3. Run `rosrun rviz rviz`
4. Open your browser to `localhost:8080/vnc.html` and click connect.
5. RViz is now running in your browser.

## Editing your workspace
The workspace folder that gets created on your machine by `docker-compose` is where you can write and edit your packages. It maps to `~/catkin_ws` on the Docker container. However, if you want to run `catkin_make`, do so by creating a bash via `docker-compose exec ros bash` and running `catkin_make` in `/catkin_ws`.

## Installing other packages
Edit the `Dockerfile` line that installs packages and rebuild the container using `docker-compose build`.