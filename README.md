## Golang Protobuf test example

Commands to generate and build:
```
brew install protoc
```

build example:
```
go mod init github.com/grahamnscp/protobuftest

go install google.golang.org/protobuf/cmd/protoc-gen-go@latest

go mod tidy

protoc --proto_path=/Users/my/git/protobuftest --go_out=/Users/my/git/protobuftest /Users/my/git/protobuftest/addressbook.proto
mv github.com/grahamnscp/protobuftest/* .
rm -rf github.com

go build
```

Run:
```
cd cmd
go build add_person.go
go build list_people.go

./add_person my.book
...

./list_people my.book
Person ID: 123
  Name: Bob
  E-mail address: bob@hopenow.labs
  Mobile phone #: 441234000555
  Home phone #: 0122277263
Person ID: 124
  Name: Bill Bud
  E-mail address: bb@thecrew.tv
  Mobile phone #: 44888777999
Person ID: 555
  Name: Ted O
  E-mail address: to@555.com
  Work phone #: 0140522786
```
