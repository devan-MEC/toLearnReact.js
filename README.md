# React.js scares me

Pointers to help me learn react

## Links

- [React and React-DOM ](https://reactjs.org/docs/cdn-links.html)
- [Babel ](https://reactjs.org/docs/add-react-to-a-website.html#quickly-try-jsx)

Include the following header files(Obtained from the above links) in your .html file to use React code

```bash
  <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
  <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```

Include this line inside the body tag (to link index.js to your index.html)

```bash
<script src="index.js" type="text/babel"></script>
```

## Getting started

React lets you include html tags inside your javascript file. To better phrase
it, it lets you "render" html tags from inside of a .js file. Pretty neat huh?

index.html

```bash
<html>
    <head>
        <link rel="stylesheet" href="index.css">
        <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
        <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
        <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
    </head>
    <body>
        <div id="root"></div>
        <script src="index.js" type="text/babel"></script>
    </body>
</html>
```

index.js

```bash
ReactDOM.render(<h1>YOOHOO</h1>,getElementById("root"));
```

This renders the h1 tag mentioned in the `index.js` on the `index.html` page. Voila!

## Creating a react class component

Components keeps your code clean and organized ( or 'composable code' as the react people seem to call it)

Create a component (function name is the component name (in CamelCase))

```bash
function MyComponent() {
    return (
        <h1>I'm learning React!</h1>
    )
}
```

Render this component (basically use this inside the render function mentioned earlier)

`<MyComponent />` is how you select the component

```bash
ReactDOM.render(<MyComponent />, document.getElementById("root"));
```

## Using variables

```bash
const navbar = (
    <nav>
        <h1>Bob's Bistro</h1>
        <ul>
            <li>Menu</li>
            <li>About</li>
            <li>Contact</li>
        </ul>
    </nav>
)

```

```bash
ReactDOM.render(navbar, document.getElementById("root"))
```

## Alternate method to use React

Get react as a dependency and import it inside index.js (The external import tags inside index.html can then be avoided)

```bash
import React from "react"
import ReactDOM from "react-dom"
```

## Splitting the components

You can further choose to include components inside components to make the whole thing more modular

```bash
function MainPage(){
    return(
        <div>
            <Header />
            <Content />
            <Footer />
        </div>
    )
}
```

## Adding styling

Similar to how you would mention class="classname" you use the keyword className in react and link the stylesheet inside the .html file

```bash
<div className="container">
```

## Moving each component into it's own file

You can further improve upon the modularity by moving each component into it's own .js file. Just be sure to import React (not applicable for later versions of react) into each file and be sure to export the function using _export default_ and import it inside of the file where you're going to be using it

```bash
import React from "react"

export default function Title() {
    return (
        <div>
            <p>CSGO was kinda meh.</p>
        </div>
    )
}

```

and import it inside the .js file you're going to be using it in

```bash
import Title from "./Title"
```

## Setting up a local server

- Make sure you have node and npm installed (preferably with nvm)
- Run the following command which takes care of everything that happens under the hood with babel and webpack compiling

```bash
npx create-react-app my-app
cd my-app
npm start
```

## Including images and linking css

This is most optimally done via importing the files and style beforehand in the .js file.

When using create-react-app, images are stored inside the ../src/images folder and css files are stored inside the src file

```bash
import "./style.css"
import reactLogo from  "../images/react_logo.png" //.. is used if we have to go back a folder in the path structure
```

After import, the image can be used as follows

```bash
<img src={reactLogo} />
```

## Adding google fonts to your page (using links)

Obtain the 'links' of the font you want from the google fonts page and include it inside of `index.html`
and specify the font family (also available from the google fonts site) in the `index.css`
