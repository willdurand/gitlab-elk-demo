Gitlab + ELK
============

## Usage

First, use the
[lc-tlscert](https://github.com/driskell/log-courier/blob/develop/src/lc-tlscert/lc-tlscert.go)
tool to generate self-signed SSL certificates:

```
$ wget https://raw.githubusercontent.com/driskell/log-courier/develop/src/lc-tlscert/lc-tlscert.go
$ go run lc-tlscert.go
```

Then, move the generated `selfsigned.{crt,key}` files to `etc/ssl/`:

```
$ mv selfsigned.{crt,key} etc/ssl/
```

Finally, up all the things!

```
$ docker-compose up
```


License
-------

Copyright (c) William Durand <will+git@drnd.me>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished
to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
