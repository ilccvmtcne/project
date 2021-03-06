# teamform-seed

### Pre-requisites

Install git: [http://git-scm.com/](http://git-scm.com/).

Install node.js and npm: [http://nodejs.org/](http://nodejs.org/).
Commands to test the installation:

```
git --version
node -v
npm -v
```
Read the book - [Clean Code](http://ricardogeek.com/docs/clean_code.pdf)

Read the [article](https://scotch.io/tutorials/angularjs-best-practices-directory-structure) about Angularjs file system best practice

Read the [article](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md) about Angularjs language style best practice

#### Setup Firebase
- In app/config/env.js, insert your firebase information to connect the application to your firebase project

#### Setup Facebook login
1. Enter [facebook developer console](https://developers.facebook.com), create a new facebook app
2. In Firebase console, <b>Authentication->Login Methods->Facebook</b>, enable facebook authentication
3. In Facebook app dashboard, copy the AppID and App Secret to Firebase console <b>Authentication->Login Methods->Facebook</b>
4. In Facebook app dashboard, <b>+Add Product</b>, add Facebook Login product
5. Copy the OAuth redirect URI in Firebase console, <b>Authentication->Login Methods->Facebook</b>, to Facebook app dashboard <b>Facebook Login->Settings->Client OAuth Settings->Valid OAuth redirect URIs</b>, the uri should be in the format of <b>https://[YOUR-FIREBASE-PROJECT-NAME].firebaseapp.com/__/auth/handler</b>
6. In Facebook app dashboard, <b>App Review</b>, make sure you make the facebook app public

### Clone the project

Please clone the repository at GitHub using `git clone` command:

```
git clone https://github.com/hkpeterpeter/teamform-seed
cd teamform-seed
```

### Install Dependencies
 
In this course project, fixed version of key libraries (e.g. AngularJS 1.5.7) are included in `app/lib` folder to avoid discreprency. Other development dependencies (e.g. karma toolkit, http-server...) will be installed separately via:

```
npm install
```

After running this command, a new folder will be created:

* `node_modules` - It contains the npm packages for the necessary tools we need to build and test our web application

### Run the Application

We have preconfigured the project via a configuration file `package.json`. The simplest way to start this web application is:

```
npm start
```

After that, open a web browser (Google chrome desktop/mobile web browser is recommended) with the following URL: `http://localhost:8080/index.html`.


## Directory Layout

```
LICENSE                 --> The software LICENSE of this open source project. Generated by Github
README.md               --> This README file (default README file for Github)
.gitignore              --> Git configuration file. It can be used to ignore files/directories from Git 
karma.conf.js           --> Configuration file for the Jasmine/Karma unit test framework. 
package.json            --> Configuration file for node.js and npm (Node Package Manager)
app/                    --> all of the source files for the application
  index.html            --> The front-end of the team form web application
  admin.html            --> The admin HTML page
  team.html             --> The team HTML page
  member.html           --> The member HTML page
  lib/                  --> Key libraries with fixed version (e.g. Angular JS 1.5.7) 
  js/                   --> User-defined JavaScript files
     admin.js           --> The JS file for the admin page
     index.js           --> The JS file for the front-end page
     team.js            --> The JS file for the team page
     member.js          --> The JS file for the member page
     site.js            --> The JS file containing functions shared by multiple pages
  unit_tests            --> The folder containing the unit test cases (Syntax: Jasmine/Karma)
     test_site.js       --> A sample test case
  
```

## APIs
### Sending email
```
$http.post(
      'https://software-engineering-server.herokuapp.com/',
        {
            email: 'colee@ust.hk',
            subject: 'Hello jeffreyleeon',
            text: 'Congratulations jeffreyleeon, you just sent an email with Mailgun!  You are truly awesome from POSTMAN!',
        }
    )
    .then(function(response) {
    // What ever you need to do
    });
```

## Testing

### Running Unit Tests

 We provide a Karma configuration file to run them.

* the configuration is found at `karma.conf.js`
* all unit test cases should be written inside the folder `app/unit_tests`

The easiest way to run the unit tests is to use the supplied npm script:

```
npm test
```

This script will start the Karma test runner to execute the unit tests. 
In this course, we will mainly focus on the branch and statement coverage. 
The output files will be stored inside the `app/coverage` folder. 

## Addtional information for COMP3111H students

Besides from web development, COMP3111H team needs to work on a mobile app (iOS and Android). We recommend your team to use Ionic framework [http://ionicframework.com/] (http://ionicframework.com/). Ionic framework is based on AngularJS. Features completed in Angular can be easily ported to Ionic.   

## Reference

For more information, please checkout:

* Full Firebase 3.0+ API: https://firebase.google.com/docs/reference/
* Full AngularFire 2.0+ API: https://github.com/firebase/angularfire/blob/master/docs/reference.md
* Angular JS: http://angularjs.org/
* git: http://git-scm.com/
* npm: https://www.npmjs.org/
* node: http://nodejs.org
* jasmine: http://jasmine.github.io
* karma: http://karma-runner.github.io
* http-server: https://github.com/nodeapps/http-server
* ionic framework (for COMP3111H teams): http://ionicframework.com/
