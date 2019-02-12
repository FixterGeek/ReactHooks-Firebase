![fixtergeek logo](https://fixter.camp/static/media/geek_completo.7e1e87a7.png)

## Introduction to Firebase 🔥

#### What are you going to learn?

- What is Firebase
- How to create an account into the platform
- Starting a Firebase project
- Wire your Firebase project to an HTML file

## Let's make an account at firebase.google.com

Firebase is a mobile and web application development platform developed by Firebase, Inc. in 2011, then acquired by Google in 2014. As of October 2018, the Firebase platform has 18 products, which are used by 1.5 million apps.

Firebase is good to enter the web development world because it allow us to have an instant backend effortless, and some key features like login, database, security access and hosting amoung others.
![Firebase home page](images/firebaseHome.png)

To create an account is as easly as have a google account like Gmail. We just have to visit firebase.google.com and signup, then we have access to the apps console.

![firebase app console](images/firebaseConsole.png)

Now we can add a project clicking the "+" card and complete the data requested, select country and accept the politycs then click in create.

![firebase politycs](images/firebasePolitycs.png)

And that's it! you have a brand new Firebase project:

![new firebase project](images/firebaseProject.png)

### Wiring the Firebase project

It is time to connect our Firebase project into a webApp, and to do this we easly can linked our references (credentials) from our Firebase project into any html file what is the backbone of any webapp project.

Let's install a code editor, this time we will use Visual Studio Code from Microsoft, why?, well, is free and very powerful.
[download VSCode here](https://code.visualstudio.com/)
![vsCode logo](https://user-images.githubusercontent.com/49339/32078472-5053adea-baa7-11e7-9034-519002f12ac7.png)

Now is time to create an HTML file whitin vsCode File > new File. And name it index.html, now that we have our new `index.html` file we can rapdly write the basic structure of an HTML file with the vsCode suggestions, write one ! sign and vsCode will suggest two options, this is comming from a plugin already installed called "emmet".

![vsCode suggestions](images/emmet.png)

Select the first one and it will write the basic structure of an HTML file for you.

![html basic structure](images/htmlBasic.png)

Now is time to wire our Firebase project into our HTML file, for this we will copy the Firebase library and our project's refs, then paste it into our HTML File before the close tag of `</body>`.

![firebase refs](images/firebaseRefs.png)

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

## Recap:

We have learned what ReactJS is, and how the component style development is acomplished, we have writen our first component and some more, we understand now what a prop is and how we can use them, and used the destructuring ES6 tool in order to write more readable components and we have set some defaults in props.

## Resources:

- [React official docs](https://reactjs.org/)
- [Destructuring](http://exploringjs.com/es6/ch_destructuring.html)
- [Tutorial: intro to React](https://reactjs.org/tutorial/tutorial.html)

> Author: @hectorbliss
