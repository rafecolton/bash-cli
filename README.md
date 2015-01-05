bash-cli
========

A starter project for a bash cli application

> Your entire `script/` directory in one file

## Usage

### Install (or fork)

```bash
curl -sLOf https://raw.githubusercontent.com/rafecolton/bash-cli/master/script && chmod +x script
```

### Edit

Edit the `./script` file to add your own subcommands  Implement the following
functions to add subcommands:

* subcommand - add a subcommand by implementing `function subcommand_<your-command>()`
* description - add descriptions by implementing `function desc_<your-command>()`
* help text - add help text by implementing `function help_<your-command>()`

**IMPORTANT:** make sure the `_main "$@"` line remains the last line in
the file

### For Example

```bash
# -h
function desc__h() { echo "- display help text and exit" ; }
function help__h() { cat <<HELP
This is example help text for the "-h/--help" commands.
HELP
}
function subcommand__h() {
  _usage
  return 1 # optionally, return non-zero to have ./script exit err
}

# --help
function desc___help() { desc__h ; }
function help___help() { help__h ; }
function subcommand___help() { subcommand__h ; }
```
