## Lonely Hangouts

Forked from [lonely](https://github.com/danvk/lonely)

I added functionality for `gapi.hangout.getHangoutId`, `gapi.hangout.getHangoutUrl`, `gapi.hangout.getLocalParticipant`, and `gapi.hangout.av.onVolumesChanged` so that these endpoints will provide the plugin with mock data. To simulate volume change events, I used `setInterval` to send out an `EVENTS.VOLUME_CHANGED` message to sockets every two seconds (see `lonely.js`). 

### Notes

I had an issue getting the server to load the static files (`fake-api.js`, `fake-socket-api.js`, `xsocket.io.min.js`) so I just loaded these in the plugin client-side as a workaround.

It seems as if `volumeCollector` is successfully adding in new functions to be called on volume change, but I couldn't test this because I was getting a `volumeCollector.js:194 Uncaught ReferenceError: s is not defined` error (since `volumeCollector.js` was being loaded from the `breakout.media.mit.edu` server from `plugin.xml`).

