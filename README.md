# PAT-with-Pool

##This lab demonstrates how to configure PAT with pool on a Cisco router.

Topics covered:
- Inside and outside interfaces
- PAT with pool configuration
- PAT with pool  verification commands

## Configure Interfaces


enable

configure terminal

interface g0/0/0

ip address 192.168.1.1 255.255.255.0

ip nat inside

no shutdown

exit


interface g0/0/1

ip address 200.1.1.1 255.255.255.0

ip nat outside

no shutdown

exit

##Create Pool

ip nat pool PUBLIC_POOL 200.1.1.10 200.1.1.20 netmask 255.255.255.0

## ACL

access-list 1 permit 192.168.1.0 0.0.0.255

##Enable PAT with Pool

ip nat inside source list 1 pool PUBLIC_POOL overload

## MORE ABOUT ME : https://www.linkedin.com/in/sanaa-el-habib-kahloul/
