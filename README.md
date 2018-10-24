# homebridge-http-opensprinkler
A switch plugin for homebridge (https://github.com/nfarina/homebridge) which integrates with HTTP(S) APIs.

A plugin for OpenSprinkler fw 1.8.3.
Based on homebridge-http-sprinkler by goedh452 (https://github.com/goedh452/homebridge-http-sprinkler)


# Installation

1. Install homebridge using: `npm install -g homebridge`
2. Install this plugin: `npm install -g homebridge-http-opensprinkler`
3. Update your `config.json` configuration file

# Configuration

Name             | Required    | Description
---------------- | ----------- | --------------------------------------------
accessory        | Yes         | Has to be HttpOpenSprinkler
name             | No          | Name in home app (default OpenSprinkler)
icon             | No          | Icon displayed in Home app (possible values: 0, 1, 2, 3; default 0)
onUrl            | Yes         | URL for turning on the sprinkler
offUrl           | Yes         | URL for turning off the sprinkler
timeout          | No          | HTTP request timeout in ms (default 5s)
checkStatus      | No          | Indicator if status should be checked via the API (possible values: once, polling, no; default no)
pollingInterval  | No          | If checkStatus is polling, the pollinginterval can be specified in milliseconds (default 3000 (3 seconds))
statusUrl        | No          | URL to check the status via the API; required when checkStatus is once or polling
onValue          | No          | Value for On when status is checked (default 1)
offValue         | No          | Value for Off when status is checked (default 0)
useTimer         | No          | Indication if a timer can be used (possible values: yes, no; default no)
defaultTime      | No          | Default time in seconds the timer should be set to; can be changed in the settings page of the accessory, but resets every time homebridge is restarted; hence here the possibility to set a default
httpMethod       | No          | Method for sending requests (default GET)



Configuration sample based:

 ``` 
"accessories": [ 
        {
                "accessory": "HttpOpenSprinkler",
                "name": "Sprinkler backyard",
                "icon": 1,
                "onUrl": "http://192.168.1.22/sn1=1",
                "offUrl": "http://192.168.1.22/sn1=0",
                "timeout": 3000,
                "checkStatus": "polling",
                "pollingInterval": 5000,
                "statusUrl": "http://192.168.1.22/sn1",
                "onValue": "1",
                "offValue": "0",
                "useTimer": "yes",
                "defaultTime": 900,
                "httpMethod": "GET"
        }
```    
