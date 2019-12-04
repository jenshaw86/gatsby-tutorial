# Gatsby Styling

## Global styling - the 3 ways
Global styling is used to set the overall styling for the site
There are many ways to implement this

### Option 1 - Using a global.css file and gatsby-browser.js
1. Create global.css 
2. Create gatsby-browser.js
3. Import global.css into gatsby-browser.js

This is a quickest and most straightforward way to include global css => Import global.css into this file 

`gatsby-browser.js` is a special Gatsby file that Gatsby looks for and utilizes.
It also holds Gatsby APIs
You create it yourself. Check your spelling.

### Option 2 (Highly Suggested) - Using shared layouts
1. Create a layout.js
```javascript
import React from "react"
import "./layout.css"

export default ({ children }) => <div>{children}</div>
```

2. Create a layout.css
3. Import layout.css into layout.js file
4. Import layout.js into a page
5. Wrap layout component <Layout> around desired parts

#### Why is this the best method?
It avoids name conflicts and side effects

### Option 3 - Separate CSS files
1. Create separate css files 
2. Directly import into pages, templates, components

## Component-Scoped CSS Using CSS Modules
What is a CSS Module?

It's a css file where "all class names and animations are scoped locally by default."

It automatically generates unique class and animation names

No selector name collisions

Gatsby knows to process .module.css files as modules and .css as plain css

import css module files like this:
`import styles as './the/name/of/the/file'`

Note for later that styles is an object

### This is the coolest part
When you import a .module.css file and you log it, you can see how CSS Modules creates an object where every class name becomes a key that contains a string value that is the unique class name that Modules generates.

We access this classname with dot notation by calling it by the object name and a key, such as `styles.user`, and that returns the unique class name string

## CSS-in-JS
component-oriented styling
composing CSS inline using Javascript, no external files

CSS-in-JS libraries with Gatsby plugins:
- [Emotion](https://www.gatsbyjs.org/docs/emotion/)
- [Styled Components](https://www.gatsbyjs.org/docs/styled-components/)


## Problems
I thought I applied an ugly layout to only the index.js page. It's imported and being used as a layout component only in that one file. 
But...I'm noticing that, the css is applying itself to ALL pages, even when it's only important and not explicitly used, which I REALLY don't want. 

Meanwhile, the .module.css file is behaving and staying localized to the component it wraps around. Does this have to do with the layout using a standard css file? 

Gasp. I wonder if it does...

That probably explains how shared layouts are used in global styling. module.css files are more specific to the component.