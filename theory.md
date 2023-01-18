Q1: What is `NPM`?
A: npm (known as Node Package Manager but not true) is the default package manager for JavaScript runtime environment Node.js. It is used to install and manage packages (collections of code written by other developers that you can use in your own projects) and their dependencies. npm makes it easy to share and reuse code, and it is the largest ecosystem of open-source libraries in the world.

npm is included in the Node.js installation, so if you have Node.js installed on your computer, you already have npm as well. You can use npm to install packages from the npm registry, which contains over 1 million packages, and you can also use it to manage and update those packages. npm also provides an command line interface (CLI) which makes it easy to run the scripts defined in the package.json file, which can automate tasks such as building and deploying your project.

---

Q2: What is `Parcel/Webpack`? Why do we need it?
A: Parcel and Webpack are both JavaScript bundlers. They are tools that take the various files in your project (such as JavaScript, CSS, and images) and bundle them together into a single file (or a few files) that can be served to the browser. This can improve the performance of your web application by reducing the number of requests the browser needs to make and reducing the amount of data that needs to be downloaded.

`Parcel` is a zero-configuration web application bundler. It is easy to use and requires minimal setup, making it a great option for small to medium-sized projects or for developers who are new to building web applications.

`Webpack`, on the other hand, is a more powerful and flexible tool. It requires more configuration, but it also provides more options and features. It is often used in larger projects or projects that have more complex build requirements. Webpack can be used to perform many additional tasks such as code splitting, asset optimization and loading on demand etc.

In summary, both Parcel and Webpack are used to bundle and optimize the assets of your web application for production use. Parcel is a simple and easy to use, while Webpack is more powerful and flexible but with a steeper learning curve. The choice between them depends on the size and complexity of your project, as well as your own preference and experience.

---

Q3: What is `.parcel-cache` ?
A: `.parcel-cache` is a directory created by the Parcel bundler to store cached assets and build artifacts. It is used to speed up the development and building process by caching the results of previous builds and reusing them when possible.

When Parcel is run, it analyzes the project's files and dependencies, and generates a bundle of optimized assets that can be served to the browser. This process can take some time, especially on larger projects. By caching the results of this process, Parcel can quickly generate the bundle on subsequent runs without needing to perform the entire process again.

The `.parcel-cache` directory typically contains subdirectories for each package in your project, containing the cached assets and build artifacts specific to that package.

Caching can be very helpful in speeding up the build process, but it can also cause issues if the cache becomes stale or out of sync with the current state of the project. You can use the `--no-cache` option or remove the `.parcel-cache` directory to force parcel to rebuild the whole project.

---

Q4: What is `npx` ?
A: `npx` is a package runner tool that comes with `npm`. It allows you to run command-line executables from packages that you have installed in your project, without having to globally install them on your system.

When you run a command using `npx`, it will first check if the package is installed locally in your project's `node_modules` directory. If it is not found, it will then check if the package is installed globally on your system. If it is not found in either location, `npx` will download and install the package temporarily, and then run the specified command.

This approach allows you to run executables from packages without having to worry about version conflicts or pollution of your global namespace. It is also useful for running one-off commands or scripts, without the need to install them permanently.

For example, you can run `npx parcel index.html` instead of `parcel index.html` to run the parcel command in your project directory, even if parcel is not installed globally.

---

Q5: What is difference between `dependencies` vs `devDependencies` ?
A: `dependencies` and `devDependencies` are both properties in the package.json file that are used to specify the packages that your project depends on. The main difference between the two is when and how they are used during the development and production process.

`dependencies` are packages that are required for the application to run properly in production. These packages should be installed on the user's system when the application is deployed. They are intended for end-users and are considered to be a critical part of the application. Examples of dependencies include packages for routing, handling HTTP requests, and storing data.

`devDependencies`, on the other hand, are packages that are only needed during the development process. These packages are not needed to run the application in production, but they are useful for developers while working on the application. Examples of devDependencies include packages for transpiling, testing, and building the application.

In summary, `dependencies` are packages that are needed to run the application in production, while `devDependencies` are packages that are only needed for development and building the application.

---

Q6: What is Tree Shaking?
A: Tree shaking is a term used to describe a feature of modern JavaScript bundlers like Webpack and Parcel that allows them to eliminate unused code from the final bundle. The process is called "tree shaking" because it eliminates "dead branches" from the dependency tree of the project.

