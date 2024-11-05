# HOW TO

## Get the code

DO NOT USE `git clone`!

instead, use `gclient` to get the code:

```
gclient config --unmanaged https://github.com/CGQAQ/v8-template.git
# or if you have ssh access
gclient config --unmanaged git@github.com:CGQAQ/v8-template.git
cd v8-template
gclient sync
```
