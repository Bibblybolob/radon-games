<img height="70px" src="https://raw.githubusercontent.com/cohenerickson/radon-games/main/public/img/banner.svg"></img>

An open-source unblocked games website built with simplicity in mind.

## Setup
```
git clone https://github.com/cohenerickson/radon-games
cd radon-games
npm i
pm2 start server.js -n Radon
```

The website listens on both port `443` and `80`, the reason it listens on both is to fix some issues resolving while using cloudflare.


### Configuring Domains
Configure your DNS settings to point to your webserver then run the following command for each of your domains. The server will automatically configure each of them with ssl. This step is unnecessary if you are proxied through cloudflare.
```
certbot certonly --standalone --preferred-challenges http -d <REPLACE WITH YOUR DOMAIN>
```


### config.json
There are a few configuration options for the website, you can view them below.
```
{
  "gameProxy": true, // If true, the website will proxy games to the backend server.
  "minify": true,
  "rateLimit": {
    "enabled": false, // If true the server will limit requests to the specified rate.
    "maxRequests": 100, // The maximum number of requests allowed per 'timeWindow'.
    "timeWindow": 60 // The time window in seconds.
  }
}
```
