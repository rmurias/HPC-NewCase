# client-database-template

This is a client datbase template to be used with DEVONthink (organization, structure, binaries) and Obsidian (notes).

## Components

1. client-database-template (this repository) is a template repository containing the root structure of the database and placeholders for other sub-modules.
2. code-review-template is a template for a sub-module of the client-database-template located under the "Code Review" directory. This repository contains
   the root structure for code review containing all the individual vendor review notes.
3. code-review-vendor is a template for a sub-module of the code-review-template which will contain review notes and cites for a single vendor. Many cases
   will have multiple vendors, so each one will be located under the code-review-template directory.

## Procedure

1. Clone client-database-template into a folder named for the client, e.g. ABC-XYZ for law firm abbreviation ABC and end client abbreviation XYZ.
2. From inside the "Code Review" directory, clone a submodule for each vendor. To do this, issue the following commands, where <vendor> is the vendor name, e.g. "Nokia":
```
git submodule add [https://](https://github.com/rmurias/code-review-template.git) <vendor>
git submodule update --init --recursive
```
3. From inside the <vendor> directory, clone a submodule for each build. To do this, issue the following commands, where <build> is the build name, e.g. "22Q1":
```
git submodule add [https://](https://github.com/rmurias/code-review-vendor-template.git)
git submodule update --init --recursive
```
Note the locations of the sub-modules may change.
