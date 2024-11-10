## Enable acces to the USB port

Ensure you add the `--privileged` flag to the Docker run command to grant the container additional privileges, such as access to hardware resources.

Add your current user to the dialout group
```
sudo usermod -aG dialout <username>
```
This grants your user access to serial devices (e.g., `/dev/ttyUSB0`)

Then, enable access to the port

```
sudo chmod a+rw /dev/ttyUSB0
```

## Build Dynamixel SDK
Build the dynamixel_sdk libraries to use methods to read and write inside the motors registers:

```
colcon build --packages-select dynamixel_sdk 
```
## Build the Dynamixel Custom interface
This library generate custom messages and service that will be used by the read_write node

```
colcon build --packages-select dynamixel_sdk_custom_interfaces
```
## Build the Dynamixel example
```
colcon build --packages-select dynamixel_sdk_examples
```

## Run arm_description, necessary to build the KDL chain
```
ros2 launch arm_description display.launch.py
```


## Run kdl_arm_dynamixel
```
ros2 run kdl_arm_dynamixel main_real
```

 