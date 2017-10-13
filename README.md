```
     /\     (_)       
    /  \     _   _ __ 
   / /\ \   | | | '__|
  / ____ \  | | | |   
 /_/    \_\ |_| |_|   
 
Live reload for Go apps
```

[![CircleCI](https://circleci.com/gh/cosmtrek/air/tree/master.svg?style=shield)](https://circleci.com/gh/cosmtrek/air/tree/master)

## Motivation

When I get started with developing websites in Go and [gin](https://github.com/gin-gonic/gin) framework, it's a pity 
that gin lacks live-reloading function. In fact, I tried [fresh](https://github.com/pilu/fresh) and it seems not much 
flexible, so I intended to rewrite it in a better way. Finally, Air's born. 
In addition, great thanks to [pilu](https://github.com/pilu), no fresh, no air :)

Air is a terminal command for live-reloading Go applications. Just `air` in your project root directory, leave it alone,
and focus on your code.

## Installation

```bash
go get github.com/cosmtrek/air
```

## usage

First enter into your project

```bash
cd /path/to/my_project
```

The simplest usage is run

```bash
# start air with defaults
air
```

While I prefer the second way

```bash
# 1. create a new file
touch .air.conf

# 2. paste the air preference following into this file, and modify it to satisfy your needs

# 3. run air with your configs
air -c ./.air.conf
```

Here is the complete air preference:

```toml
# TOML format

# where runner watches
root = "."
tmp_path = "./tmp"

[build]
bin = "./tmp/server"
cmd = "go build -o ./tmp/server ./cmd/server"
log = "server-errors.log"
include_ext = ["go", "tpl", "tmpl", "html"]
exclude_dir = ["assets", "tmp", "vendor"]
delay = 1000 # ms

[color]
main = "magenta"
watcher = "cyan"
build = "yellow"
runner = "green"
app = "white"
```

## Contributing

PRs are welcome~
