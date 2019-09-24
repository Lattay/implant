Disclaimer: This project is in a very early stage and will probably change a lot.

Implant is not a package manager.
It merely aims at making easy to install locally projects containing executable files in a standardized
manner.
It is a very simple single file bash script that should work on most UNIX-like platform.

# Installation

implant depend on:
* basic POSIX tools (cd, ls, grep, sed...)
* bash
* jq (a JSON parser)
* git

Install implant with implant itself by running the following:
```bash
bash <(curl https://raw.githubusercontent.com/Lattay/implant/master/implant) get lattay/implant
```

# Usage
To get lst of commands type
```bash
implant help
```

To install a package, it must be available as a git remote (on github, gitea, bitbucket...)
and contain a `package.json` at the root.
The minimal `package.json` is the following:
```JSON
{
    "name": "my package name",
    "scripts": [
        "path/to/some/cli"
    ]
}
```

For example to install ubiq from my github you would type
```bash
implant get lattay/ubiq
```

To install a repo from anything else, pass the full git remote url:
```bash
implant get git@mygit:lattay/my_proj
```

```bash
implant get https://bitbucket.org/lattay/another_proj
```

You can update the package with
```bash
implant update ubiq
```

You can uninstall the package with
```bash
implant remove ubiq
```
