<div align="center">
  <h1>My CV</h1>
  <p>
    Written, built and released with love using LaTeX, GitHub Actions, and Semantic Release.
  </p>
</div>

<hr />

[![Build Status][build-badge]][build]
[![Latest Release][release-badge]][release]
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

## What is this?

My CV written in LaTeX format, with a GitHub Actions workflow
to generate a PDF which is added as an asset to release tags produced by
Semantic Release.

## Motivation

First and foremost: it sounded fun! There are a couple benefits though:

LaTeX is something I last used at university to write my dissertation and I
found that, while challenging, it gave me really great control over the final
document. Traditional word processors never gave me the same control I remember
having, and now it is not nearly as challenging as it was when I was new to
programming.

Having everything in a git repo also means I'll never have to search for my most
recent CV again. A nice bonus is that I'll have a nice history of my CV over the
years.

Using GitHub Actions to generate the final PDF document means I know the PDF
matches the source code, it also means I don't need to use Dropbox anymore.

I decided to use semantic-release to produce releases and then upload the
generated PDF as an asset to them so I can control the public facing iterations
using branches and commits.

## Setup

### Mac

#### Install MacTeX

- Download and install [MacTeX](https://www.tug.org/mactex/)
- Open TeX Live Utility and update

#### Add executables to PATH

Add the following to `.zshrc` (or equivalent)

```sh
# LaTeX
export LATEXMK=/Library/TeX/texbin/latexmk
export LATEXINDENT=/Library/TeX/texbin/latexindent
export PATH=$PATH:$LATEXMK
export PATH=$PATH:$LATEXINDENT
```

#### Setup Perl

Setup Perl via homebrew if it is not already. The system Perl is for Mac OS and
[will cause problems if used](https://stackoverflow.com/questions/52682304/fatal-error-extern-h-file-not-found-while-installing-perl-modules/52997962#52997962)

```sh
brew install perl
```

Setup Perl to [use brew installation](https://docs.brew.sh/Gems,-Eggs-and-Perl-Modules)

```sh
sudo cpan local::lib
```

Add the following to `.zshrc`

```sh
eval "$(perl -I$HOME/perl5/lib/perl5 -Mlocal::lib)"
```

Install required Perl modules

```sh
cpan YAML::Tiny
cpan File::HomeDir
cpan Unicode::GCString
```

### Install LaTeX Workshop VSCode extension

[VS Marketplace Link](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)

[build-badge]: https://img.shields.io/github/workflow/status/olivierwilkinson/CV/main/main?style=flat
[build]: https://github.com/olivierwilkinson/CV/actions?query=branch%3Amain+workflow%3Amain
[release-badge]: https://img.shields.io/github/v/release/olivierwilkinson/CV?display_name=release&style=flat
[release]: https://github.com/olivierwilkinson/CV/releases