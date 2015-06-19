# Apps-Script-Firebase-Notifications
A demo project showing how to use firebase as a backend for push notifications in an Apps-Script project

###Push notifications  
Pushing to the client has always been an issue for Apps Script webapp projects. Becuase of the redirecting required by the platform serviceworkers cannot be used for Apps Script projects. This means that the new Web Push API will not work.  
Luckly Romain Vialard posted a firebase library on the Apps Script community page.  It got me looking into firebase and lead me to this project.  Firebase is blazing fast, simple to implament, and just works.  
I figured out the the Firebase JWT token generater works on the Apps Script server side without modification.  This allowed for the client to use the Apps Script on the server side to authenticate using the firebase custom authentication flow. This makes for a completly seemless experiance to the users.


###Setup:  
1) Make an account on firebase  
2) Create a new firebase project  
3) Add json from securityAndRules.json to the security and rules tab on your firebase project.  
4) Get the firebase project secret from the secrets tab. Add it to the 'secret' property in Apps Script script properties.  
5) Change the 'firebaseURL' variable in code.gs and index.html to point to your firebase project URL.  
6) Add the library MYeP8ZEEt1ylVDxS7uyg9plDOcoke7-2l  
   You can find more about this library at https://sites.google.com/site/scriptsexamples/new-connectors-to-google-services/firebase  
7) Enable the Google+ advanced service and enable the API in the dev console.
  
###Sending a notification  
function sendNotificationToUser(string UID, string message)  
-UID is the stripped down users email.  
-ie person@example.com becomes personexamplecom   
-Message can be any string
  
###Note:  
The polymer files are bieng hosted on a person App Engine project.  You can use it for testing this app, but don't link to it for any other projects. It will be taken down as soon as I figure out the proper CORS settings for firebase hosting.
