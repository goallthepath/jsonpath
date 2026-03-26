# jsonpath

Extract values from JSON without learning `jq`.

## What it does

Takes a simple dot-notation path and returns the value from JSON.

```bash
jsonpath user.address.city data.json
# → "Berlin"
```

## Why it exists

`jq` is powerful but overkill for 90% of use cases. You just want a value, not a query language.

## Installation

```bash
curl -fsSL https://raw.githubusercontent.com/goallthepath/jsonpath/main/jsonpath -o /usr/local/bin/jsonpath
chmod +x /usr/local/bin/jsonpath
```

Or clone and use directly:

```bash
git clone https://github.com/goallthepath/jsonpath.git
./jsonpath/jsonpath user.name data.json
```

## Usage

```bash
# From file
jsonpath user.name data.json

# From stdin
cat data.json | jsonpath user.name

# Nested paths
jsonpath users.0.email data.json

# Returns objects too
jsonpath user.address data.json
# → {"city": "Berlin", "zip": "10115"}
```

## Examples

```bash
# Extract API key from config
curl -s api.example.com/config | jsonpath api.key

# Get first item from array
cat users.json | jsonpath users.0.name

# Deep nesting
cat data.json | jsonpath company.departments.0.employees.2.email
```

## Philosophy

Tools should be obvious. No flags, no syntax, no docs to read.

## License

MIT
