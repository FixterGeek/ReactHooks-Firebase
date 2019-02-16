![fixtergeek logo](https://fixter.camp/static/media/geek_completo.7e1e87a7.png)

## Introduction to Firebase 🔥

#### What are you going to learn?

- What is Firebase
- How to create an account into the platform
- Starting a Firebase project
- Wire your Firebase project to an HTML file
- Add some Firebase rules to the DB
- Login with Google

## Let's make an account at firebase.google.com

Firebase is a mobile and web application development platform developed by Firebase, Inc. in 2011, then acquired by Google in 2014. As of October 2018, the Firebase platform has 18 products, which are used by 1.5 million apps.

Firebase is good to enter the web development world because it allow us to have an instant backend effortless, and some key features like login, database, security access and hosting amoung others.
![Firebase home page](https://i.imgur.com/k6fFhR4.png)

To create an account is as easly as have a google account like Gmail. We just have to visit firebase.google.com and signup, then we have access to the apps console.

![firebase app console](https://i.imgur.com/cixMLkX.png)

Now we can add a project clicking the "+" card and complete the data requested, select country and accept the politycs then click in create.

![firebase politycs](https://i.imgur.com/ydJ9LHW.png)

And that's it! you have a brand new Firebase project:

![new firebase project](https://i.imgur.com/IO3YPRN.png)

### Wiring the Firebase project

It is time to connect our Firebase project into a webApp, and to do this we easly can linked our references (credentials) from our Firebase project into any html file what is the backbone of any webapp project.

Let's install a code editor, this time we will use Visual Studio Code from Microsoft, why?, well, is free and very powerful.
[download VSCode here](https://code.visualstudio.com/)
![vsCode logo](https://user-images.githubusercontent.com/49339/32078472-5053adea-baa7-11e7-9034-519002f12ac7.png)

Now is time to create an HTML file whitin vsCode File > new File. And name it index.html, now that we have our new `index.html` file we can rapdly write the basic structure of an HTML file with the vsCode suggestions, write one ! sign and vsCode will suggest two options, this is comming from a plugin already installed called "emmet".

![vsCode suggestions](https://i.imgur.com/ANP7Tf6.png)

Select the first one and it will write the basic structure of an HTML file for you.

![html basic structure](https://i.imgur.com/DiL0kdG.png)

Now is time to wire our Firebase project into our HTML file, for this we will copy the Firebase library and our project's refs, then paste it into our HTML File before the close tag of `</body>`.

![firebase refs](https://i.imgur.com/x2g8YE2.png)

At the end we will have our HTML file like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body>
    <script src="https://www.gstatic.com/firebasejs/5.8.2/firebase.js"></script>
    <script>
      // Initialize Firebase
      var config = {
        apiKey: "AIzaSyC4y_UiuUZI1GUaRxiJTT7iSMDahpwj_Bc",
        authDomain: "nevermind-ad1ae.firebaseapp.com",
        databaseURL: "https://nevermind-ad1ae.firebaseio.com",
        projectId: "nevermind-ad1ae",
        storageBucket: "nevermind-ad1ae.appspot.com",
        messagingSenderId: "1077643302463"
      };
      firebase.initializeApp(config);
    </script>
  </body>
</html>
```

This refs are public, we do not have to worry about the publication of those, but we have to remember to take care of the rules in our new project, and we will in a moment.

We are now connected to our project, and we can start working with our HTML file and our Firebase project all together.

### Learning how to use Firebase Firestore DB

We are now about to work with some javascript into our webapp (the HTML file) in order to save some objects into our DB, first we have to initiate the Firestore database, let's go to the firebase console and select the tab database, then select Cloud Firestore, testing mode and start.

![cloud firestore](https://i.imgur.com/ZraTGqR.png)

Now we can connect to the DB and create a document.

let's write some JavaScript code to connect with the DB.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body>
    <script src="https://www.gstatic.com/firebasejs/5.8.2/firebase.js"></script>
    <script>
      // Initialize Firebase
      var config = {
        apiKey: "AIzaSyC4y_UiuUZI1GUaRxiJTT7iSMDahpwj_Bc",
        authDomain: "nevermind-ad1ae.firebaseapp.com",
        databaseURL: "https://nevermind-ad1ae.firebaseio.com",
        projectId: "nevermind-ad1ae",
        storageBucket: "nevermind-ad1ae.appspot.com",
        messagingSenderId: "1077643302463"
      };
      firebase.initializeApp(config);
    </script>
    <script>
      //here we are going to code
    </script>
  </body>
</html>
```

We are going to write our JavaScript into this Script tag

```javascript
let firestore = firebase.firestore();

firestore
  .collection("students")
  .doc("1")
  .set({
    name: "BlisS"
  });
```

With this we are now writing into the Firestore DB, directly, this thanks to the development settings that we choose, but we have a database now!, so easy right?, if we go looking into the console we can find our new record, now we have our first document into the students collection.

![first firestore document](https://i.imgur.com/8uZ4MIC.png)

### Add some documents more and try with some inputs.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body>
    <h2>Simple form</h2>
    <form>
      <input placeholder="name" name="name" type="text" />
      <br />
      <input placeholder="email" name="email" type="text" />
      <input type="submit" />
    </form>

    <script src="https://www.gstatic.com/firebasejs/5.8.2/firebase.js"></script>
    <script>
      // Initialize Firebase
      var config = {
        apiKey: "AIzaSyC4y_UiuUZI1GUaRxiJTT7iSMDahpwj_Bc",
        authDomain: "nevermind-ad1ae.firebaseapp.com",
        databaseURL: "https://nevermind-ad1ae.firebaseio.com",
        projectId: "nevermind-ad1ae",
        storageBucket: "nevermind-ad1ae.appspot.com",
        messagingSenderId: "1077643302463"
      };
      firebase.initializeApp(config);
    </script>
    <script>
      let firestore = firebase.firestore();
      document.querySelector("form").addEventListener("submit", function(e) {
        e.preventDefault();
        let user = {
          name: e.target.name.value,
          email: e.target.email.value
        };
        firestore
          .collection("students")
          .add(user)
          .then(function() {
            e.target.name.value = "";
            e.target.email.value = "";
          });
      });
    </script>
  </body>
</html>
```

We can see how the new document gets an automatic ID that is unique. Congratulations you are now using a backend as a service. But wait, we can add some security into our DB with some rules and a social login 😱

### Firebase Google login and Rules

Now let's add a simple rule to the database in order to write on it only if we are logged in as user of the webapp, this work is one of the most hard to accomplish for a backend developer but, we are going to do it without too much effort.

First we have to go to the rules tab in the Firestore console.

then add the next rule:

```javascript
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth.uid != null;
    }
  }
}
```

This is going to block the reading and writing for users non loggedin.
Now if we try to add some documents again as we did before we will see this error at the navigator console:

![insuficient permissions](https://i.imgur.com/AMJxcid.png)
Yes, this is good, it means that our security rules are working and now in order to write into the database we need to do a login, so we are going to add a button login validation into our app, and use the `.auth()` tool from Firebase, but in order to the loggin to workm, we need to emulate a web server, luckily there is a very simple web server available as a chrome extension:

![webs erver for chrome](https://i.imgur.com/ZDXN3K3.png)
Web server for Chrome is a very powerful tool that allow us to serve some folder as a webserver, just selecting the folder we wish to use.

Select the folder of your project (where your indexz.html file is living) and then visit `http://localhost:8887` and you will see our form. Now is time to create a login button and put it to work.

Let's write this code into our `Script` tag

```javascript
//login section
let form = document.querySelector("form");
form.style = "display:none";
document.querySelector("button").onclick = function() {
  let provider = new firebase.auth.GoogleAuthProvider();
  firebase
    .auth()
    .signInWithPopup(provider)
    .then(function(result) {
      console.log(result.user);
      form.style = "display:inherit";
    });
};
```

We alse have added a login button into the `<body></body>` tag, and the complete code looks something like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Document</title>
  </head>
  <body>
    <button>Login with Gmail</button>
    <h2>Simple form</h2>
    <form>
      <input placeholder="name" name="name" type="text" />
      <br />
      <input placeholder="email" name="email" type="text" />
      <input type="submit" />
    </form>

    <script src="https://www.gstatic.com/firebasejs/5.8.2/firebase.js"></script>
    <script>
      // Initialize Firebase
      var config = {
        apiKey: "AIzaSyC4y_UiuUZI1GUaRxiJTT7iSMDahpwj_Bc",
        authDomain: "nevermind-ad1ae.firebaseapp.com",
        databaseURL: "https://nevermind-ad1ae.firebaseio.com",
        projectId: "nevermind-ad1ae",
        storageBucket: "nevermind-ad1ae.appspot.com",
        messagingSenderId: "1077643302463"
      };
      firebase.initializeApp(config);
    </script>
    <script>
      let firestore = firebase.firestore();
      document.querySelector("form").addEventListener("submit", function(e) {
        e.preventDefault();
        let user = {
          name: e.target.name.value,
          email: e.target.email.value
        };
        firestore
          .collection("students")
          .add(user)
          .then(function() {
            e.target.name.value = "";
            e.target.email.value = "";
          });
      });

      //login section
      let form = document.querySelector("form");
      form.style = "display:none";
      document.querySelector("button").onclick = function() {
        let provider = new firebase.auth.GoogleAuthProvider();
        firebase
          .auth()
          .signInWithPopup(provider)
          .then(function(result) {
            console.log(result.user);
            form.style = "display:inherit";
          });
      };
    </script>
  </body>
</html>
```

The only missing piece is to go to the authentication tab of the Firebase console, login methods and active the Google login:

![active google login](https://i.imgur.com/p25V2mI.png)

Now if we try our button, we could see that in the console, we will receive the info of our Google user, in adition to the apperance of the form and if we try to write some new record in our database, we can do it! because we are logged in. So nice right?

## Recap:

Uff we have covered a lot of advanced stuff here, we are now using some of the key features of any backend but effortless, thanks to Firebase, we don't even need an advanced webapp we have done all this only with a HTML file, we have added some rules to add security into our app, and we have used Google for make an OAuth2 login, wow nice! you are ready for the next step.

## Resources:

- [Firebase docs](https://firebase.google.com/docs/)
- [Login OAuth2](https://oauth.net/2/)
- [HTML script tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script)

> Author: @hectorbliss
