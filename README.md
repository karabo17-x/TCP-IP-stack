# Transmission Control Protocol and Internet Protocol 
Learning C by building a TCP/IP stack from scratch 

```

tcpip-stack/
├── link-layer/              # Ethernet framing + ARP (only needed if using TAP)
│   ├── ethernet.c/h
│   └── arp.c/h
│
├── network-layer/           # IPv4 addressing, routing, checksums
│   ├── ipv4.c/h
│   └── checksum.c/h
│
├── control-messages/        # ICMP — ping, error reporting
│   └── icmp.c/h
│
├── datagram-transport/      # UDP — connectionless transport
│   └── udp.c/h
│
├── reliable-transport/      # TCP — the state machine, the big one
│   ├── tcp-state-machine.c/h
│   ├── tcp-retransmission.c/h
│   ├── tcp-flow-control.c/h
│   └── tcp-connection.c/h   # the TCB (Transmission Control Block) struct + lifecycle
│
├── device-interface/        # TUN/TAP setup — where raw packets enter/exit
│   └── tun-device.c/h
│
├── application-interface/   # Your socket-like API that apps use to talk to the stack
│   └── socket-api.c/h
│
├── demo-application/        # A tiny app proving the stack works end-to-end (e.g. HTTP echo)
│   └── http-demo.c
│
├── network-setup/           # Shell scripts to configure the TUN device, routes, IPs
│   └── setup-tun.sh
│
├── tests/                   # Unit tests for checksums, header parsing, state transitions
│   ├── test-checksum.c
│   └── test-tcp-states.c
│
├── docs/                    #  RFC references, diagrams
│   └── tcp-state-diagram.md
│
├── Makefile
└── README.md 
```