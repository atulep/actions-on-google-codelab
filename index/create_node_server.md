# Create Node server
In this section, we will create a Node server that will process the fulfillment request of our Action.

Start by creating directory ```number-facts``` which will be our source code directory.

Create an ```app.js``` file. Paste the following code:

```javascript
'use strict'

process.env.DEBUG = 'actions-on-google:*';

let Assistant = require('actions-on-google').ApiAiAssistant;
let express = require('express');
let bodyParser = require('body-parser');

let app = express();

app.set('port', (process.env.PORT || 8080));
app.use(bodyParser.json({type: 'application/json'}));

app.post('/', function(request, response) {
  const assistant = new Assistant({request: request, response: response});

  /**
   * Action for the welcome. It can be equivalently defined in the API.AI console as well.
   */
  function welcome(assistant) {
    var reply = ;//TODO: Change the phrase.
    // ask vs. tell -> expects reply vs. doesn't expect reply
    assistant.ask(reply);
  }

  let actionMap = new Map();
  actionMap.set(DEFAULT_WELCOME, welcome);
  assistant.handleRequest(actionMap);
});

var server = app.listen(app.get('port'), function() {
  console.log('App listening on port %s', server.address().port);
  console.log('Press Ctrl+C to quit.');
});
```
Create a file titled ```package.json```. Paste the following code:
```javascript
{
  "name": "number-facts",
  "description": "Google Actions application that uses Numbers API to do the fulfillment.",
  "version": "0.0.1",
  "private": true,
  "license": "MIT",
  "scripts": {
    "start": "node app.js",
    "monitor": "nodemon app.js",
    "deploy": "gcloud app deploy"
  },
  "dependencies": {
    "body-parser": "^1.15.2",
    "express": "^4.13.4",
    "request": "^2.79.0",
    "sprintf-js": "^1.0.3",
    "actions-on-google": "^1.0.0",
    "assert": "^1.4.1"        
  }
}
```
Finally, run our Node server by typing ```node app.js```. Also, run ```ngrok``` by typing ```./ngrok http 8080``` from directory where you downloaded ```ngrok``` to.

Go to ```API.AI``` testing console and tell ```Talk to Number Facts```.
