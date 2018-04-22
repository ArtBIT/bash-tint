# bash-tint
[![Build Status](https://travis-ci.org/ArtBIT/bash-tint.svg)](https://travis-ci.org/ArtBIT/bash-tint) [![GitHub license](https://img.shields.io/github/license/ArtBIT/bash-tint.svg)](https://github.com/ArtBIT/bash-tint) [![GitHub stars](https://img.shields.io/github/stars/ArtBIT/bash-tint.svg)](https://github.com/ArtBIT/bash-tint)  [![awesomeness](https://img.shields.io/badge/awesomeness-maximum-red.svg)](https://github.com/ArtBIT/bash-tint)

Bash-tint aims to make your script's output nice and colorful, as easy as possible.
```bash
# Compare regular ANSI/VT100 Control sequences
echo -e "e[97m\e[46mT\e[49m\e[45mI\e[49m\e[43mN\e[49m\e[40mT\e[49m\e[39m is fun!"
# To the simplicity of tint:
tint "white(Cyan(T)Magenta(I)Yellow(N)Black(T)) is fun!"
```

It is more readable than the regular ANSI/VT100 Control sequences:
```bash
# Can you guess what will this output?
^[[97m^[[41mR^[[49m^[[43mA^[[49m^[[103mI^[[49m^[[42mN^[[49m^[[104mB^[[49m^[[44mO^[[49m^[[45mW^[[49m^[[39m$

# How about this?
tint "white(Red(R)Yellow(A)Light_yellow(I)Green(N)Light_blue(B)Blue(O)Magenta(W))"
```

It also comes with `tintf`, the colorful sister of `printf`:
```bash
tintf "Running test: bold(%s) %s" "Test XYZ" "green([OK])"
```


# Installation

## Manually
```
git clone https://github.com/ArtBIT/bash-tint.git
source path/to/bash-tint/src/tint
```

## Using [bash-clam](https://github.com/ArtBIT/bash-clam)
```
clam install ArtBIT/bash-tint && clam source ArtBIT/bash-tint/src/tint
```

# Usage

## Examples

<img src="/assets/example1.png">

```bash
tint "white(Cyan(T)Magenta(I)Yellow(N)Black(T)) is bold(really) easy to use."
```

<img src="/assets/example2.png">

```bash
tintf "Running test: bold(%s) %s" "Test XYZ" "green([OK])"
```

<img src="/assets/example3.png">

```bash
tintf "bold(%s) %s" "red([Error:])" "Could not load config file."
```

```bash
for (( i=0; i<=$(tput colors); i++ )); do tintf "Color($i)( )"; done;
```

# Credits
Inspired by https://misc.flogisoft.com/bash/tip_colors_and_formatting

# License

[MIT](LICENSE.md)
