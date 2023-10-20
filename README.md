# laptop
The laptop must communicate all trackers in the browser to the raspberry pi.

## Set-up
- Install Google Chrome and the [Webhook on Request](https://chrome.google.com/webstore/detail/webhook-on-request/omjifoffgbnhdgcmeepmgopiopkbafio) extension.
- Configure Webhook on Request with `config.json`.

## Details
- The Webhook on Request browser extension sends a HTTP GET request to the raspberry pi when a tracker is detected.
- The HTTP GET request is processed by [webdis](https://github.com/nicolasff/webdis), which is running on the raspberry pi. The HTTP GET request contains the following [Redis command](https://redis.io/commands/set/):<br>`SET nameoftracker 1 EX 5` (key = name of tracker; value = `1`; expire after 5 seconds).

## Sources
- https://github.com/dyne/domain-list
- https://github.com/nickspaargaren/no-google
- https://github.com/jmdugan/blocklists
- https://github.com/llacb47/mischosts
- https://github.com/nickspaargaren/no-amazon
- https://github.com/blocklistproject/Lists
