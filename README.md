# firefoxing
A repo to save all the information I collect about Firefox source, building process, hacking...


## Getting started

From **How to build Firefox** by _David Walsh_: https://davidwalsh.name/how-to-build-firefox

If you don't have an HG (Mercurial, software control version) client. You can download TortoiseHG here: https://tortoisehg.bitbucket.io/

```
hg clone https://hg.mozilla.org/mozilla-central/
cd mozilla-central
./mach bootstrap
```

Create a `mozconfig` file:

More info about `mozconfig` files here: https://firefox-source-docs.mozilla.org/build/buildsystem/mozconfigs.html

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

## Follow-up links

+ Codetribute for first issues: https://codetribute.mozilla.org/
+ Mozilla chat: https://chat.mozilla.org/#/welcome
+ Bugzilla: https://bugzilla.mozilla.org/home
+ Matrix: https://wiki.mozilla.org/Matrix
+ Discourse: https://discourse.mozilla.org/
+ SearchFox: https://searchfox.org
+ Contributors quick reference: https://firefox-source-docs.mozilla.org/contributing/contribution_quickref.html