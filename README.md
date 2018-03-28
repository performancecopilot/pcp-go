# pcp-go
golang support for Performance Co-Pilot

### PMAPI

Example usage:
```go
package main

import "github.com/performancecopilot/pcp-go/pmapi"
import "fmt"

func main() {
	context, _ := pmapi.PmNewContext(pmapi.PmContextHost, "localhost")
	
    hostname, _ := context.PmGetContextHostname()
	pmIDS, _ := context.PmLookupName("disk.dev.read", "disk.dev.write")

	fmt.Println(hostname)
	fmt.Println(pmIDS)
}
```

### Contributing
Great!

New features or extensions to the API should include full test coverage. These tests are written as a single assertion per test.
See `pmapi/pmapi_test.go` for examples. 

The tests rely on the local developer workstation having PCP running and the `sample` PMDA installed. To run the tests:

```sh
make test
```

Git commits should be in the format of `component: short description` with a longer explanation if needed as the body
of the commit. `component`s are `pmapi`, `docs`, `build` etc...

### License
The project is licensed under MIT. It links to libpcp so be aware of license implications there too.