---
layout: post
title:      "JavaScript addEventListener()"
date:       2021-04-25 18:23:54 +0000
permalink:  javascript_addeventlistener
---


As a newbie, coding in JavaScript can be intimidating. An Event Listener is an important action to manipulate a webpage and to help change it dynamically.  The Event Listener is a method that is attached to an html element that helps us manipulate it in one way or another. 

Let’s examine an example where we could use an event listener. A common one is to listen to a click in our page. 

To addEventListner() Syntax for a click: 

Imagine we have a “#user-container” that is capturing all the users in our page with all the assigned attributes including a delete button . Now, we would like to listen to a click on that delete button for a particular user. 

First, we would like to have access to that container and save it  in a variable: 

```deleteName = document.querySelector(“#user-container”)``` 

Next step is to call “ addEventListener” on that variable and execute some function thereafter to enable us to successfully delete that user. 

```deleteName.addEventListener(“click”, (e) => someFunction(e))```

Next step is to create someFunction and pass in our code to execute the deletion process. 

```function someFunction(e) {
	
	// enter your code here. 
}```

The best way to understand anything is to continue practicing and repeating the code over and over. Utilizing a debugger and console.loging your code are the best ways to understand what is going on under the hood.  
