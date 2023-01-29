# lern-fedora
lern-fedora

## set ipaddress

````
nmcli connection modify 'Wired connection 1' IPv4.address 10.0.2.27/24

nmcli connection modify 'Wired connection 1' IPv4.gateway 10.0.2.11

nmcli connection modify 'Wired connection 1' IPv4.dns 8.8.8.8

nmcli connection modify 'Wired connection 1' IPv4.method manual

nmcli connection down 'Wired connection 1.'

nmcli connection up 'Wired connection 1.'
````

## Fedora 36 Using nmcli

````
nmcli con modify 'Wired connection 1' ifname enp0s3 ipv4.method manual ipv4.addresses 192.168.1.149/24 gw4 192.168.1.1

nmcli con mod 'Wired connection 1' ipv4.dns 192.168.1.1

nmcli con down 'Wired connection 1'

nmcli con up 'Wired connection 1'

ip a s
````

## example 
````
nmcli con add type ethernet con-name 'static-fedora' ifname enp0s3 ipv4.method manual ipv4.addresses 192.168.1.179/24 gw4 192.168.1.1

nmcli con mod 'static-fedora' ipv4.dns 192.168.1.1

nmcli con up 'static-fedora'

ip a s enp0s3
````
