# HypeRate DevDocs

## Getting an API key

You need to request your websocket key on our [website](https://www.hyperate.io/api).

## I don't have a compatible device! What should I do?

The API sends a random heartbeat between 60 and 80 every second to the
`internal-testing` device id.

## Connecting to the API

URL: `wss://app.hyperate.io/socket/websocket?token=<MY-WEBSOCKET-KEY>`

## Required websocket messages

### Join Channel

You need to join the appropiate channel before any data will be sent to your
client.

To do this you need to send the following JSON message:

```json
{
	"topic": "hr:<ID>",
	"event": "phx_join",
	"payload": {},
	"ref": 0
}
```

This would be the correct message to join the "internal-testing" channel:

```json
{
	"topic": "hr:internal-testing",
	"event": "phx_join",
	"payload": {},
	"ref": 0
}
```

### Receiving data

Every time the user updates their heartbeat the following JSON will be send from the server to the client:

```json
{
	"event": "hr_update",
	"payload": { "hr": 79 },
	"ref": null,
	"topic": "hr:internal-testing"
}
```

### Send keep-alive packet

Phoenix expects that you send the keep-alive packet every 10 seconds otherwise the connection will be closed.

```json
{
	"topic": "phoenix",
	"event": "heartbeat",
	"payload": {},
	"ref": 0
}
```

### Leave channel

In case you only want to leave a joined channel you can send the following message:

```json
{
	"topic": "hr:<ID>",
	"event": "phx_leave",
	"payload": {},
	"ref": 0
}
```

This would be the correct message to leave the "internal-testing" channel:

```json
{
	"topic": "hr:internal-testing",
	"event": "phx_leave",
	"payload": {},
	"ref": 0
}
```
