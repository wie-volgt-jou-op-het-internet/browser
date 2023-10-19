# browser
The browser must communicate all tracker requests to the raspberry pi.

## Set-up
- Install Google Chrome and the Webhook on Request extension.
- Configure Webhook on Request with `config.json`.

## Details
- The browser sends a HTTP GET to the raspberry pi on tracker occurence.
- [webdis](https://github.com/nicolasff/webdis), running on the raspberry pi, processes the HTTP GET which contains the following [Redis command](https://redis.io/commands/set/):<br>`SET nameoftracker 1 EX 5` (key = name of tracker; value = `1`; expire after 5 seconds).
