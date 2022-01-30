<p align="center">
    <img src="assets/gtrace.svg" height="250" width="250"/>
</p>

</br>
Unofficial, simple yet effective Google Cloud Trace CLI tool.

</br></br>
# Installation
```
go install github.com/
```
go install github.com/moshebe/gtrace@latest
```

# Usage

```
› gtrace help
NAME:
   gtrace - Google Cloud Trace CLI tool

USAGE:
   Simple command-line tool for query and fetch tracing information from Cloud Trace API.
   Find more information at: https://cloud.google.com/trace/docs

VERSION:
   v1.0.0

COMMANDS:
   get      Get a specific trace by id from one or more projects
   list     Query traces from a project according to the given conditions
   url      Generate a browsable URL for a given trace
   format   Format trace spans according to a given template
   help, h  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --help, -h     show help (default: false)
   --version, -v  print the version (default: false)
```

# Examples

Fetch a specific trace from multiple projects:
```
gtrace get --project production-a,production-b 5e26a889fa12da351beee9ea16ce0a65
```

Format trace spans by a specific template:
```
gtrace format --input /tmp/trace.json --template "{{ .Name }}, {{ .Duration }}"
```

Query traces by multiple filters from the last 3 hours:
```
gtrace list --project dev --limit 10 --since 3h --filter service:api --filter user-id:1234
```

