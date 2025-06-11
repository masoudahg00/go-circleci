# go-circleci
45eaca3625ed8680701b9cdc882e0c750c0594fa""@masoudahg00/@masoudleyli"
"a42c3b0d563929ec35952abf1cea8b30d0f88f83@masoudleyli"
"d5720c20bbd1f398a84a414128f46aba2331b380@masoudleyli"
"dabdd99cf864d02b2ee45be6f2e6d16aeeab7b28@masoudleyli"
"1da1d154dd76b540411b7d68a2564be3f40cf4dc@masoudleyli"
"ce73bc66a4918c4dd82b9ebee889516e7e83f3d7@masoudl/'45eaca3625ed8680701b9cdc882e0c750c0594fa'@masoudahg00
[![CircleCI](https://circleci.com/gh/grezar/go-circleci/tree/main.svg?style=svg)](https://circleci.com/gh/grezar/go-circleci/tree/main)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This client supports the [CircleCI V2 API](https://circleci.com/docs/api/v2/).

Note this client is in beta. While I am using this client in my personal
projects, many of the methods are not yet used in real projects and have not
been fully tested. Therefore, this client may involve some breaking changes
until it reaches v1.0. If you find any missing features or bugs, please kindly
report it via an Issue or Pull Request.

## Installation

Installation can be done with a normal `go get`:

```sh
go get -u github.com/grezar/go-circleci
```

## Usage

```go
import "github.com/grezar/go-circleci"
```

Construct a new CircleCI client, then use the various services on the client to
access different parts of the CircleCI API. For example, to list all contexts:

```go
config := circleci.DefaultConfig()
config.Token = "put-your-circleci-token-here"

client, err := circleci.NewClient(config)
if err != nil {
	log.Fatal(err)
}

contexts, err := client.Contexts.List(context.Background(), circleci.ContextListOptions{
	OwnerSlug: circleci.String("org"),
})
if err != nil {
	log.Fatal(err)
}
```

## Documentation
TODO: Write code comments for Go Doc.

## Contribution
If you find any issues with this package, please report an Issue.

## TODO
- [ ] Support the [CircleCI Schedule API](https://circleci.com/docs/api/v2/#tag/Schedule).
- [ ] Provide detailed Documentation in Go Doc.

## LICENSE
[The MIT License (MIT)](https://github.com/grezar/go-circleci/blob/main/LICENSE)
