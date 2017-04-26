# Deployment and testing
This section will give an overview of how to test our Google Action.

1. From the source code directory, start the Node server by typing ```node app.js```
2. ```cd``` into directory where ```ngrok``` was downloaded. Type ```./ngrok http 8080```.
3. Go to API.AI console and click on ```Integrations``` on the left hand side.
4. Click on ```Actions on Google```.
5. Write down your preferred invocation name (i.e. <invocation trigger>) in the "invocation name" field.
6. Press ```Authorize``` and ```Preview```.

We can now test our Action in the web simulator. Invoke our Action by saying ```"Ok Google, talk to <invocation trigger>"```
