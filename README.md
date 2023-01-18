# 02-igniting-our-app

- This is an existing project. I built a 'create react app' with parcel bundler. And these are the steps:
  - intialize `npm` into repo > `npm init`
  - install `react` and `react-dom` > `npm install react` , `npm install react-dom`
  - remove CDN links of react from index.html file
  - install parcel > `npm install -D parcel` (-D means dev dependency)
  - add type attribute in script tag to connect with App.js file > `<script type="module" src="App.js"></script>`
  - import react and reactdom in App.js file from node_module > `import React from "react"; import ReactDOM from "react-dom/client";`
  - ignite or run my app with parcel in local machine> `npx parcel index.html` (because, 'index.html' is the entry point of my project. This line of code tells parcel to creates a development build for us and host it in our local server)
  - build a production version of your code using `parcel build` > `npx parcel build index.html`
  - add scripts for “start” and “build” with parcel commands > `npx parcel build index.html` (it is the production build command, when we command build, it creates lot of things like: minifying files. And it push the build production files in the dist folder. To make index.html file entry point of my project, we need to edit our package.json file. From there we need to remove `"main": "App.js"` line of code. and then add these in `"scripts": {
    "start": "parcel index.html",
    "build": "parcel build index.html"
  }
)`. To start the development server, you can run `"npm start"` in your terminal, and to build your project for production, you can run `"npm run build"`.
  - add `.gitignore` file and put these to ignore when we push in git: node_modules/, dist/, .parcel-cache, .DS_Store, .gitignore
  - add `browserlists`in package.json file >
    ` "browserslist":[
      "last 6 versions"
  ]`
