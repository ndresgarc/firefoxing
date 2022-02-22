# firefoxing
A repo to save all the information I collect about Firefox source, building process, hacking...

## Building Firefox for Desktop in Windows 10

From _Building Firefox On Windows_ at https://firefox-source-docs.mozilla.org/setup/windows_build.html

Requirements:

+ 4GB RAM minimum, 8GB+ recommended.
+ 40GB of free disk space (at least)
+ Windows 10.
+ Build Tools para Visual Studio 2022
+ MozillaBuild
+ `mozilla-central` source code
+ **Patience** and ☕

If you don't have an HG (Mercurial, software control version) client. You can download TortoiseHG here: https://tortoisehg.bitbucket.io/

Git can be used as well, but not preferred. Some steps may vary.

Download and install **Build Tools para Visual Studio 2022** from https://aka.ms/vs/17/release/vs_BuildTools.exe.

Install **MozillaBuild**. It can be downloaded from https://ftp.mozilla.org/pub/mozilla.org/mozilla/libraries/win32/MozillaBuildSetup-Latest.exe


Clone `mozilla-central` repo. Better to do it in C:/.

```
hg clone https://hg.mozilla.org/mozilla-central/
```

Now we have Firefox source code in C:/mozilla-central

Download dependencies, compile stuff:

```
cd mozilla-central
mach bootstrap
```

Create a `mozconfig` file:

More info about `mozconfig` files here: https://firefox-source-docs.mozilla.org/build/buildsystem/mozconfigs.html

`mozconfig` file has to be created in the root directory: `C:/mozilla-central/mozconfig`

```
# Automatically download and use compiled C++ components:
ac_add_options --enable-artifact-builds

# Write build artifacts to:
mk_add_options MOZ_OBJDIR=./objdir-frontend
```

Build

```
mach build
```

Run

```
mach run

// mach run --jsdebugger
```

Update repo

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