# transit-clj

A Clojure library designed to ... well, that part is up to you.

## Usage

FIXME

## Testing Tansit implementations

This project contains code which may be used to test all
implementations of transit.

To run a test, execute the following command in the `transit-clj`
directory.

```
bin/verify -impls clj -enc json
```

This will test the `json` version of the `transit-clj` implementation.

The `-enc` option value can be either `json` or `msgpack`. If it is
omitted then both with be tested.

The `-impls` can be any languange implementation. `clj` will test
`transit-clj` and `ruby` will test `transit-ruby`. If this option is
omitted then it will attempt to test all implementations.

To test everything run:

```
bin/verify
```

Tests are currently limited to json and a few EDN examples.


### What you need to run the test

To run the java tests you will need to have maven installed.

To run the Ruby tests you will need Ruby 1.9.


### Supporting testing

The only requirement for an implementation to be testable is that it
have a script named `roundtrip` in its `bin` directory. This script
must start a process which accepts transit data on standard in and
returns transit data on standard out. The process should read the
transit data, the write it to standard out.

The script must take one argument which can be either `json` or
`msgpack` which will be used to setup the correct encoding.


### Improvements

Add bin/roundtrip scripts for the other implementations
Get it working with msgpack
Add generative tests

## License

Copyright © 2014 FIXME

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
