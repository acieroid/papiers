# Papiers

*Papiers* is a tool to index your pdf files/research papers/… and quickly search through them.

## Build instructions

- Install batteries, yojson, ANSITerminal, uri, camlzip and cmdliner (`opam install batteries yojson ANSITerminal uri camlzip cmdliner` if you have opam)
- Edit the `src/config.ml` if you want to change the default reader for the sources (default: `xdg-open`), or the colors.
- Then:
```
./configure  
make && sudo make install
```

## How to use *Papiers*

*Papiers* now works a bit like *git*: you have *papiers* repositories;
 a repository is located in a directory, and index sources that are
 contained in this directory.

- Initialize a new repository in the current directory: `papiers init`
- Add documents to the database: `papiers doc add interesting_paper.pdf`
- Make queries to the database: `papiers search keyword1 keyword2`
- Type `papiers --help` to see the other possibilities

A query is more or less simply a list of keywords, that are searched through the
documents informations, like the title, authors, sources and tags.

You may want to refine this keyword based search. It is possible in some way by
using prefixes:

- If you prepend a keyword with `tag:` or `ta:`, it will only match tags.
- Prepend with `title:` or `ti:`, it'll search only in titles.
- With `a:`, `au:` or `author:`, only in authors.
- With `s:`, `src:` or `source:`, only in sources.
