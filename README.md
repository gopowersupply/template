[![GitHub](https://img.shields.io/github/license/gopowersupply/template)](https://github.com/gopowersupply/shell/blob/master/LICENSE)
[![Go version](https://img.shields.io/github/go-mod/go-version/gopowersupply/template)](https://blog.golang.org/go1.13)
[![Build Status](https://travis-ci.org/gopowersupply/shell.svg?branch=master)](https://travis-ci.org/gopowersupply/template)
[![Go Report Card](https://goreportcard.com/badge/gopowersupply/template)](http://goreportcard.com/report/gopowersupply/template)
[![Coverage Status](https://coveralls.io/repos/github/gopowersupply/template/badge.svg?branch=master)](https://coveralls.io/github/gopowersupply/template?branch=master)
[![code-coverage](http://gocover.io/_badge/github.com/gopowersupply/template)](https://gocover.io/github.com/gopowersupply/template)
[![GoDoc](https://godoc.org/github.com/gopowersupply/shell?template.svg)](https://godoc.org/github.com/gopowersupply/template)
[![GitHub tag (latest SemVer)](https://img.shields.io/github/v/tag/gopowersupply/template)](https://github.com/gopowersupply/template/releases)
[![GitHub last commit](https://img.shields.io/github/last-commit/gopowersupply/template)](https://github.com/gopowersupply/template/commits/master)
[![GitHub issues](https://img.shields.io/github/issues/gopowersupply/template)](https://github.com/gopowersupply/template/issues)

The repo is template for other projects.

Here long repo description.

Get it from github:
```bash
go get -u https://github.com/gopowersupply/template
```

Documentation can be [found here](https://godoc.org/github.com/gopowersupply/template)

# Examples

This is examples section:
```go
    res, err := shell.Cmd("echo hi")
    panic(err)
    // res: hi    
```
> :warning: Be aware that command result string truncates.
> This means that if the real output is `' sample output\n'` you will get `'sample output'`

## Errors handling


```go
    func ExecUnexpected() error {
    	// [...] Here your other returns with own errors
        _, err := shell.Cmd("unexpected_command")
        if err != nil {
        	return err
        }
        // [...] Here your other returns with own errors
    }

    func main() {
    	err := ExecUnexpected()    	
    	if shell.IsCommandError(err) {
    		// [...] to do anything
    	} else {
    		// [...] to do something other    		
    	}
    }
```
And you can use `errors.As(err, &shell.CommandError{})` as alternative.