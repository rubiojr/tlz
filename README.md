# Timelinize Risor client and CLI

[Timelinize](https://github.com/timelinize/timelinize) Risor client provides a convenient way to interact with the Timelinize API using the Risor programming language. This package allows you to search, manage and import data into Timelinize repositories.

## Installation

This package is designed to be used with Risor. Make sure you have Risor installed before using this client.

## Basic Usage

```Go
import tlz

# Create a new Timelinize client.
# arg1: Timelinize URL
# arg2: Repository ID (the repository must exist)
#
repo := "35b953ea-5f60-4f4d-86f2-acb1c7a52644"
client := tlz.new_client("http://localhost:12002", repo)

# List open repositories.
#
client.open_repositories().json()

# List file selector roots.
#
client.file_selector_roots().json()

# Open existing or create a new repository
# path: the filesystem path where the repo lives
# create: create the repository if it doesn't exist
#
client.open_repository("/home/rubiojr/tmp/foobarstuff", false).json()

# Search items text
# repo: repo ID
# opts: search parameters (see https://github.com/timelinize/timelinize/blob/9dd00b724c1497df262be90f04229ac1b22e7f59/timeline/search.go#L40)
#
# Exact match
client.search_items(repo, { datasource: "firefox", data_text: ["guides and information"] }).json()
# Semantic search
client.search_items(repo, { datasource: "firefox", semantic_text: "guides" }).json()
```

## API documentation

See [api.md](/api.md).

## Examples

You can find more examples in the `examples` directory.

## CLI Usage

### Building the CLI

You'll need [rsx](https://github.com/rubiojr/rsx) installed, then:

`./script/build`

The Timelinize CLI provides command-line access to Timelinize functionality. Run with `--help` for usage information.

```
$ tlz --help
```
