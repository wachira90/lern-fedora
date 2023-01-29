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
