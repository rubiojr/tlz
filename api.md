# Global Functions

## new_client

new_client creates a client for interacting with the Timelinize API.

### Parameters

- base_url: The base URL of the Timelinize server (e.g., "http://localhost:12002")
- repo_id: Repository ID to perform operations on (must exist)

### Returns

A client object with methods to interact with the Timelinize API

### Example

```go
// Example usage of new_client
new_client(base_url, repo_id)
```

# Classes
## client

### import_files

import_files imports files into a specified data source in the repository.

#### Parameters

- data_source: Name of the data source
- filenames: List of files to import
- processing_options: Options controlling how data is processed during import

#### Returns

An HTTP response object

#### Example

```go
// Example usage of import_files
client.import_files(data_sources, filenames, opts)
```

### open_repositories

open_repositories lists all open repositories

#### Returns

An HTTP response object. Call .json() to parse the response

#### Example

```go
// Example usage of open_repositories
client.open_repositories()
```

### file_selector_roots

file_selector_roots retrieves file selector roots from the API

#### Returns

An HTTP response object. Call .json() to parse the response

#### Example

```go
// Example usage of file_selector_roots
client.file_selector_roots()
```

### open_repository

open_repository opens an existing repository or creates a new one

#### Parameters

- path: The filesystem path where the repository lives
- create: Boolean indicating whether to create the repository if it doesn't exist

#### Returns

An HTTP response object. Call .json() to parse the response

#### Example

```go
// Example usage of open_repository
client.open_repository(path, create)
```

### search_items

search_items searches for items in the repository

#### Parameters

- repo: Repository ID
- opts: Search parameters object, which can include:
- datasource: Data source to search within
- data_text: Array of strings for exact text matching
- semantic_text: String for semantic search

#### Returns

An HTTP response object. Call .json() to parse the response

#### Example

```go
// Example usage of search_items
client.search_items(repo, opts)
```

### datasources

datasources retrieves available data sources

#### Returns

An HTTP response object. Call .json() to parse the response

#### Example

```go
// Example usage of datasources
client.datasources()
```

### charts

charts returns statistics about the timeline for use in charts

#### Parameters

- name: The chart name
- datasources
- periodical
- classifications
- recent_data_sources

#### Returns

No return information available.

#### Example

```go
// Example usage of charts
client.charts(name)
```
