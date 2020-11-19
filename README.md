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