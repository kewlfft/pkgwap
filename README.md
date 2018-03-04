# pkgwap
_**pkg**build **w**atch **a**nd **p**ush_

Scan directory for PKGBUILDs, look for upstream updates, update the description and push to the AUR

## Goal
The objective of _pkgwap_ is to ease and automate as much as possible the update of user packages in the AUR. It scans directories for PKGBUILD files and compare them with the current AUR version and the upstream version.

* The upstream version can be successfully guessed for `github.com` projects and `python` packages.

* The PKGBUILD can be enriched with an option named `_watch` providing an _URL_ where the latest version number can be found and the associated _regular expression_ to capture it in the page.
```
_watch = ('https://www.upstreamsite.org/download' '<title>[a-zA-Z_-]*(\d[\d.]*\d+)</title>')
```

* If only an _URL_ is provided to `_watch` it will calculate the hash of the page and will warn in case the upstream _URL_ is changed next time _pkgwap_ is run.
```
_watch = ('https://www.upstreamsite.org/download')
```

## Instructions
An environment variable `GITHUB_TOKEN` can be set to a GitHub OAuth token in order to raise the request limit for the GitHub API.
