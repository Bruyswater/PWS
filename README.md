# PWS [![Godoc](https://godoc.org/github.com/TrizlyBear/PWS?status.svg)](https://godoc.org/github.com/TrizlyBear/PWS) [![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
Simple layered neural network library made in Go.

## Goals
- [x] Create a working Neural Network with Fully Connected layers
- [ ] Solve MNIST
- [ ] Create a working Convolutional Neural Network

## Try it

First clone the repository
```shell
git clone https://github.com/TrizlyBear/PWS.git && cd PWS
```
Then run one of the testing scripts
```shell
go run testing/xor_test.go
```

Or try the module by importing it

```go
package main

import (
	"github.com/TrizlyBear/PWS/sequential"
	"github.com/TrizlyBear/PWS/sequential/activation"
	"github.com/TrizlyBear/PWS/sequential/layers"
)

func main() {
	x_train := [][][]float64{...}
	y_train := [][][]float64{...}
	model := &sequential.Model{Layers: []sequential.Layer{&layers.FC{Out: 10}, &activation.Tanh{}, &layers.FC{Out: 1}, &activation.Tanh{}}}
	model.Fit(x_train, y_train, 10, 0.1)
}
```
