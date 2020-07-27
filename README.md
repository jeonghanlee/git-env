# Configuration Environment for git

![Linter Run](https://github.com/jeonghanlee/git-env/workflows/Linter%20Run/badge.svg)

## Check the version one would like to use

Update the `configure/RELEASE` file by using `RELEASE.local`

```bash
$ echo "SRC_TAG:=tags/v2.28.0" > configure/RELEASE.local
$ make vars
APPNAME = git
DOCURL = https://github.com/git/git
FILTER = 1
INSTALL_LOCATION = /home/jhlee/git
LEVEL = 1
SITE_TEMPLATE_PATH = /home/jhlee/gitsrc/git-env/site-template
SRC_GITURL = https://github.com/git/git
SRC_NAME = git
SRC_PATH = git-src
SRC_TAG = tags/v2.28.0
SRC_URL = https://github.com/git
SUDO =
SUDO_INFO = 0
```

## Normal installation

Git will be installed in `${HOME}/bin`

```bash
make init
make build
make install
```

```bash
git-env (master)$ ~/bin/git --version
git version 2.28.0
```

## More specific installation

* Packages : asciidoc, libpcre2-dev. `make install.pkgs` if the system is Debian 10.
* `INSTALL_LOCATION` in `configure/CONFIG_SITE` according to your desired location.
* Support POSIX threads
* Support PCRE2
* Define the default git editor

```bash
make configure
```

* Install minimal git

```bash
make build
make install
```

* Install all include documentatation.

```bash
make build.all
make install.all
```

## Execute

```bash
jhlee@parity: git-env (master)$ tree -L 2 ~/git
/home/jhlee/git
├── [jhlee    4.0K]  bin
│   ├── [jhlee     19M]  git
│   ├── [jhlee    159K]  git-cvsserver
│   ├── [jhlee    345K]  gitk
│   ├── [jhlee     19M]  git-receive-pack
│   ├── [jhlee     12M]  git-shell
│   ├── [jhlee     19M]  git-upload-archive
│   └── [jhlee     19M]  git-upload-pack
├── [jhlee    4.0K]  libexec
│   └── [jhlee    4.0K]  git-core
└── [jhlee    4.0K]  share
    ├── [jhlee    4.0K]  git-core
    ├── [jhlee    4.0K]  git-gui
    ├── [jhlee    4.0K]  gitk
    ├── [jhlee    4.0K]  gitweb
    ├── [jhlee    4.0K]  locale
    └── [jhlee    4.0K]  perl5

git-env (master)$ ~/git/bin/git --version
git version 2.28.0
```

Enjoy your the latest git!
