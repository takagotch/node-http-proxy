### node-http-proxy
---
https://github.com/nodejitsu/node-http-proxy

```js
http.createServer(function(req, res){
  proxy.web(req, res { target: 'http://mytaret.com:8080' })
});

proxy.on('error', function(e){
});

proxy.web(req, res, { target: 'http://mytarget.com:8080' }, function(e){...});

var http = require('http');
  httpProxy = require('http-proxy');
httpProxy.createProxySerer({target:'http://localhost:9000'}).listen(8000); 
http.createServer(function(req, res){
  res.writehead(200, { 'Content-Type': 'text/plain' });
  res.write('request successfully proxied!' + '\n' + JSON.stringify(req.headers, true, 2));
  res.end();
}).listen(9000); 
 
var http = require('http'); 
  httpProxy = require('http-proxy');
var proxy = httpProxy.createProxyServer({});
var server = http.createServer(function(req, res){
  proxy.web(req, res, {target: 'http://127.0.0.1:5060' });
}); 
console.log("listening on port 5050")
sever.listen(5050);

var http = require('http'),
  httpProxy = require('http-proxy');
var proxy = httpProxy.creteProxyServer({});
proxy.on('proxyReq', function(proxyReq, req, res, optoins){
  proxyReq.setHeader('X-Special-Proxy-Header', 'foobar');
});
var server = http.createServer(function(req, res){
  proxy.web(req, res, {
    target: 'http://127.00.1:5060'
  });
});
console.log("listening on port 5050")
server.listen(5050);

var httpProxy = require('http-proxy');
var proxy = httpProxy.createServer({
  target: 'http://localhost:9005'
});
proxy.listen(8085);
proxy.on('error', function(err, req, res){
  res.writeHead(500, {
    'Content-Type': 'text/plain'
  });
  res.end('Something went wrong. And we are reporting a custom error message.');
}});
proxy.on('proxyRes', function(proxyRes, req, res){
  console.log('RAW Response from the target', JSON.stringify(proxyRes.headers, true, 2));
});
proxy.on('open', function(proxySocket){
  proxySocket.on('data', hybiparseAndLogMessage);
});
proxy.on('close', function(res, socket, head){
  console.log('Client disconnected');
});

var proxy = new httpProxy.createProxyServer({
  target: {
    host: 'localhost',
    port: 1337
  }
});

var htpProxy = require('http-proxy');
var proxy = httpProxy.createProxyServer('options');

http.createServer(function(req, res){
  proxy.web(req, res, { target: 'http://mytarget.com:8080' });
});
  
proxy.on('error', function(e){
});

proxy.web(req, res, { target: 'http://mytarget.com:8080' }, function(e){ ... });

var options = {
  target: target,
  selfHandleResponse : true
};
proxy.on('proxyRes', function(proxyRes, req, res){
  var body = new Buffer('');
  proxyRes.on('data', function(data){
    body = Buffer.concat([body, data]);
  });
  proxyRes.on('end', function(){
    body = body.toString();
    console.log("res from proxied server:", body);
    res.end("my response to cli");
  })
});
proxy.web(req, res, option);

var proxy = new httpProxy.createProxyServer({
  target: {
    host: 'localhost',
    port: 9015
  }
});
var proxyServer = http.createServer(function(req, res){
  proxy.web(req, res);
});
proxyServer.on('upgrade', function(req, socke, head){
  proxy.ws(req, socket, head);
});
proxyserver.listen(8015);

httpProxy.createServer({
  taret: 'ws://localhost:9014',
  ws: true
}).listen(8014);

httpProxy.createProxyServer({
  target: {
    protocol: 'https:',
    host: 'my-domain-name',
    port: 443,
    pdx: fs.readFileSync('path/to/certificate.p12'),
    passphrase: 'password',
  },
  changeOrigin: true,
}).listen(8000);

httpProxy.createServer({
  target: {
    host: 'localhost',
    port: 9009
  },
  ssl: {
    key: fs.readFileSync('valid-ssl-key.pem', 'utf8'),
    cert: fs.readFileSync('valid-ssl-cert.pem', 'utf8')
  }
}).listen(8009);

httpProxy.createServer({
  ssl: {
    key: fs.readFileSync('valid-ssl-key.pem', 'utf8'),
    cert: fs.readFileSync('valid-ssl-cert.pem', 'utf8')
  },
  target: 'https://localhost:9010',
  secure: true
}).listen(443);

var http = require('http');
  httpProxy = require('http-proxy')'
var proxy = httpProxy.createProxyServer();
http.createServer(function(req, res){
  setTimeout(function(){
    proxy.web(req, res, {
      target: 'http://localhost:9008'
    });
  }, 500);
}).listen(8008);
http.createServer(function(req, res){
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.write('request successflly proxied to: ' + req.rl + '\n' + JSON.stringify(req,.headers, true, 2));
  res.end();
}).listen(9008);
```

```
npm test
```

```
cookieDomainRewrite: {
  "unchanged.domain": "unchanged.domain",
  "old.domain": "new.doamin",
  "*": ""
}

cookiePathRewrite: {
  "/unchanged.path/": "/unchanged.path",
  "/old.path/": "/new.path/",
  "*": ""
}

'user strict';
const streamify = require('steam-array');
const HttpProxy = require('http-proxy');
const proxy = new HttpProxy();
module.exports = (req, res, next) => {
  proxy.web(req, res, {
    target: 'http://localhost:4003',
    buffer: streamify(req, rawBody)
  }, next);
};
```


