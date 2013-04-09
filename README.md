location-stream
=============
### Version 0.0.1 ###

Simple Node.js Twitter (API 1.1) location stream client



Usage
-------
```javascript
var Stream = require('location-stream');
var stream = new Stream({
    consumer_key: '',
    consumer_secret: '',
    access_token_key: '',
    access_token_secret: ''
});

var locations = [{
	lat: 37.7749295,
	lon: 12.4607737,
	radius: 10
}, {
	lat: 51.9514808,
	lon: 7.62553879,
	radius: 10
}, {
	lat: 53.34410399,
	lon: -6.267493699,
	radius: 10
}, {

	lat: 22.2939806,
	lon: 114.1712193,
	radius: 10
}];

//create stream
stream.stream(locations);

//listen stream data
stream.on('data', function(json) {
	console.log(json);
});

```

Events
-------
- ```data```        - stream data in JSON format
- ```garbage```     - stream data who can't be parsed to JSON
- ```close```       - stream close event (stream connection closed)
- ```error```       - error event (request error, response error, response status code greater than 200)
- ```connected```   - stream created
- ```heartbeat```   - twitter emitted heartbeat

Methods
-------
- ```stream```  - create stream connection
- ```destroy``` - destroy/close stream connection