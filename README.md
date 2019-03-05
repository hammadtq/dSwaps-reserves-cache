# dSwaps-reserves-cache

This repository contains full package to run a cache on a centralized server.

You just need to install it on any node.js hosting service provider and run `npm rebuild`. (not suitable for heroku as it creates json files.)

The package uses `bn.js` and `web3` as dependencies as configured in `package.json`.

The package was tested using `web3@1.0.0-beta.46`.

Once you run `node index.js`, the package will create two json files, one containing the orderbook reserves for Ropsten and other for the Mainnet. Copy the URLs into [common.js](https://github.com/hammadtq/dSwaps/blob/master/functions/common.js) of the dSwaps.

To run the cache fully, you will also need to enable CORS support on your server. The package was tested using nginx webserver running on a basic $5 VPS on digitalocean. To allow CORS on nginx webserver please see [this thread](https://gist.github.com/Stanback/7145487).

After you test it, you need to start a cron to run on any of your defined time (to fetch data after every x number of minutes or hours). If you will be using digitalocean, follow this [tutorial](https://www.digitalocean.com/community/tutorials/how-to-use-cron-to-automate-tasks-on-a-vps).
