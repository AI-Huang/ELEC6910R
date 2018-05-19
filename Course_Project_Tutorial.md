# Course Project Tutorial
Author: HUANG, Kan
Date: 2018.4.8
## Enviroment
The newest version of regarding softwares is recommended.
[ROS: Kinetic](http://wiki.ros.org/kinetic)
[V-REP: 3.5.0 PRO EDU](http://coppeliarobotics.com/files/V-REP_PRO_EDU_V3_5_0_Linux.tar.gz)
Plugins(Please git clone them from the latest master):
[vrep_ros_bridge](https://github.com/lagadic/vrep_ros_bridge)
[vrep_ros_interface](https://github.com/CoppeliaRobotics/v_repExtRosInterface)
Platform: Ubuntu 16.04 LTS

For vrep_ros_bridge, if you choose V-REP 3.5.0 PRO EDU, please notice:

>If you are using the last version of V-REP (V3_4_0_Linux) and you are under Ubuntu 14.04 you have to download an older version of V-REP (V-REP_PRO_V3_3_2_64_Linux for example) and copy paste the file compiledRosPlugins/libv_repExtRos.so from here. If you are using Ubuntu 16.04 and ROS Kinetic you will need to compile the plugin by yourself: Copy the folders vrep_plugin and vrep_common from home/user/Desktop/V-REP_PRO_V3_3_2_64_Linux/programming/ros_packages in your catkin_ws/src and do a catkin_make. You will find in devel the file libv_repExtRos.so. You will need to copy it in the root of the new V-REP Folder.

which means, besides **V-REP: 3.5.0 PRO EDU** you also need to download **V-REP_PRO_EDU_V3_3_2_64_Linux.tar.gz**, see *→ Previous versions of V-REP are available here* in the http://www.coppeliarobotics.com/downloads.html or http://www.coppeliarobotics.com/previousversions.html.
Direct link: http://coppeliarobotics.com/files/V-REP_PRO_EDU_V3_3_2_64_Linux.tabr.gz
Or you can access it on shared Course Google Drive, it's in root/Softwares

### Potential dependency problems:  
fatal error: opencv2/opencv.hpp: No such file or directory  
sudo apt-get install libopencv (https://askubuntu.com/questions/656461/where-is-opencv-installed)  

opencv2/photo/photo.hpp: No such file or directory  
sudo apt-get install libopencv-dev (https://stackoverflow.com/questions/35281312/fatal-error-opencv2-photo-hpp-opencv-3-0-install)  
Install OpenCV  

The above environment is test by TA. If you have any problems, please contact kan.huang.hkust@gmail.com | kan.huang@connect.ust.hk

## Tutorial
Here are some useful links for you.  
The hyperlinks above, which containing the installation tutorials, and
[Ros Bridge Installation test](http://wiki.ros.org/vrep_ros_bridge#Installation_test)  
Pay attention, since installation of vrep_ros_bridge uses catkin_make, and ROS Interface plugin for V-REP uses catkin build, you can create different catkin workspaces for them, refer to this article [Create a temporary catkin workspace for ROS Interface](http://analuciacruz.me/articles/RosInterface_kinetic/). Note! This is just an example for creating tmp workspace, don't use her git clone. Use the latest one:
```
git clone https://github.com/CoppeliaRobotics/v_repExtRosInterface
```

put the cloned vrep_ros_interface repo in your new workspace like:  
quickstart_ws/src  

some problem catches:
1.
Cannot find V-REP installation.  Please set the VREP_ROOT environment
  variable to point to the root of your V-REP installation.
to deal with:
```
export VREP_ROOT=YOUR_VREP_3_5_PATH
# Mine is ${HOME}/V-REP_PRO_EDU_V3_5_0_Linux
```
2.
runprogram('xsltproc', '-o', output('reference.html'), rel('xsl/reference.xsl'), input_xml)
  File "/home/huangkan/quickstart_ws/src/vrep_ros_interface/external/v_repStubsGen/generate.py", line 50, in runprogram
    runsubprocess(what, [what] + list(args))
  File "/home/huangkan/quickstart_ws/src/vrep_ros_interface/external/v_repStubsGen/generate.py", line 38, in runsubprocess
    child = subprocess.Popen(args)
  File "/usr/lib/python2.7/subprocess.py", line 711, in __init__
    errread, errwrite)
  File "/usr/lib/python2.7/subprocess.py", line 1343, in _execute_child
    raise child_exception
OSError: [Errno 2] No such file or directory
to deal with:
sudo apt install xsltproc

Remember, we only need a temporary catkin workspace to compile the source files of vrep_ros_bridge and vrep_ros_interface, because we just need the library files(*.so), which should be copied into root path of vrep_3.5.0_edu for it to load.
## Demo
After configing the environment, run
```
roscore
```
first.
And in another terminal, run(cd to VREP_ROOT)
```
./vrep.sh
```
You should see the loading details of plugins, including ROS Bridge and ROS Interface.
```
huangkan@Y480:~/V-REP_PRO_EDU_V3_5_0_Linux$ ./vrep.sh
Using the default Lua library.
Loaded the video compression library.
Add-on script 'vrepAddOnScript-addOnScriptDemo.lua' was loaded.
Simulator launched.
Plugin 'MeshCalc': loading...
Plugin 'MeshCalc': load succeeded.
Plugin 'BlueZero': loading...
Plugin 'BlueZero': warning: replaced variable 'simB0'
Plugin 'BlueZero': load succeeded.
Plugin 'BubbleRob': loading...
Plugin 'BubbleRob': load succeeded.
Plugin 'Bwf': loading...
Plugin 'Bwf': load succeeded.
Plugin 'Collada': loading...
Plugin 'Collada': load succeeded.
Plugin 'ConvexDecompose': loading...
Plugin 'ConvexDecompose': load succeeded.
Plugin 'CustomUI': loading...
Plugin 'CustomUI': warning: replaced variable 'simUI'
Plugin 'CustomUI': load succeeded.
Plugin 'DynamicsBullet-2-78': loading...
Plugin 'DynamicsBullet-2-78': load succeeded.
Plugin 'DynamicsBullet-2-83': loading...
Plugin 'DynamicsBullet-2-83': load succeeded.
Plugin 'DynamicsNewton': loading...
Plugin 'DynamicsNewton': load succeeded.
Plugin 'DynamicsOde': loading...
Plugin 'DynamicsOde': load succeeded.
Plugin 'DynamicsVortex': loading...
Plugin 'DynamicsVortex': load succeeded.
Plugin 'ExternalRenderer': loading...
Plugin 'ExternalRenderer': load succeeded.
Plugin 'ICP': loading...
Plugin 'ICP': warning: replaced variable 'simICP'
Plugin 'ICP': load succeeded.
Plugin 'Image': loading...
Error with plugin 'Image': load failed (could not load). The plugin probably couldn't load dependency libraries. For additional infos, modify the script 'libLoadErrorCheck.sh', run it and inspect the output.
Plugin 'K3': loading...
Plugin 'K3': load succeeded.
Plugin 'LuaCommander': loading...
Plugin 'LuaCommander': warning: replaced variable 'simLuaComm'
Plugin 'LuaCommander': load succeeded.
Plugin 'LuaRemoteApiClient': loading...
Plugin 'LuaRemoteApiClient': load succeeded.
Plugin 'Mtb': loading...
Plugin 'Mtb': load succeeded.
Plugin 'OMPL': loading...
Plugin 'OMPL': warning: replaced variable 'simOMPL'
Plugin 'OMPL': load succeeded.
Plugin 'OpenMesh': loading...
Plugin 'OpenMesh': load succeeded.
Plugin 'PovRay': loading...
Plugin 'PovRay': load succeeded.
Plugin 'Qhull': loading...
Plugin 'Qhull': load succeeded.
Plugin 'RRS1': loading...
Plugin 'RRS1': load succeeded.
Plugin 'ReflexxesTypeII': loading...
Plugin 'ReflexxesTypeII': load succeeded.
Plugin 'RemoteApi': loading...
Starting a remote API server on port 19997
Plugin 'RemoteApi': load succeeded.
```
**
Plugin 'Ros': loading...  
Plugin 'Ros': load succeeded.  
Plugin 'RosInterface': loading...  
Plugin 'RosInterface': warning: replaced variable 'simROS'  
Plugin 'RosInterface': load succeeded.  
**
```
Plugin 'SDF': loading...
Plugin 'SDF': warning: replaced variable 'simSDF'
Plugin 'SDF': load succeeded.
Plugin 'SurfaceReconstruction': loading...
Plugin 'SurfaceReconstruction': warning: replaced variable 'simSurfRec'
Plugin 'SurfaceReconstruction': load succeeded.
Plugin 'Urdf': loading...
Plugin 'Urdf': load succeeded.
Plugin 'Vision': loading...
Plugin 'Vision': load succeeded.
Using the 'MeshCalc' plugin.
Checking for an updated V-REP version...
This V-REP version is up-to-date.

```
In V-REP, load the scene file *env.ttt*.
You can use
```
rostopic list
```
to see the Topics of vrep.
Like
```
rostopic echo /vrep/cmd_vel
```
For controling the Pioneer p3dx robot, type the following in terminal
```
rostopic pub -r 10 /vrep/cmd_vel geometry_msgs/Twist  '{linear:  {x: 1.0, y: 1.0, z: 0.0}, angular: {x: 0.0,y: 0.0,z: 0.0}}'
```
where x stand for the velocity of left wheel, and y for the left.
A [demo video](https://drive.google.com/file/d/1JxcH519VuLYpr4ukUh8mx_vIoU89ZSsR/view) is attached for your information.

Notes: above cmds are only valid after the **simulation is started** (the run button is clicked)

Hints: when you don't know the syntax of command, hit **tab** key in the console.
Passing the command using ROS package: you should work by yourself, its part of the project.

# Acknowledgement
This tutorial is still not so pretified and polished, regarding the outline and maybe also details.  
If you wish to contribute, you can blame it and create issues on GitHub [https://github.com/KellyHwong/ELEC6910R-Public](https://github.com/KellyHwong/ELEC6910R-Public)


