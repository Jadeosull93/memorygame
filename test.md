# Project Testing

## General Testing
*	I tested all the navigation links repeatedly to guarantee that they worked from each individual page.

*	I loaded pages several times to verify that the images loaded perfectly every time, as well as establishing that images appeared zoomed if they were designed to do so. 

*	I confirmed that all buttons on the site performed the task that they were set out to, E.G; the hint button works for each level.

*   The HTML and CSS were validated on [W3](https://validator.w3.org/), there were 13 errors found in total. However, all errors were successfully corrected.

## How User Stories Were Tested:
###### As a game player, I want clear navigation so that I can quickly access what I need, i.e how to play or a different level.
- Both web pages have clearly labelled buttons for users and the game page also has an icon section. The game landing page displays a clear panel of buttons.
###### As a game player, I want to be able to have control over any audio on the site.
- On the landing page there is a button to toggle on and off the music, when the user has moved on to the game page they have the option to control the sound by clicking the "Speaker" icon.
###### As a game player, I want to be able to access how to play the game at any time.
-  The landing page displays a button labelled how to play, when the user has moved on to the game page there is an "information" icon which allows them to access the how to play modal if needed.*
###### As a game player, I want to see bright eye-catching visual images which add to my experience.
-I created all the images for the game board cards using canva.com and ensured I was bright colours that complimented the game page background
###### As a game player, I want to be able to see how I am doing in the game: how many moves i've made and how long it has taken me.
- Above the game board is a scoreboard section which enables the user to see the time elapsed since they made the first move in the game along with the number of moves they made. 
###### As a game player, I want to be able to receive a hint if I am struggling with the game. 
- The buttons panel above the game board allows users to click a hint button which flashes the cards on the board for 600 milliseconds. The number of hints allowed in the game varies on whatever level the user has picked. 


## How Responsiveness Was Tested
I investigated the responsiveness of the website by utilizing the Google Chrome extension to establish that the site was receptive to all device sizes; mobiles, tablets and monitors. 
The responsiveness of the web game was futher tested by using [amiresponsive.is](http://ami.responsivedesign.is/). 

I also tested the responsiveness by asking family and friends to play the game on their mobiles/tablets - the following devices were used to test: Iphone 11, Iphone 7, Samsung Galaxy Note and Samsung Galaxy Tab S6.
It was through this testing that the issue with cards not flipping correctly on iOS was picked up. This is discussed in the JS testing and debugging section below. 

### Issues Encountered with Responsiveness during design:
#### GameBoard
Initally the gameboard grid wasn't responding to mobile size devices. This was an oversight on my part by setting the height and width dimensions too large. I resolved this issue by using VW and VH as the measurements and setting a max-height and max-width.
The game grid is now fully responsive. 

## Testing and Debugging Javascript:
Each time I wrote a javascript function I ran the code to ensure it worked. If the code didn't work I debuged it using some functions I had written and by using the chrome developer tools console.
I debugged the JS by creating a javascript file called debug.js which held some key testing functions outlined below: 

- One common issue I encountered while writing JS for the first time was that I was calling elements that I had not defined or at least not defined properly.
to overcome this issue I created a function called *validateElement(elementName)* if the element was missing the following text was logged to the console :**"ERROR: Element " + elementName + " is not defined"**.
On seeing this message I knew what element to go back and fix/define. 

- I also used a *shuffleTest* function, which ensured that pairs of images were allocated side by side. This was especially useful when testing certain aspects of the game such as the game over modal as it meant I didn't have to go through a while game each time. 

Another tool I used to clean the JS in the project was [JShint.com](https://jshint.com/). This is a website which checks if JavaScript source code complies with coding rules e.g if all brackets are present. 

One bug I ran into while coding the game was on the function in *createboard.js* called setImageSources() - at first the sources were not allocating correctly, this was because imageallocation contains numbers from 1 to n but the array index needs to be from zero for setimagesources() to function. To correct this problem I had to -1 from imageallocation as so: imagesAllocation[i] - 1.

As stated above the main issue I ran into with JS not working as intended was not having declared elements correctly. Some other issues included not having exported/imported functions into the correct JS file. This was easy to solve with the help of chrome developer tools.

## Issues during testing:
One major issue that occured during testing and deployment was how the game functioned on iOS and Safari. There was an issue with the cards flipping during the game. Only the first card would flip correctly and the rest would turn white. 
To solve this issue several changes were made. From researching similar issues online I found various different possible solutions. Unfortunatly, most of these did not fix the issue including:
- changing the degrees of the transform rotate so it is not exactly 90 degrees or a multiple of 90 degrees.
- adding -webkit prefixes to all transforms and backface-visibilty's 

Through trial and testing I found that changing the background color of the Box Div that the front-face and back-face of the card are stored in; from the color white to transparent worked.









