 
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

 