# Google Actions Basic Concepts
This section will give an overview of Google Actions concepts.

Google Actions (or Actions on Google, or Conversation Action) is an interface to communicate with a Google Assistant. In other words, the application that you will write will be called a "Google Action".

There are three major components that comprise a Google Action.

1. Invocation Trigger - how users invoke your action (i.e. Okay Google, talk to <invocation trigger>).
2. Dialogs - dialogs between the user and your Action.
3. Fulfillment - the code that processes the user input and returns the responses and you expose it as a REST endpoint.

  ![components](index/google_action_components.png)

The communication between Google Assistant and your application is done via HTTP request/response. The format is specified by Conversation API. However, in this codelab, we will be using a tool called API.AI that will handle the Conversation API formatting for us.

![conversation api](index/conv_api.png)

For more in-depth reading, please refer to [official Actions on Google documentation](https://developers.google.com/actions/develop/conversation).
