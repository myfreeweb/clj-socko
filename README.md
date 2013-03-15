# clj-socko

A Clojure wrapper for the [Akka](http://akka.io)-based [Socko](http://sockoweb.org) web server.  
Uses [Okku](https://github.com/gaverhae/okku) as the Akka wrapper.  

For now, only a dumb Ring server is available.  
Routing, streaming, websocket coming soon.

## Usage

```clojure
(ns your.app
  (:use clj-socko.core)
  (:import akka.actor.ActorSystem))

(defn handler [req]
  {:status 200
   :headers {"Content-Type" "application/json"}
   :body "{\"hello\": \"world\"}"})

(def as (ActorSystem/create "as"))

(run-server (ring-actor handler) as {:port 8080})
```

## License

           DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                   Version 2, December 2004

Copyright (C) 2013 Greg V

Everyone is permitted to copy and distribute verbatim or modified
copies of this license document, and changing it is allowed as long
as the name is changed.

           DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
  TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

 0. You just DO WHAT THE FUCK YOU WANT TO.
