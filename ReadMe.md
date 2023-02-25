Install nats-server binary from here:

https://docs.nats.io/running-a-nats-service/introduction/installation#installing-via-a-package-manager


Install nats (client) binary from here:

https://docs.nats.io/running-a-nats-service/clients

On Startup, enable nats websocket configuration:
nats-server -c nats.conf

send commands to hias's map:  
`nats pub hias '{"cmd":"set_center","lat":47.8, "lon": 13.03}`

send commands to sepp's map:  
`nats pub sepp '{"cmd":"set_zoom","zoom":1}'`


