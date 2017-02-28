# push-api-demo

This is an attempt to create a simple chatroom example to demonstrate the [Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API). It also illustrates some uses of [Service Workers](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API), and how to use [Channel Messaging](https://developer.mozilla.org/en-US/docs/Web/API/Channel_Messaging_API) to communicate data between a Service Worker and the main window context.

## Current status

At the moment this demo only works on [Firefox Nightly](https://nightly.mozilla.org/). The working parts are:

* Requesting permission to send notifications/push messages.
* Registering and activating a service worker to handle the Push/Channel Messages.
* Subscribing/unsubscribing (to/from) the push sevice.
* Sending a push message from the server.
* Sending messages to and from the SW via a message channel.
* Receiving a push message in the SW via the `onpush` handler and firing a notification and sending a channel message as a result.

See [Using the Push API](https://developer.mozilla.org/en-US/docs/Web/API/Push_API/Using_the_Push_API) for more details about how this works.

## Still to do

* Hosting the server somewhere on t'internet so it can be accessed by multiple users (a chatroom is pretty useless with only one user!)
* Improving the Node server so that it will handle the push messages, AND serve the static files. This is needed for it to start working on Chrome (and Chrome doesn't yet support the PushMessageData either.)


## Running the demo

To get it running:


1. Clone this repo locally (you'll need to [install git](http://git-scm.com/downloads)):

        git clone https://github.com/chrisdavidmills/push-api-demo.git

2. Install [NodeJS](https://nodejs.org/) if you haven't already.
3. Install dependencies:

        cd push-api-demo
        npm install

4. Run the app:

        node server.js

5. Open the app at
   [https://127.0.0.1:7000/index.html](https://127.0.0.1:7000/index.html)
   (Note: You will need to add a security exception)

Note: Some of the client-side code in this demo is heavily influenced by Matt Gaunt's excellent examples in [Push Notifications on the Open Web](http://updates.html5rocks.com/2015/03/push-notificatons-on-the-open-web). Thanks for the awesome work Matt!

