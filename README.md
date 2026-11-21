# major-project-list

Choosing a practice project can take longer than starting one. major-project-list collects programming exercises by topic, with concrete tasks you can implement in any language, including Go.

## Features

- Choose numerical exercises such as prime factorization, Fibonacci sequences, and mortgage calculations.
- Practice algorithms with merge sort, Dijkstra’s shortest-path algorithm, and minimum spanning trees.
- Build applications from prompts for text editors, inventory managers, budget trackers, and other utilities.
- Extend selected exercises with optional requirements, such as syntax highlighting or recurring calendar events.
- Contribute solutions, suggest new projects, or propose corrections to existing prompts.

## Installation

Install [Go](https://go.dev/doc/install) if you want to write and run Go solutions. Reading the project list requires no runtime or dependencies.

Clone your copy of this repository, replacing `<repository-url>` with its Git URL:

```sh
git clone <repository-url> major-project-list
cd major-project-list
go version
```

**This is a project collection, not an installable Go command.** Individual solutions may have their own dependencies and run instructions.

## Usage

Pick a prompt, define its expected inputs and outputs, and implement it in your preferred language. Start with the required behavior before adding optional extensions.

For example, the Factorial Finder prompt asks for the factorial of a nonnegative integer. To try an iterative Go solution, save this example as `factorial.go` in your local `major-project-list` directory:

```go
package main

import (
    "flag"
    "fmt"
    "os"
)

func main() {
    n := flag.Int("n", 5, "integer from 0 through 20")
    flag.Parse()
    if *n < 0 || *n > 20 {
        fmt.Fprintln(os.Stderr, "n must be between 0 and 20")
        os.Exit(1)
    }

    result := uint64(1)
    for i := 2; i <= *n; i++ {
        result *= uint64(i)
    }
    fmt.Printf("%d! = %d\n", *n, result)
}
```

Run it from the repository directory:

```sh
go run ./factorial.go -n 5
```

Expected output:

```text
5! = 120
```

The input limit keeps the result within `uint64`. For the rest of the exercise, add a recursive implementation and check that both versions agree, including for `0! = 1`.

When submitting a solution, include its run command, any dependencies, and sample input and output. Use only systems you own or have permission to test for networking and security exercises. Historical ciphers such as Caesar are learning exercises, not protection for sensitive data.

## License

Licensed under the MIT License. This project is based on [ManojKumarPatnaik/Major-project-list](https://github.com/ManojKumarPatnaik/Major-project-list). Retain the original copyright and MIT permission notice when redistributing inherited material.

The source project credits Martyr2’s Mega Project List and Rosetta Code as inspiration for its problems.

