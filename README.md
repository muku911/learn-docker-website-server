# docker-website-server-starter
 
## docker networking
### docker public network same ip as host
docker network create -d macvlan --subnet 10.10.10.0/24 --gateway 10.10.10.1 -o parent=ens3 publicmacvlan
- publicmacvlan = name of docker network
- setup subnet same as dhcp server
- setup gateway
- and also can make range for specific ip address with --ip-range [10.10.10.200/30]