When you import a module in JavaScript, the bundler will follow the imports and dependencies of that module and include all the code required to run it in the final bundle. But, in many cases, a module exports more than what is actually used in the application.

Tree shaking uses the static structure of the ES6 import and export statements to determine which code is actually used and which is not. By analyzing the code and identifying which parts are not being used, the bundler can eliminate them from the final bundle. This can significantly reduce the size of the bundle and improve the performance of the application.

The process of tree shaking is not limited to JavaScript, it can also remove the unused CSS by using a specific plugin like purgeCSS.

It's worth noting that tree shaking requires that the code is written in a way that is amenable to static analysis, and it only works with the ES6 module syntax and not with the older CommonJS or AMD module formats.

---

Q7: What is Hot Module Replacement?
A: Hot Module Replacement (HMR) is a feature that allows you to update modules in a running application without needing to reload the entire page. It is often used in development to speed up the development process by allowing you to make changes to your code and see the results immediately, without the need to manually refresh the browser.

HMR works by having a runtime that listens for updates to the files in your project and updates the corresponding modules in the running application. This means that when you make a change to a file and save it, the runtime will detect the change, update the corresponding module in the application, and then apply the changes to the browser without refreshing the page.

HMR is a development-only feature and it's not recommended to use it in production. It is usually used in development to speed up the development process and make it more efficient by allowing developers to see the changes in the browser without refreshing the page.

---

Q8: - List down your favourite 5 superpowers of Parcel and describe any 3 of them in your
own words.
A: `Zero Configuration`: One of the most powerful superpowers of Parcel is its zero configuration setup, it doesn't require any configuration files or complex setup process. It automatically detects and uses the correct parsers and plugins for your project, which makes it easy to get started with a new project.

`Hot Module Replacement (HMR)`: Parcel supports Hot Module Replacement (HMR) which allows you to update the modules in a running application without needing to reload the entire page. This feature can significantly speed up the development process and make it more efficient.

`Asset Management`: Parcel has built-in support for handling different types of assets such as images, CSS, and fonts. It can automatically optimize and bundle these assets along with your JavaScript, which makes it easy to manage and maintain your assets.

`Code Splitting`: Parcel has a built-in code splitting feature that allows you to split your code into smaller chunks, which can be loaded on demand. This improves the performance of your application by only loading the code that is actually needed.

`Development Server`: Parcel comes with a development server that has built-in support for features like hot module replacement, asset management, and live reloading. This makes it easy to get started with a new project and quickly see the changes in the browser.

---

Q9: What is `.gitignore`? What should we add and not add into it?
A: `.gitignore` is a file that tells Git which files or directories to ignore when committing changes to a repository. It is typically used to exclude files that are specific to a particular development environment, such as compiled files, dependencies, and configuration files.

The contents of a `.gitignore` file are a list of file patterns, one per line. Git will ignore any file or directory that matches one of the patterns in the file.

Here are some examples of files and directories that are commonly added to `.gitignore`:

- Compiled files, such as .js, .css, .min.js, .min.css etc.
- Package manager files and directories, such as node_modules/, .lock files, yarn.lock, package-lock.json etc.
- Log files, such as .log
- Configuration files, such as .env files.
- Cached files, such as .parcel-cache/
- Operating system files, such as .DS_Store

It's important to not add sensitive information, such as keys and passwords, in the `.gitignore` file.

---

Q10: What is the difference between `package.json` and `package-lock.json` ?
A: package.json and package-lock.json are both files used in npm (Node Package Manager) to manage dependencies in a JavaScript project. They serve different purposes and have different functions.

package.json is a manifest file that contains information about the project, such as its name, version, and dependencies. It also includes scripts that can be run using npm, such as npm start or npm test. This file is used to specify the dependencies of a project and the versions of those dependencies that the project is compatible with. The versions of the dependencies specified in package.json are often represented by a semantic versioning (semver) range.

package-lock.json, on the other hand, is a file that is automatically generated when you run npm install command. It contains a detailed and precise record of the exact version of each dependency and its sub-dependencies that is installed in the project. It also includes the version of each package that is installed and the location where it was installed from. The package-lock.json file is intended to be committed to version control and shared among the development team.

