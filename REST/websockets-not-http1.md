#### REST over WebSockets instead of HTTP
#### https://hackernoon.com/rest-over-websockets-instead-of-http-81b0f0632295

##### onathan Gros-Dubois Creator of SocketCluster http://socketcluster.io Feb 25, 2017

#### EXCERPTS and QUOTES

These days, it’s practically impossible to talk about REST without also talking about HTTP — The two concepts are tightly intertwined; in fact, REST and HTTP 1.1 were developed in parallel by the same person (Roy Fielding). The verbs in HTTP (GET, POST, PUT, DELETE…) make it ideal for performing the kinds of stateless atomic operations required by REST.

Over the past couple of years, a few things have happened on the web which have disrupted the order of things:

FP front-end frameworks like React have gained a lot of traction and have introduced entirely new paradigms for loading data from a server and manipulating that data (see GraphQL).
WebSockets have become widely supported* thereby increasing the interest in real-time technology (see https://blog.baasil.io/why-you-shouldnt-use-long-polling-fallbacks-for-websockets-c1fff32a064a).
