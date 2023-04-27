## Creating method of a firbase project 



## iNITIAL SETuP

visit : console.firebase.google.com
create project (skip google anylytics)
register app (create config)
install firebase : npm install firebase
add config file to your project
DANGER : Do not publish or make public firebase config by pushing code in github


## INTEGRATION 

Visit : go to docs > build > Authentication > web > get started
export app from the firebase.config.js file : export default app 9 . Login,jsx : import getAuth from firebase/auth
create const auth = getAuth(app)


## PROVIDER SETUP 


import googleAuthorProvider and create a new provider
use SignWithPopUp and pass auth and provider
activate sign-in method (google, facebook github etc) 14 . [vite] : change 127.0.0.1 to localhost


### More auth provider

active the auth provider (create app, provide redirect url, client id, client secret)


 1. what is firebase?
 A product of google. Helps developers to build apps faster and securely . No programming is required on the firebase side which makes it  easy to use its features more efficiently . Provides services to android , ios, web and unity . It provides cloud storage . Uses NoSQL for the database for the storage data .

 2. What is firebase SDK
 The Firebase Admin SDKs bundle the Google Cloud client libraries for Firebase alongside client libraries and SDKs for several other Firebase features. The SDKs provides by firebase. Directly interact with backend service .There is no need to establish any connection between the app and the services. If you're using on of the firebase database options, you typically write code to query the database in your client app . the traditional  app development process requires writing both fronted and backend software . The fronted code just implements the API endpoints exposed by the backend and the backend code actually does the work . With Firebase Products , the traditional backend is bypassed , putting the work into the client . Full meaning of Firebase SDk is Software Development Kit

 3. Firebase Authentication ?
 Firebase Authentication provides backend services , easy-to-use SDKs , and ready-made Ui libraries to authenticate users to your app . It supports authentication using passwords , phone numbers popular federated identity providers like google, facebook and tweeter and more.... . Firebase Authentication Authentication integrates tightly with other firebase services and it leverages industry standards like OAuth 2.OAuth

 4. OAuth 2.0 is?
 OAuth 2.O which stands for "o[pen Authorization] is a standard designed to allow a website  or application to access resources  hosted by the others web apps on behalf of a user. OAuth 2.O provides consented access and restricts actions of what the client app can perform on resources on behalf of the user , without ever sharing the user's credentials. . Since Firebase Authentication follows industry standards like OAuth 2.O , lets's discuss more about OAuth 2.O to know how firebase authentication works behind the scene..........

 5. Principles of OAuth 2.O ?
 OAuth 2.O is an authorization protocol and Not an authentication protocol. Authentication verifies the identity of a user or service , and authorization determines their access  rights.  OAuth 2.O is designed primarily as means of granting access to a set of resources , for example remote APIs or user's data. OAuth 2.O uses Access tokens . An Access Token is a piece of data that represents  the authorization to access resources on behalf to the end-user .

 6. How OAuth 2.O works ?
 i. The client requests authorization (authorization request)  from the authorization server , supplying the client id and secret to as identification ; It also provides the scopes and an endpoint URI (redirect URi) to send the access token or the Authorization code to.

 ii. The Authorization server authentication sever authenticates the client and verifies that the requested scopes are permitted .

 iii. The resources owner interacts with the Authorization sever to grant access

 iv. the Authorization server redirects back to the client with either an Authorization Code or Access token depending on the grant type

v. With the access token the client requests access to the resources from the resources services

7. Firebase Authentication ?
Once a user authenticates , 3 things will happen
i Information about the user is returned to the application via callbacks to allow us to personalize our apps;'s user experience for the specific user.

ii. The User information contains a unique ID which is guaranteed  to be unique distinct across all providers . 

iii. This unique Id is used to identify the user and what parts pf the backend system they are authorized access

8. Why use an Oauth provider ?
A you make an app that accesses a solid web based back-end its's important to consider the following aspects of security.
requiring strong passwords 
the use of strong  encryption ensuring secure 
ensuring secure communication (between client and server) 
securing password storage within an encrypted database .
Implementing password recovery . (which also has to be secure)
adding 2 factor authentication (highly recommended extra layer of security)
Including protection against man in the middle attacks




9. What is onAuthStateChanged?

onAuthStateChanged allows us to subscribe to the users current authentication state, and receive an event whatever that state changes...

 On AuthStateChanged adds an observer for changes to the user's sign-in state . The observer triggers when it sign in and sign  out..

 The onAuthStateChanged method also  returns  an unsubscriber function which allows us to stop listening for events whatever the hook is no longer use...

 Calling onAuthStateChanged( )  adds an observer/listener for changes to the user's sign in state and return an unsubscribe function that can be called to cancel the listener....


10. How to use onAuthSTateChanged ?

There are two ways for call Interaction :
 i. Triggering an event by clicking a button etc........
 ii. useEffect

Since onAuthStateChanged is a side-effect and this function needs to be called without triggering any event , it needs to be incorporated inside the useEffect hook....


The  onAuthStateChanged  takes two parameters 
i. auth  - provides an Auth instance
ii. observer - its a callback function . I gets invoked immediately after registering the onAuthStateChanged observer with the current authentication state and whenever the authentication state changes





########################################### EXAMPLE WITH VIDEO ON MODUEL 61-2#################################


11.   Why need to unsubscribe to onAuthStateChanged in firebase ?

You unsubscribe to avoid memory leaks.
When you initialise  onAuthStateChanged you create a listener . If you dint unsubscribe then this listener will continue to listen even after you stop using it . This will waste memory.

In order to unsubscribe you need something to unsubscribe from.. This is why you assign the listener to a variable. This allows you too refer to the variable when you want to unsubscribe





12. What is private Route ?

The private route component is used to protect selected pages in react app from unauthenticated users . 

The privateRoute component will simply check the current user state from the user , destructured from useContext hook.

The private route component renders child components (children)  if the user is logged in . If not logged in the user is redirected to the login page with the return url passed in the navigate component 




13. AUTHENTICATION VS AUTHORIZATION 

***AUTHENTICATION***

determines  whether  users are who the claim to be

challenges the user to validate credentials (for example through  passwords , answer to security question , to facial recognition)

usually done before AUTHORIZATION

it usually needs the users login details


generally , transmits info through an ID Token


***AUTHORIZATION***

determines what users can and cannot access

verifies whether access is allowed through policies and rules

usually done after successfull authentication

while it needs user's privilege or security levels

generally transmits info through an access token



