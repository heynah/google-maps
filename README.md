Use React w/Server to Test Bredcrumbz Code
================================================

Resources (React):

*   [Displaying data with JSX](https://facebook.github.io/react/docs/displaying-data.html)

*   [JSX in depth](https://facebook.github.io/react/docs/jsx-in-depth.html)

*   [Interactivity and dynamic UIs](https://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html)

*   [Multiple components](https://facebook.github.io/react/docs/multiple-components.html)

*   [The React way: getting started tutorial](https://blog.risingstack.com/the-react-way-getting-started-tutorial/)

    **NOTE**: we will not be building a so-called "isomorphic" application so you may skip that part of the article.

*   [Five practical examples for learning React](http://tutorialzine.com/2014/07/5-practical-examples-for-learning-facebooks-react-framework/)

    **NOTE**: make sure to reproduce each of the five examples on your own!

    **NOTE 2**: in the last example, the tutorial uses jQuery to do AJAX. Try to do it with [`isomorphic-fetch`](https://github.com/matthew-andrews/isomorphic-fetch)

*   [Introduction to `react-router`](https://github.com/reactjs/react-router/blob/master/docs/Introduction.md)

    **NOTE**: routing is a concept you are already familiar with, but on the server side.

    As far as we are concerned, routing is the process of deciding what to display based on the current URL.

    On the server side, we are using the Express library to help us do our routing. For example, we tell Express that we want to handle **`GET`** requests to `/content/:id`. When a request comes along for this URL, Express knows which function to call.

    Routing in the browser is similar: we already saw that we could induce a change of the URL in the browser without refreshing the page, by using the [History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API) provided by the browser. Similarly, [we can get notified when the URL changes](https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onpopstate) due to the back or forward buttons being clicked.

    If we put these two concepts together, we can write JavaScript code for the browser that can decide what to display based on the current URL. We can do it manually, but `react-router` does it for us :)

* [React router: a comprehensive introduction](https://www.themarketingtechnologist.co/react-router-an-introduction/)

## Base structure
Our application will be built to run in the browser. This means we will not be needing our own server nor database. However, **we need to serve our files somewhere**. For this reason, a tiny web server was created at `server.js`. All you have to do is run it with `node server.js`. You should not need to restart it nor modify it.

This repository already contains a base structure to get you started:

* `src`: Source directory that contains all your HTML, CSS and JavaScript code
* `src/index.html`: This will load our application. Since it's an all front-end app, everything happens in here :)
* `src/js`: Will contain your JavaScript code
* `src/css`: Your stylesheet
* `.babelrc`: tells Babel what to transform. In our case, it will transform JSX to React calls, and ES6 to "regular JavaScript"
* `.gitignore`: tells Git to ignore some files. `node_modules` can be installed with NPM
* `package.json`: contains the project dependencies as well as some scripts that we can `npm run`
* `README.md`: This file ;)
* `server.js`: Runs a tiny web server that always sends `index.html` by default
* `webpack.config.js`: Configuration for Webpack

To start hacking on this project:

1. `npm install`
2. Start the server with `node server.js`
3. Start Webpack with `webpack --watch`
4. Start coding!

## App specification
This is a tiny specification of the app you will be building:

### Routes
The app will have the following routes:
  *   `/`
