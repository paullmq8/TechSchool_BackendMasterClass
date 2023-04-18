[DB Schema](https://dbdiagram.io/embed/6428e4225758ac5f1725ff84)


$docker exec -it postgres13 /bin/bash

#createdb --username=root --owner=root simple_bank

#psql simple_bank

#\q

#dropdb simple_bank

$docker exec -it postgres13 createdb --username=root --owner=root simple_bank

$docker exec -it postgres13 psql -U root simple_bank

$docker rm postgres13

*using Makefile:
$make createdb
$make dropdb

$migrate -path db/migration -database "postgresql://root:secret@localhost:5432/simple_bank?sslmode=disable" -verbose up

$sqlc version
$sqlc help
$sqlc init