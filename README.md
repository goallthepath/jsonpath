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

## Philosophy

Tools should be obvious. No flags, no syntax, no docs to read.
