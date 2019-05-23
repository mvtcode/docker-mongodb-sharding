# Mongodb Sharding 4.0.9

## Config replication mongo config

`docker exec -it mongoconfig1 mongo`

`rs.initiate()`

`rs.conf()`

`rs.add("10.0.0.102:27017")`

`rs.add("10.0.0.103:27017")`

`exit`

## Config sharding cluster 1

`docker exec -it mongosharding11 mongo`

`rs.initiate()`

`rs.conf()`

`rs.add("10.0.0.12:27017")`

`exit`

## Config sharding cluster 2

`docker exec -it mongosharding21 mongo`

`rs.initiate()`

`rs.conf()`

`rs.add("10.0.0.22:27017")`

`exit`

## Config sharding cluster 3

`docker exec -it mongosharding31 mongo`

`rs.initiate()`

`rs.conf()`

`rs.add("10.0.0.32:27017")`

`exit`

## Config sharding

`docker exec -it mongos mongo # IP: 10.0.0.100`

`sh.addShard("setSha1/mongosharding11:27017,10.0.0.12:27017")`

`sh.addShard("setSha2/mongosharding21:27017,10.0.0.22:27017")`

`sh.addShard("setSha3/mongosharding31:27017,10.0.0.32:27017")`

## Author

tanmv