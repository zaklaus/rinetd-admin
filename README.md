# rinetd-admin

Simple REST API to manage routing rules and access policies for the [rinetd](http://www.rinetd.com/) super server.

## Prerequsites
- Local rinetd server instance
- Node.js - v14.x and newer
- npm

## How to set up
1. Copy `config.dest.json` to `config.json`
2. Edit `config.json` to specify the local rinetd.conf file location, on save hook and webserver port.
3. `node server.js`

## Things to do
- Access policies, they are unsupported at the moment.

## REST API

`api/v1/add/[dport]/[addr]/[port]` - Adds a new entry to the config:
- **dport** - Remote port accessible from the outside network
- **addr** - Local address to redirect packets to
- **port** - Local port we receive packets at

`api/v1/del/[index]` - Removes a specific row:
- **index** - Row to delete from the config

`api/v1/list` - Lists all the config entries

## Dashboard

You can also access a simple to use dashboard via browser that makes use of the API.

## Note

**rinetd-admin** offers no security on its own. It is recommended to run it behind firewall only accessible from the intended local network.
It also works best with config fully managed by this service.
