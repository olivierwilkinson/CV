# Setting up Mac for LaTeX

## Install MacTeX

- Download and install [MacTeX](https://www.tug.org/mactex/)
- Open TeX Live Utility and update

## Add executables to PATH

Add the following to `.zshrc` (or equivalent)

```sh
# Path to latex executables
export LATEXMK=/Library/TeX/texbin/latexmk
export LATEXINDENT=/Library/TeX/texbin/latexindent
export PATH=$PATH:$LATEXMK
export PATH=$PATH:$LATEXINDENT
```

## Setup Perl

Setup Perl via homebrew if it is not already. The system Perl is for Mac OS and
(will cause problems if used)[https://stackoverflow.com/questions/52682304/fatal-error-extern-h-file-not-found-while-installing-perl-modules/52997962#52997962]

```sh
brew install perl
```

Setup Perl to (use brew installation)[https://docs.brew.sh/Gems,-Eggs-and-Perl-Modules]

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

## Install LaTeX Workshop VSCode extension

VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop
