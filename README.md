# Welcome! 

# Website Link
Please go to: https://melodyofadalyn.github.io/

# Introduction
One artifact was chosen to represent growth in software engineering, databases, and algorithms and structures. That artifact is the android app I had developed for an application course. This artifact was chosen in particular because apps typically incorporate a variety of different elements. Databases to view information that the user interacts with, software complexity which could include the display, or the structure of the app. Which is important to ensure security and decrease the amount of software patches that could be needed. 

# Purpose of the app
The purpose of this app was to act as an event viewer similar to apps such as EventBrite and Ticketmaster. The user is able to view event information (such as event title, event location, and event time.) and add it into the favorites page. 

# Previous Version
  Before the event app was updated with new information. The app was fairly simplistic due to limited knowledge of java and databases, but even though it was fairly simple it held a lot of errors. For example, when you first entered the app, you could type in credentials, but you could also just press the login button. The app in return would show the message “Welcome Jane Doe!”, but never take the user to the homepage. It was clear that the app needed more security for logging in. The register page was also not opening properly when the button was clicked which led the app to crash. The “remember me” checkbox button was also not functional and the hyperlink of forgot password was not connected. The user was never able to get to the home page of the app, it would often crash and go back to the main login page or the default android home screen. Therefore, the user never got to see any of the navigational pages.
  If you look at the xml files within the old version of the app, it is clear that nothing had clickable functions nor was anything clearly connected. Permissions were also implemented within the notifications page which isn’t correct format wise. Permission requests often occur when an app is downloaded or a new feature is clicked on. Overall, the original version of the app had clear functionality issues and had an abundance of files that could have been simplified into one. 


# Enhancements (Current Version)

Enhancements were first added to the login features of the app. Seeing as there were a variety of security issues residing here. With research, I found out that firebase could be implemented with android studio in order to track and maintain user information. So now, when a user goes to log into the app, the credentials must be valid. If they are not valid an error message will appear and will not allow the user to move forward. The register page is also now accessible, the user can also implement credentials into it. Once all credential fields are filled in then the user will be able to log in at any time or log out. As for the forgot password hyperlink, this was converted into a button. The forgot password button also works through firebase. So once the request is sent with a valid email address that has been registered then a password request will be sent to the junk mail of the user. So, in terms of login features more database information was implemented and if/else, try/catch statements were implemented in order to make the app more secure and increase the flow for the user. 

Once the user logs into the app, it will not crash. With increased knowledge on how to use inflater methods and call upon the correct classes. We can see that the user can go from the login page to the home page without any issues as long as all credentials are valid. From here, an array was implemented to view events and scroll views were included so that the user can look through a variety of different events at one time.  The favorites page would work similarly, but is not running at this time because of issues with the inflater. Although, this would work similarly to the adapter for the events in which the favorited events would be placed into an array. They would be removed from the page based on the users’ decisions based on a button. Lastly, the settings page is also reachable, in which shows some settings information. Although this still needs to be connected to the database to show the user’s actual name. Along with their profile picture. 

# Improvements and Growth 

Ultimately this course, I have practiced secure coding, focused on variable naming conventions, reusability and writing as few lines as possible. I was able to achieve this by implementing these practices throughout the android app. Removing unnecessary files and code by making classes such as the login.class handle more functions. While other classes such as the bot_nav.class were broken into several fragments in order to assist in scaling the project. Security features were implemented through the login.class in which credentials are maintained and tracked through firebase. Athough, I did not work with a team on this project, I did take in feedback from my instructor to implement more comments throughout the project so that in the future other programmers could look at the code and navigate it more easily. I took what I learned from my internship, this course, and past courses to improve my coding practices and create an app that can login, logout, and allow users to interact within its UI.  









