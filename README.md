# tuto

tuto is a tutorial generator. It helps you maintain series of patches, and
generate corresponding project repositories as well as a text document (be it
Markdown, or whatever) with all those patches, in order.

Patches are stored as text files, outside of the project repository tree.
You start working from a git repository, then explain your changes in commit
message bodies.

Here's an example session:
```
$ git clone https://github.com/radareorg/radare2 workspace
$ git init course
$ cd workspace
$ tuto init ../course/patches
$ cat >>README.md <<EOF
## Extra
Here's an extra section.
EOF
$ git add README.md
$ tuto commit extra
$ tuto generate >tutorial.md
$ cd ../course
$ git add patches
$ git commit -m "Add a step"
```
