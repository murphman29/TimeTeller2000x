# TimeTeller2000x

<b>Required Libraries:</b>
No external libraries are required to use this application.

<b>Features and how to use:</b>

 This application is the ultimate time-telling software. If watching clocks is your thing, you can watch an unlimited number of clocks tick at the exact same time. The clock tick information is shown in the texbox at the bottom of the application. Wonderful! If you get tired of living in the present, you can change all clocks’ times with the press of the “Change!” button. Just type in the time you desire the application to change to before doing so! For a visual representation, see Figure One. 
Oh, but wait. There’s more! Not only can you watch multiple instances of one clock format, but two! You have the choice to instantiate either a digital or analog clock whenever a new one is desired. The digital clock displays the information in a format that is similar to what you would see on a tangible digital clock whereas the analog version displays in a labored fashion, similar to how people really read analog clocks. New versions of these clocks can be created by pressing the "New Digital" or "New Analog" buttons, respectively.
So you thought that was all? Well there is even more in store for when you use this amazing application! If you accidentally change the time to something you actually did not want to relive, you can simply click the “Undo” button to revert back to the previous time. If you change your mind later, you can press the “Redo” button to pick up the clock right where you left off. 

<b>Figure One:</b>

![alt text](https://github.com/murphman29/TimeTeller2000x/blob/master/Screenshot%20(12).png)

<b>My Experience:</b>
	The implementation of the design patterns was really quite easy. I spent about two hours considering the actual design of the application’s backend, which was complete in less than six hours. The GUI, however, took 8 hours all on its own…
	The Command Design Pattern is certainly worth the time to implement if it is common to complete actions multiple times. The main negative to this pattern is how many extra classes need to be created just to execute tasks that may only be one one or two lines long, so I would not find this suitable for small applications. 
	The MVC Design Pattern was the more painful of the two to implement, however also was the most useful. The main problem I had when creating the MVC was deciding which entities would have which responsibilities. In the end, I decided to make the model contain the list of done and undone actions and of course its time. The controller, however, was responsible for updating the views and relaying any changes to the model. Since Android works a little funny, I needed to put the update thread in the mainActivity to ensure it would always maintain priority. 
	
<b> Class Functionality </b>

The application is structured to contain, from highest to lowest precedence, a model; a controller; a ClockView interface; and two types of clocks that implement the interface. The Activity the user interacts with sends all of its change requests to the controller, which then forwards them to the model. If the model ends up changing, it pushes the updates down to the controller which keeps a running list of all instantiated views it needs to update. As desired, the views know nothing about anything but the controller so that they can register themselves. 
