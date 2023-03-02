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


############
# nats cli #
############
pub/sub:
    nats sub msg.test
    nats.sub msg.>          # all subtopics
    nats sub msg.*          # immediate subtopic only

    nats pub msg.test "hello world"
    nats pub msg.test.hello "hello world"

req/reply:
    nats reply help.please 'OK, I CAN HELP!!!'
    nats request help.please 'I need help!'

queuegroups:
    nats reply foo "service instance A Reply# {{Count}}"
    nats reply foo "service instance B Reply# {{Count}}"
    nats reply foo "service instance C Reply# {{Count}}"
    nats request foo --count 10 "Request {{Count}}"





