# aipool

[![LINK](https://img.shields.io/badge/link-Github-%23FF4D5B.svg?style=flat-square)](https://github.com/aiio/aipool) 
[![Go Report Card](https://goreportcard.com/badge/github.com/aiio/aipool)](https://goreportcard.com/report/github.com/aiio/aipool)
[![GoDoc](https://godoc.org/github.com/aiio/aipool?status.svg)](https://godoc.org/github.com/aiio/aipool)
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg?style=flat-square)](https://github.com/996icu/996.ICU/blob/master/LICENSE)


## Example
```Go
package main

import (
	"fmt"
	"time"
  
  
	"github.com/aiio/aipool"
)

func main()  {
	pool := aipool.New(10)
	for i := 0;i<1000;i++ {
		pool.Add()
		go func() {
			// TODO something
			time.Sleep(1)
			fmt.Print(".")
			pool.Done()
		}()
	}
	pool.Wait()
}


```
