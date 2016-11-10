# Markdown to Godoc converter

Sort of like [godocdown](https://github.com/robertkrimen/godocdown), but in
reverse.

md-to-godoc takes markdown as input, and generates godoc-formatted package
documentation.

## Status

Way, way alpha. Barebones. The minimalest.

## Code example

Mostly here so we can see some code in godoc:

```go
func main() {
  fmt.Println("Hello, world")
}
```

## Usage

First, install the binary:

```
go get -u github.com/sectioneight/md-to-godoc
```

Then, run it on one or more packages. If you'd like to generate a `doc.go` file
in the current package (that already has a `README.md`), simply run
`md-to-godoc` with no flags:

```bash
md-to-godoc
```

## Advanced usage

To generate `doc.go` for all subpackages, you can do something like the
following:

```bash
find . -name README.md \
       -not -path "./vendor/*" | \
       xargs -I% md-to-godoc -input=%
```

## Licence

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)
