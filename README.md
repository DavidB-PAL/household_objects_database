### Forked ROS Package: household_objects_database

This is a fork of the ROS Fuerte release of household_objects_database, <br>
from the object_manipulation stack: <br>
https://code.ros.org/svn/wg-ros-pkg/stacks/object_manipulation/branches/0.6-branch/household_objects_database/

The ROS Wiki is incorrect, and the Trunk (Groovy-devel) is now at: <br>
https://github.com/ros-interactive-manipulation/household_objects_database

These fixes & modifications are for using this node as part of the ROS Manipulation Pipeline, for robots other than the PR2. These changes have been tested to not break the simulated PR2 robot in ROS Fuerte Gazebo. <br>
-- David Butterworth, PAL Robotics S.L.
<br>

<br>
**Changelist:**

 - If the connection to the Objects Database fails, print a ROS_WARN message instead of a fatal ROS_ERROR. <br>
The information circulating for this node is incorrect, and the Manipulation Pipeline can be run without the database, however this error message makes users think the Pipeline has failed to load. <br>
The household_objects_database node must be started, because other nodes in the Pipeline require one of its Services. Therefore it can be loaded with an incorrect configuration e.g. wgs36.yaml, and the node will run but without a database. This means you can plan grasps on PointCloud clusters (but not recognized objects) without the hassle of configuring a PostgreSQL database.


