<p><a target="_blank" href="https://app.eraser.io/workspace/iEHqGT0ON7222vaZ303u" id="edit-in-eraser-github-link"><img alt="Edit in Eraser" src="https://firebasestorage.googleapis.com/v0/b/second-petal-295822.appspot.com/o/images%2Fgithub%2FOpen%20in%20Eraser.svg?alt=media&amp;token=968381c8-a7e7-472a-8ed6-4a6626da5501"></a></p>

# What is this codebase?
This is the Sauce Labs Sample Application which is designed to be used from desktop web browsers

![sample-app-web workflow](https://github.com/saucelabs/sample-app-web/actions/workflows/sample-app-web.yml/badge.svg "")

![codecov](https://codecov.io/gh/saucelabs/sample-app-web/branch/master/graph/badge.svg?token=Q4UsgDSRd3 "")

- [﻿Setup](#setup) 
    - [﻿Requirements](#requirements) 
    - [﻿Build](#build) 
    - [﻿Storybook](#storybook) 
- [﻿Test](#test) 
- [﻿Deploy](#deploy) 
## Setup
### Requirements
To set up the development environment directly on your host computer:

1. You’ll need [﻿Node.js](http://nodejs.org/)  installed (this needs to be NodeJS 14, not higher). If you don't have Node installed,
we recommend installing [﻿NVM](https://github.com/creationix/nvm)  to assist managing multiple active Node.js versions.
2. Install [﻿OpenJDK 8](https://adoptopenjdk.net/)  for running the end-to-end tests
3. Install [﻿Google Chrome](https://www.google.com/chrome/)  for running the end-to-end tests
4. Clone the project somewhere on your computergit clone git@github.com:<your-username>/sample-app-web.git
5. Install all dependencies by running this command from the **root of the project**npm install
### Error reporting with Backtrace
To set up error reporting with your Backtrace instance:

1. Open `src/index.jsx`  file and find the `BacktraceClient.initialize`  function call:BacktraceClient.initialize({
    name: 'Swag Store',
    version: '3.0.0',
    url: 'https://submit.backtrace.io/UNIVERSE/TOKEN/json',
    userAttributes: () => ({
        user: currentUser(),
        shoppingCart: ShoppingCart.getCartContents()
    })
})
2. Replace `UNIVERSE`  and `TOKEN`  in `url`  with your universe and token.
For more details, [﻿see the docs about React integration with Backtrace](https://docs.saucelabs.com/error-reporting/language-integrations/react/).

### Build
1. Build the application with This will build the application, start Chrome and load the website on [﻿http://localhost:3000/](http://localhost:3000/) npm run start
2. Click around - this is the app!
### Sourcemaps in error reporting with Backtrace
To enable additional insight in Backtrace, you can send built sourcemaps and sources to Backtrace:

1. Open `.backtracejsrc`  file
2. Replace `UNIVERSE`  and `TOKEN`  in `upload.url`  with your universe and token.
3. Build the application withnpm run build
4. Run `backtrace-js` npm run backtrace.sourcemaps
5. Host the app using e.g. `http-server`  (sourcemaps integration won't work with `npm run start` )npx http-server -p 3000 ./build
6. New uploaded errors should display with sourcemaps attached!
For more details, [﻿see the docs about sourcemap integration with Backtrace](https://docs.saucelabs.com/error-reporting/platform-integrations/source-map/).

### Storybook
This website uses components which can be tested with Storybook. To run Storybook execute the following command:

```
npm run storybook
```
This will open Storybook on [﻿http://localhost:6006/](http://localhost:6006/). More information about Storybook can be
found [﻿here](https://storybook.js.org/docs/react/get-started/introduction).

## Test
### E2E
#### Testing locally
To run the application test suite (which uses Webdriver.io, Selenium, and Chrome) make sure the application is running
on [﻿http://localhost:3000/](http://localhost:3000/) (see above steps)

```
npm run test.e2e.local
```
This will run the application test suite

#### Testing on Sauce Labs
Running on Sauce Labs uses Environment Variables to authenticate credentials. You can find a guide on how to do this
[﻿here.](https://wiki.saucelabs.com/display/DOCS/Best+Practice%3A+Use+Environment+Variables+for+Authentication+Credentials) 

1. `npm run test.e2e.sauce.us`  to run tests on the Sauce Labs in the US Data Center
2. `npm run test.e2e.sauce.eu`  to run tests in the EU Data Center
>  Make sure you've added the `SCREENER_API_KEY` variable to your environment variables. 

### Visual Component Testing
You can test the components with Screener Component testing by running the following commands

```
# This will test all components on Chrome only
npm run test.storybook.ci

# This will test all components on Chrome and Safari in mobile viewports
npm run test.storybook.mobile

# This will test all componentes on Chrome, Safari, Firefox and Safari
# with different desktop resolutions
npm run test.storybook.desktop
```
Each PR to master will also test the components with the `test.storybook.ci`-command.

>  Make sure you've added the `SAUCE_USERNAME` and `SAUCE_ACCESS_KEY` variables to your environment variables. 

## Deploy
Merges to master need to manually be triggered in [﻿Actions > github pages release](https://github.com/saucelabs/sample-app-web/actions/workflows/github-pages.yml) and will automatically deploy to:

- [﻿https://www.saucedemo.com](https://www.saucedemo.com/) 
- [﻿https://saucelabs.github.io/sample-app-web/](https://saucelabs.github.io/sample-app-web/) 
See: [﻿.github/workflows/github-pages.yml GitHub Action](.github/workflows/github-pages.yml) 

![SequenceDiagram.png](/.eraser/iEHqGT0ON7222vaZ303u___rD0khWVDa9T9TBzsOw7lkBsSbMP2___YXOs-2RLE-2UehDDinoCH.png "SequenceDiagram.png")





<!--- Eraser file: https://app.eraser.io/workspace/iEHqGT0ON7222vaZ303u --->