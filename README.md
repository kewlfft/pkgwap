# pkgwap
**PKG**BUILD **W**atch **A**nd **P**ush

Scan directory for PKGBUILDs, look for upstream updates, update the description and push to the AUR

## Goal
The objective of _pkgwap_ is to ease and automate as much as possible the update of user packages in the AUR. It scans directories for PKGBUILD files and compare them with the current AUR version and the upstream version.

* The latest upstream version can be figured out for **GitHub** projects and **Python** packages.

* The PKGBUILD can be enriched with an option named `_watch` providing an _URL_ where the latest version number can be found and the associated _regular expression_ to capture it within the HTML page.
```
_watch = ('https://www.upstreamsite.org/download' '<title>[a-zA-Z_-]*(\d[\d.]*\d+)</title>')
```

* Only the _URL_ can also be provided in `_watch`, in this case the hash of the page is calculated and it will warn next time if the upstream _URL_ is modified.
```
_watch = ('https://www.upstreamsite.org/download')
```

## Usage
Run `pkgwap -h` to see the full list of options. The basic usage consists in:
```
$ pkgwap directory_name
```
_pkgwap_ checks into `directory_name` and analyses the `PKGBUILD` files found, the sub-directories are also recursively scanned.

An environment variable `GITHUB_TOKEN` can be set to a GitHub OAuth token in order to raise the request limit for the GitHub API.
