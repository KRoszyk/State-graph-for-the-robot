# State graph for a manipulator with a wood gripper

In this project i created a simulation for picking up and putting away wooden profiles for a robot with gripper containing suction cups.

All needed librtaries are included in requirements.txt file. 

To visualize the robot's movements I used the robotics_exercises repository which was created by user called mbed92. The link is given below.

https://github.com/mbed92/robotics_excercises?fbclid=IwAR0GvMvQ0NNfaaMxftM85txJCv1-sWIT6Zj_Yo6AEWlbqC_2HVRVFinUr8M

# Visualization of state graphs

**State graphs with explanations and names in Polish are presented below.**

![Screenshot](https://github.com/KRoszyk/State_graph/blob/master/images/main_graph.png)

![Screenshot](https://github.com/KRoszyk/State_graph/blob/master/images/robot_graph.png)

![Screenshot](https://github.com/KRoszyk/State_graph/blob/master/images/gripper_graph.png)

**List of used transitions in Polish is presented below:**
- **a1** - Robot w pozycji opuszczonej do podniesienia drewna i platforma w pozycji 1,
- **a2** - Pełny wsuw łapy,
- **a3** - Przyssawki zassały drewno,
- **a4** - Robot w pozycji opuszczonej do odłożenia drewna i platforma w pozycji 2,
- **a5** - Przyssawki podniesione całkowicie,
- **a6** - Pełny wysuw łapy,
- **b1** - Wykrycie drewna przez czujnik,
- **b2** - Ramię robota opuszczone,
- **b3** - Ramię robota podniesione z drewnem,
- **b4** - Ramię w pozycji obróconej i platforma w pozycji 2,
- **b6** - Chwytak otwarty,
- **b7** - Ramię robota podniesione bez drewna, robot skręcony,
- **b8** - Platforma dojechała do położenia docelowego i robot wykonał obrót 2,
- **b9** - brak potwierdzenia z drugiej krańcówki,
- **b10** - brak potwierdzenia z pierwszej krańcówki,
- **e1** - Zanik ciśnienia przyssawek,
- **e2** - Blokada łapy chwytaka,
- **e3** - Potwierdzenie regulacji układu cisnienia,
- **e4** - Potwierdzenie awarii którejś z krańcówek,
- **e5** - Awaria pierwszej krańcówki,
- **e6** - Awaria drugiej krańcówki,
- **e8** - Błąd wysuwu łapy.


# What's inside the code?
There are 4 main files responsible for the operation of the program:
- **main.py** - this file is responsible for communication between the program and the user via the console. It also calls appropriate functions contained in other files.

- **robot_platform.py** - Our robot is placed on a mobile platform, therefore a separate file has been created for the platform and the robot together. This file contains the definition of the graph vertices for the networkx library and the calling of appropriate messages in the console.

- **wood_gripper.py** - This file was created to handle a gripper. It contains the definition of the graph vertices for the networkx library and the calling of appropriate messages in the console.

- **supervisor.py** - This file handles the robot and gripper graph, which allows them to be synchronized.

# Final results
After integrating all files together, program works. Interface to communicate with the user is created in the terminal. You can choose option to follow another states of the graphs or only visualize final movement of the robot.
Visualization only shows the movement of the robot. Robot platform and special gripper weren't added, because of using the ready environment.
The appearance of the ready toolkit for the puma 560 robot after completing the task is presented below.


![Screenshot](https://github.com/KRoszyk/State_graph/blob/master/images/robot.png)
