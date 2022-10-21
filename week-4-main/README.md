## Turtlesim and RQT

Before starting a Turtlesim installation we have to make sure that the Terminal is in ROS2 DISTRO.

to check our Terminal's path we need following command.

```
printenv | grep -i ROS
```
![image](https://user-images.githubusercontent.com/92859942/194726415-ebd46ed1-0e2d-431c-a31b-57087042ac9c.png)

## 1. Install Turtlesim

After making sure that you are in ROS2 Distro, install Turtlesim package.for this process command are below

```
sudo apt update
sudo apt install ros-foxy-turtlesim
```
![image](https://user-images.githubusercontent.com/92859942/194727517-30694e69-6829-4e96-a39b-5e2b84630406.png)

to check list of installed packages 

```
ros2 pkg executables turtlesim
```
![image](https://user-images.githubusercontent.com/92859942/194727573-3207423f-2291-4659-8890-385f12f388e9.png)

## 2. Start Turtlesim

to start turtlesim , we need following command 

```
ros2 run turtlesim turtlesim_node
```
the new window will appear 

![image](https://user-images.githubusercontent.com/92859942/194727640-1b2c9a6c-248c-4efe-96fd-4dd24693eb2e.png)

in the terminal we see following message 
![image](https://user-images.githubusercontent.com/92859942/194727704-769480f1-c725-45f8-b744-922378728257.png)

## 3. Use Turtlesim

firstly ,Open a new terminal
secondly, Make sure you are in ROS2 Distro

```
printenv | grep -i ROS
```
![image](https://user-images.githubusercontent.com/92859942/194727808-5736050c-a378-4d4f-9644-f5d0ebe49d2e.png)

after sourcing our files run a new node to control the turtle in the first mode 

```
ros2 run turtlesim turtle_teleop_key
```
![image](https://user-images.githubusercontent.com/92859942/194727871-6ddf4b2b-b704-4f2a-928b-1886b74212c6.png)



## 4. Install RQT

in a new terminal install the required rqt and its plugins
 
 ```
 sudo apt update
sudo apt install ~nros-foxy-rqt*
```

to run rqt 
```
rqt
```
![image](https://user-images.githubusercontent.com/92859942/194727999-4e9f1913-e417-4870-88db-aead15354ff6.png)

## 5. USE RQT 
plugins>services> service celler 
we can see service clear 

for spawn , in service we need to chooose spawn which will create another turtle 
![image](https://user-images.githubusercontent.com/92859942/194728255-6503e9ee-e989-4e9d-b890-12f2f35cf3ba.png)

give new name to the turtle and enter new coordinates,new turtle is appear in the screen 

![image](https://user-images.githubusercontent.com/92859942/194758469-1901d141-1485-47a0-b8c5-1201286a8e46.png)


## Try the set_pen service

give turtle2 a unique pen using the /set_pen service:

we changed the value r=255 and width=5 , if we press arrow key in terminal the size will changes as following 

![image](https://user-images.githubusercontent.com/92859942/194758717-9062b53e-c315-4eaf-a556-2fdc106a6fbb.png)

## 6.Remapping

after entering the following command we can move the turtle2 bye arrows keys 

```
ros2 run turtlesim turtle_teleop_key --ros-args --remap turtle1/cmd_vel:=turtle2/cmd_vel
```


![image](https://user-images.githubusercontent.com/92859942/194758876-eda8b3fe-9687-47d3-9cc6-ebbb58599488.png)

## 7.Close Turtlesim
To stop the simulation, you can enter Ctrl + C in the turtlesim_node terminal, and q in the teleop terminal.

