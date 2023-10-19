# browser
The browser must be configured to communicate all tracker requests to the raspberry pi.

## Set-up
- Install Google Chrome
- Install Webhook on Request Chrome extension.
- Configure Webhook on Request with the `config.json` file.

## Details
- Webhook on Request will send a HTTP GET to the raspberry pi when trackers are requested in the browser.
- The HTTP GET is processed by [webdis](https://github.com/nicolasff/webdis), a HTTP interface for [Redis](https://redis.io/).
- The following [Redis command](https://redis.io/commands/set/) is submitted: `SET nameoftracker active EX 5`<br>(key = name of tracker; value = `active`; expire after 5 seconds).
