# WebSocketJSONStream

Expose a WebSocket connection on the server with
JSON-encoded strings as a stream.

Fix for Primus.js usage

```js
this.ws.send(JSON.stringify(msg));
```
to
```js
this.ws.write(JSON.stringify(msg));
```
to match Primus spark.write() syntax

## Usage

```js
var WebSocket = require('ws');
var wss = new WebSocket.Server({server: server});
var WebSocketJSONStream = require('websocket-json-stream');

wss.on('connection', function(ws, req) {
  var stream = new WebSocketJSONStream(ws)

  // ...

});
```
