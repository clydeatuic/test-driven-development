# Software Testing Activity
This activity will provide a demo to software testing using node stack. The activity will include unit, integration and end-to-end type of software testing.

### Part I - Node Core Setup

```bash
# Update and Install node, npm, git and heroku
$ npm install -g n
$ sudo n latest
$ node -v
$ npm -v
$ express --version
$ git --version 
$ heroku --version
```

### Part II - App Deploy

```bash
# App Deploy LOCALLY (https://expressjs.com/en/starter/generator.html)
$ express --view=ejs lastname-appname
$ cd lastname-appname
$ npm install
$ npm start
	# navigate to localhost:3000
$ git add .
$ git config user.name "github_username_here"
$ git config user.email "github_email_here"
$ git commit -m "message_here"
$ git push -u origin master


# App Deploy REMOTELY (https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)
$ heroku login
$ heroku create lastname-appname
$ git push heroku master
$ heroku open

```

### Part III - Testing

```bash
# On your First Terminal
$ npm install selenium-standalone -g
$ npm install webdriverio --save-dev
$ mkdir test
$ touch e2e.js

# On your Second Terminal
$ selenium-standalone install
$ selenium-standalone start
```

```java

/* test1.js */
var webdriverio = require('webdriverio');
var options = { desiredCapabilities: { browserName: 'chrome' } };
var client = webdriverio.remote(options);
client
    .init()
    .url('https://duckduckgo.com/')
    .setValue('#search_form_input_homepage', 'WebdriverIO')
    .click('#search_button_homepage')
    .getTitle().then(function(title) {
        console.log('Title is: ' + title);
        // outputs:
        // "Title is: WebdriverIO (Software) at DuckDuckGo"
    })
    .end();

/* test2.js */
var assert = require('assert');

describe('webdriver.io.page',function(){
    it('should have the right title', function(){
        browser.url('/');
        var title = browser.getTitle();
        console.log("TITLE IS ", title);
        assert.equal(title, 'WebdriverIO - WebDriver bindings for Node.js')

    });
});

/* test3.js */
var assert = require('assert');

describe('webdriver.io.page',function(){
    it('should have a link to the API page',function(){
        browser.url('/');
        var hasApiLink = browser.isExisting('=API');
        assert(hasApiLink);
    });
});

/* test4.js */
var assert = require('assert');

describe('webdriver.io.page',function(){
    it('should take you to the API page', function(){
        browser.url('/');
        browser.click('=API');

        var title = browser.getTitle();
        assert.equal(title, 'WebdriverIO - API Docs');
    });
});


```

### Deliverable
File: Test Scenario Matrix
Document Type: PDF
Submit To: cbalamanatuic@gmail.com
