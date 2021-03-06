# Arylic TCP UART Command-Line-Tool

This is a very small (< 50 LOC) command line tool to interact with Arylic devices via their UART TCP API. It sends the command, and returns the response, nothing else.

```
usage: arylic-uart [option] ... 

A small CLI tool to interact with Arylic devices via the UART TCP API.

 Required:
 -c, --cmd VALUE                             The command you want to send, e.g. MCU+PAS+RAKOIT:VER
 -d, --device VALUE                          IP or URL (without protocol) of the Arylic device you want to send the command to

 Optional:
 -h, --help                                  Show this help message.
```

Will print the response when everything went well.

## Build instructions

This project uses [janet](janet-lang.org/). It is set up using [jpm](https://github.com/janet-lang/jpm) and you can find its configuration in [project.janet](./project.janet), the entry is in [main.janet](./main.janet). `.envrc` and `flake.nix` take care of dependencies if you have [direnv](https://direnv.net/) set up using [nix flakes](https://github.com/nix-community/nix-direnv) support.

To build run:

``` bash
jpm deps
jpm build
```

You will find a `arylic-uart` executable in the `build/` folder.

## UART API Docs

- https://web.archive.org/web/20211204170758/https://developer.arylic.com/download/SA50_TCP_API.pdf
- https://drive.google.com/file/d/1gOb4VBruyJgaBZJHClV6dEkoiwf5hkzE/view
- https://forum.arylic.com/t/latest-api-documents-and-uart-protocols/534
