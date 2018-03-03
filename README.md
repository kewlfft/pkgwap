# pkgwap
**PKG**BUILD **w**atch **a**nd **p**ush: scan directory for PKGBUILDs, look for upstream updates, update the description and push to the AUR

## Goal
The objective with _pkgwap_ is to ease and automate as much as possible the update of user packages in the AUR.

_pkgwap_ scans directories for PKGBUILD files and compare them with the current AUR version and the upstream version.

The upstream version can be successfully guessed for `github.com` projects and `python` packages.

It is possible to enrich the PKGBUILD with an option named `_watch` providing an _URL_ where the latest version can be found and the associated _regular expression_ to capture the version number in the page.

Example:
```
_watch = ('https://www.upstreamsite.org/download' '<title>[a-zA-Z_-]*(\d[\d.]*\d+)</title>')
