# browser
The browser must be configured to communicate all requests to trackers to the raspberry pi.

## Set-up
- Install Google Chrome
- Install Webhook on Request Chrome extension.
- Configure Webhook on Request with the `config.json` file.

## Details
- Webhook on Request will make a GET request to the raspberry pi when a tracker domain is requested in the browser.
- The GET request is processed by [webdis](https://github.com/nicolasff/webdis), a HTTP interface for [Redis](https://redis.io/).
- The following [Redis command](https://redis.io/commands/set/) is submitted: `SET nameoftracker active EX 5`.<br>This sets a key to the name of the tracker, the value to `active` and lets the key expire after five seconds.
