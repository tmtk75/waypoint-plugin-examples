.PHONY: protos build

.DEFAULT_GOAL := build

protos:
	protoc -I . --go_out=plugins=grpc:. --go_opt=paths=source_relative ./registry/output.proto
	protoc -I . --go_out=plugins=grpc:. --go_opt=paths=source_relative ./platform/output.proto
	protoc -I . --go_out=plugins=grpc:. --go_opt=paths=source_relative ./release/output.proto

build: protos
	CGO_ENABLED=0 go build -o ./bin/waypoint-plugin-filepath ./*.go
