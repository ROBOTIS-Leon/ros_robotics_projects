1. If you have problem with centroid.h, copy the include folder to your devel folder and try cmake_make.

2. You should change the haar cascade filter file path in face_tracker_pkg/config/track.yaml

3. If all devices are set correctly, execute the following

$ sudo chmod a+rw /dev/ttyUSB0 (if USB2Dynamixel port was detected as ttyUSB0 | check this by ls /dev/ttyUSB*)
$ roslaunch face_tracker_pkg start_dynamixel_tracking.launch

4. If you don't have dynamixel, only face detection is available

$ roslaunch face_tracker_pkg start_tracking.launch


----------------------------------------------------------------------------------------------------------------

Currently doing:

1. replacing official Dynamixel toolkit - DynamixelSDK with currently-being-used dynamixel_motor package
to make the user be able to use not only the Dynamixel AX-12 but also the other Dynamixel series.
