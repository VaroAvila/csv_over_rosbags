# csv_over_rosbags

This is a simple ROS2 node created to address the lack of compatibility of rosbags to export data in certain applications by recording and storing ROS2 topics' real-time data in a .csv file.

In this case, it is customized to record position and orientation data (specifically, only some variables from the topic amcl_pose) from an agent in a Navigation 2 system and store the information in a .csv file, but it can be rewritten to record any other data from any topic being published on real-time while this node runs. 

## Use 

To run the node execute the python3 program as you would normally do with any other python executable (python3 + program_name.py), and add in the same command line as parameters the topic you want to record from, in this case "/amcl_pose", and the path to store the .csv file with your information.

### E.g.: 

python3 amcl_pose_csv_writer.py /amcl_pose /path/to/output.csv


As long as the program runs it will record any information received from the published topic, and won't record anything if it is not receiving any data. The data recording will be stopped only after finishing the program. 

In case you modify the program, the /amcl_pose should be substituted by the name of the topic you want to record after adapting the code for your application (If you don't modify the program, you can still use a different topic name in the command line when executing the program as long as it is a topic of the type PoseWithCovarianceStamped from GeometryMsgs).

