# Getting the device ID / session ID

The device ID or session ID is always the last part of the URL which is shown to the user.

Lets consider the following example:

`https://app.hyperate.io/1234`

The device ID / session ID would be `1234` in this case.

## Note for Apple watches and Garmin watches

Not all devices have enough space to display the full URL. In that case the protocol is omitted.

Example:

`app.hyperate.io/1234`

In this case the session ID is `1234`.

## Note for WearOS watches

The WearOS app is displaying the following text: `Session ID: 1234`

In this case the session ID is `1234`.

## Known ID lengths

| Name              | Length |
| :---------------- | :----: |
| Android           |   3    |
| iOS / Apple Watch |   4    |
| Garmin            |   5    |
| wearOS            |   6    |
| Web Bluetooth     |   7    |
| FitBit            |   8    |
