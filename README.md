go-pinyin
=========

[![Build Status](https://travis-ci.org/mozillazg/go-pinyin.svg?branch=master)](https://travis-ci.org/mozillazg/go-pinyin)
[![Coverage Status](https://coveralls.io/repos/mozillazg/go-pinyin/badge.png?branch=master)](https://coveralls.io/r/mozillazg/go-pinyin?branch=master)
[![GoDoc](https://godoc.org/github.com/mozillazg/go-pinyin?status.svg)](https://godoc.org/github.com/mozillazg/go-pinyin)

汉语拼音转换工具 Go 版。


Installation
------------

```
go get -u github.com/mozillazg/go-pinyin
```

install CLI tool:

```
go get -u github.com/mozillazg/go-pinyin/pinyin
$ pinyin 中国人
zhōng guó rén
```

Usage
------

```go
package main

import (
	"fmt"
	"github.com/mozillazg/go-pinyin"
)

func main() {
	hans := "中国人"
    // 默认输出 [[zhong] [guo] [ren]]
	fmt.Println(pinyin.Pinyin(hans, pinyin.Args{}))
    // 包含声调 [[zhōng] [guó] [rén]]
	fmt.Println(pinyin.Pinyin(hans, pinyin.Args{Style: pinyin.TONE}))
    // 声调用数字表示 [[zho1ng] [guo2] [re2n]]
	fmt.Println(pinyin.Pinyin(hans, pinyin.Args{Style: pinyin.TONE2}))
    // 开启多音字模式 [[zhong zhong] [guo] [ren]]
	fmt.Println(pinyin.Pinyin(hans, pinyin.Args{Heteronym: true}))
    // [[zho1ng zho4ng] [guo2] [re2n]]
	fmt.Println(pinyin.Pinyin(hans, pinyin.Args{Style: pinyin.TONE2, Heteronym: true}))
}
```


Related Projects
-----------------

* [hotoo/pinyin](https://github.com/hotoo/pinyin): 汉语拼音转换工具 Node.js/JavaScript 版。
* [mozillazg/python-pinyin](https://github.com/mozillazg/python-pinyin): 汉语拼音转换工具 Python 版。
