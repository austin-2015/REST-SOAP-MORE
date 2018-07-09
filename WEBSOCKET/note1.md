#### REST over WebSockets instead of HTTP
#### https://hackernoon.com/rest-over-websockets-instead-of-http-81b0f0632295
##### Jonathan Gros-Dubois Creator of SocketCluster http://socketcluster.io Feb 25, 2017
#### IMPORTANT EXCERPTS as applies to project

##### Why should we force users to refresh the page to get the latest data when we can just as easily have that data update itself in real-time?

#### NOTE TO SELF ON ACCESSIBILITY:  Refreshing pages is an accessibility burden.  This might be a better way to go.

##### Data synchronisation services/frameworks like Firebase and Parse are convenient, but they are not ideal for a number of reasons:
1. They force you to structure your system’s data in a particular sub-optimal way.
1. They typically have limited querying capabilities — Making it hard to search through that data.
1. The synchronisation aspect is error-prone; data conflicts might not resolve correctly so you have to add hooks on the front-end to handle those cases — This could affect the correctness of your data if you’re not careful.
1. The synchronisation aspect is expensive (bandwidth and CPU-wise) and is not necessary for most use cases (where REST would normally be used).
1. You still need to have your own server(s) on the side to process sensitive business logic like emails and payments, so the entire data sync service is in fact redundant… These services go against the fundamental idea of dumb pipes and smart endpoints. Why not interact directly with the target server from your front-end using dumb pipes (WebSockets)?
https://crisp.im/blog/why-you-should-never-use-firebase-realtime-database/
