# firefoxing
A repo to save all the information I collect about Firefox source, building process, hacking...


## Getting started

From **How to build Firefox** by _David Walsh_: https://davidwalsh.name/how-to-build-firefox

```
hg clone https://hg.mozilla.org/mozilla-central/
cd mozilla-central
./mach bootstrap
```

Create a `mozconfig` file:

```
# Automatically download and use compiled C++ components:
ac_add_options --enable-artifact-builds

# Write build artifacts to:
mk_add_options MOZ_OBJDIR=./objdir-frontend
```

Build

```
./mach build
```

Run

```
./mach run --jsdebugger
```

Update

```
hg pull && hg update --clean
```