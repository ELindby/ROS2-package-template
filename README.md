# ROS2-package-template
This is a completely useless project on its own, but contains a template for new packages in ROS2.

# ROS2 Project structure
In workspace folder, have a src folder. In src folder, add a folder for each new package.
I have chosen to divide each package into Nodes, Include, Src

# Notes on renaming packages:
Clean build/install/log folders (clean.sh), and build again.
- project name in CMakeLists.txt
- package_name in launch.py
- <name> in package.xml
- Description in package.xml
- (optional) Edit includepath in .vscode/c_cpp_properties.json

# Notes on running the project
Create an alias for sourcing foxy: sfoxy
        alias sfoxy='source /opt/ros/foxy/setup.bash'
Create an alias for sourcing gazebo: sgz
        alias sgz='. /usr/share/gazebo/setup.sh'
Create an alias for sourcing the build: sbuild
        alias sbuild='source install/setup.bash'
Terminal 1:
- sfoxy
- sgz
- colcon build
- sbuild
- ros2 launch main_package main.launch.py
Terminal 2:
- sfoxy
- rviz2

Can compile specific packages instead of all packages: colcon build --packages-select <pkg_name> --symlink-install
    colcon build --packages-select main_package
