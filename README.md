# CLP Knoxville Lightwall
The Lightwall at Carnegie Library of Pittsburgh-Knoxville is an interactive light installation that can be controlled from within the CLP network. The Lightwall was built with a REST API. This allows users to easily extend the wall's functionality by writing their own programs that can communicate and control the Lightwall.

Users can learn more about the Lightwall's API and play around with the different pattern-making events by heading to [lightwall.carnegielibrary.org]() any computer in the library.

When not in active interactive mode, the installation relies on its own generative system to create always-changing patterns that move across the canvas.

![CLP_Diagram](https://cloud.githubusercontent.com/assets/1325463/16654813/7d2387e0-4425-11e6-8f07-bbb21692773f.png)


## How It Works



### The API
Pattern-making on the Lightwall consists of three types of "events"; **sweep**, **explode**, and **dots**. Each event can be triggered and controlled through a simple web [GET request](http://www.w3schools.com/tags/ref_httpmethods.asp). Each type of event has a different set of parameters that determine how that event is executed. All parameters can accept values between 0-100. 


#### **Sweep Parameters**

Create a sweeping animation from one point to another. This command **requires four parameters**. You can add a fifth parameter to control the speed of the animation.

- **start_x** : The horizontal starting location of the sweep animation.
- **start_y** : The vertical starting location of the sweep animation.
- **end_x** : The horizontal end location of the sweep animation.
- **end_y** : The vertical end location of the sweep animation.
- **speed** : How fast the animation moves from start to end.

- **Example GET Request:** http://lightwall.carnegielibrary.org/sweep?start_x=7&start_y=16&end_x=75&end_y=71&speed=29



#### **Explode Parameters**
Create an explosion at a specific location. This command **requires two parameters**. You can add a third parameter to control the size of the explosion.

- **start_x**: The horizontal location of the explosion.
- **start_y**: The vertical location of the explosion.
- **size**: The size of the explosion.

- **Example GET Request:** http://lightwall.carnegielibrary.org/explode?start_x=22&start_y=20&size=5

#### **Dots Parameters**
Create "popping" animation across the light wall. This command **requires one parameter**. You can add a second parameter to control the duration of the animation.
- **size**: The size of the pops.
- **duration**: How long the popping animation lasts.

- **Example GET Request:** http://lightwall.carnegielibrary.org/dots?size=34&duration=99


## More Information
