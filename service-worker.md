# Service Worker

## How the Service Worker works in the user's device

```                            
                                           |------------------> Cross-Domain
                                           │                    Servers / CDNs
                                           │ 
                                           │------------------> Your Server
Your PWA ------------> Service Worker------│
                                           
client                Proxy Middleware                           Servers
_______________________________________________________________________________
      User's Device - Browser                                     Cloud
```




```
    ____________________________________________________________________________  
    │                                                                          │
    │                                                 Cache miss               │
    │                                            --------------------          │
    │      Makes request                         forwards the request          │
    │      -------------                            to the network             │
    v            1                                       3b                    │            
Your PWA --------------------> Service Worker ----------------------------> Network
    ^                              │    ^                           same-origin and cross origin
    │                              │    │
    │                              │    │
    │         Cache hit            │    │ 2 Searches in cache
    │    --------------------      │    │   ----------------
    │    responds with cached      │    │
    │         response             │    │
    │            3a                │    v
    │______________________________│  Cache
```