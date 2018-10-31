# PCAP generation write-up

This file contains very basic information on how each PCAP was created. If adding to this file, please include the following:

* docker-compose file
* which script was used and by this container
* which container or host performed the capture

## syn-flood-001.pcap

Used he following compose script:

```
version: '3.5'

services:
    target:
        build: Target/.
        networks:
          attack-net:
            ipv4_address: 172.19.0.10
        volumes:
        - ./pcaps:/pcap
    bystander:
        build: Bystander/.
        networks:
          attack-net:
            ipv4_address: 172.19.0.11
    attacker:
        build: Attacker/.
        networks:
          attack-net:
            ipv4_address: 172.19.0.12
        depends_on:
          - "target"
          - "bystander"

networks:
  attack-net:
    driver: bridge
    ipam:
      driver: default
      config:
      - subnet: 172.19.0.0/24
```

Atacker used *SYN-flood*.

Traffic captured using TCPDUMP from the *target*.
      