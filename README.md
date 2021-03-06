# is [![GoDoc](https://godoc.org/github.com/matryer/is?status.png)](http://godoc.org/github.com/matryer/is) [![Go Report Card](https://goreportcard.com/badge/github.com/matryer/is)](https://goreportcard.com/report/github.com/matryer/is) [![Build Status](https://travis-ci.org/matryer/is.svg?branch=master)](https://travis-ci.org/matryer/is)
Professional lightweight testing mini-framework for Go.

* Easy to write and read
* [Beautifully simple API](https://godoc.org/github.com/matryer/is) with everything you need: `is.Equal`, `is.OK`, `is.NoErr`, and `is.Fail`
* Use comments to add descriptions (which show up when tests fail)

Failures are very easy to read:

![Examples of failures](https://github.com/matryer/is/raw/master/misc/delicious-failures.png)

### Usage

The following code shows a range of useful ways you can use
the helper methods:

```go
func Test(t *testing.T) {

	is := is.New(t)
	
	signedin, err := isSignedIn(ctx)
	is.NoErr(err)            // isSignedIn error
	is.Equal(signedin, true) // must be signed in
	
	body := readBody(r)
	is.OK(strings.Contains(body, "Hi there"))
	
}
```