---

Q11: Why should I not modify `package-lock.json`?
A: You should not modify package-lock.json manually because it is intended to be an automatically generated file that reflects the exact state of the dependencies in your project at a specific point in time. Modifying it manually can cause inconsistencies and errors in your project and it's recommended to use the npm install command with appropriate flags to add or update dependencies in your project.

Manually modifying package-lock.json can lead to several issues:

- Inconsistencies between the installed dependencies and the versions specified in the package-lock.json file.
- Conflicts with other packages that have different versions of the same dependencies.
- It can also cause issues with other developers working on the same project.

It's recommended to use npm install command with --save or --save-dev flags to add or update dependencies in your project. This will automatically update the package.json file and also generate a new package-lock.json file that reflects the new state of the dependencies.

---

Q12: What is `node_modules` ? Is it a good idea to push that on git?
A: node_modules is a directory that contains all the packages and dependencies that your project depends on. It's generated by the npm when you run the npm install command, and should not be committed to version control as it's not necessary to distribute with your application in production. Instead, it is recommended to include the package.json and package-lock.json files in version control and let other developers run npm install to install the dependencies when they clone the repository.

And no, it is not a good idea to push on git.

---

Q13: What is the `dist` folder?
A: `dist` (short for "distribution") folder is a directory that contains the final, production-ready version of your application or project. It is typically generated by a build tool or a task runner, and contains the files that are ready to be deployed to a web server or other production environment. The dist folder should not be committed to version control as it's not necessary to distribute with your application in production.

The contents of the dist folder will depend on the type of project you are working on, but it commonly includes the following:

- Compiled and minified versions of your JavaScript, CSS, and other assets.
- Optimized and compressed images and other media files.
- HTML, CSS and JavaScript files that are ready to be served to a browser.

---

Q14: What is `browserlists` ?
A: browserlist is a configuration file that is used to specify the target browsers and versions that your project supports. It is commonly used by tools like Autoprefixer and Babel to determine which browser-specific features and polyfills to include in the final build of your project.

For example, .browserslistrc file specifies that the project should support the last 2 versions of all the major browsers (Chrome, Firefox, Edge, Safari, and Opera), as well as Internet Explorer 11.

---

Q15: What is `^` - caret and `~` - tilda ?
A: `^` and `~` are both prefixes used in semantic versioning (semver) ranges in the `dependencies` and `devDependencies` section of the `package.json` file to specify the version of a package that a project depends on.

`^ (caret)` is a prefix that is used to specify that a project is compatible with any version that is equal to or greater than the specified version, but less than the next major version.
For example, if a package has the version `1.2.3` and the `^1.2.3` is used in package.json, it will match any version starting with `1.x.x` but not `2.x.x`

`~ (tilda)` is a prefix that is used to specify that a project is compatible with any version that is equal to or greater than the specified version, but less than the next minor version.
For example, if a package has the version `1.2.3` and the `~1.2.3` is used in package.json, it will match any version starting with `1.2.x` but not `1.3.x`

It's worth noting that if you don't specify any prefix, it will match only the exact version.

---

Q16: What are the Script attributes in html ?
A: In HTML, the <script> tag has several attributes that can be used to define how the script should be executed and loaded by the browser:

- `src`: This attribute is used to specify the location of an external script file. The browser will load and execute the script file located at the specified URL.

- `async`: This attribute is used to specify that the script should be executed asynchronously, which means that the script will be loaded and executed in parallel with the rest of the page, without blocking the parsing of the HTML.

- `defer`: This attribute is similar to async in that it also allows the script to be loaded and executed in parallel with the rest of the page, but it also specifies that the script should be executed after the page has finished parsing.

- `type`: This attribute is used to specify the type or language of the script. The default value is `"text/javascript"`, but other values like `"application/javascript"` or `"module"` can be used if needed.

- `charset`: This attribute is used to specify the character encoding of the script file.

- `nomodule`: This attribute is used to indicate that the script should not be executed when the <script> element is used in a module context.

- `crossorigin`: This attribute is used to indicate whether the script should be executed with a CORS (Cross-origin resource sharing) request or not.

It's worth noting that some of these attributes are only available in HTML5 and not in previous versions of HTML.
