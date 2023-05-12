# Description
This submodule is a copy from http://luatex.org/download.html (linux > x86-64). 

Using this submodule in another project is not recommended. Please download your version directly from http://luatex.org/download.html.

[LuaTeX](http://luatex.org) is an extended version of pdfTeX using Lua as an embedded scripting language. The LuaTeX project's main objective is to provide an open and configurable variant of TeX while at the same time offering downward compatibility. From the user perspective we have pdfTeX as stable and more or less frozen 8 bit engine, XeTeX as unicode input and font aware engine using libraries for font handling, and LuaTeX as engine that is programmable and delegates as much as possible to Lua, with the objective to keep the core engine lean and mean. Each engine has its benefits and drawbacks [more details here](http://luatex.org/roadmap.html#tbp).

## Requirements
- This submodule is meant to be used in the [Open Journal Systems](https://pkp.sfu.ca/software/ojs/download/) plugin [latexConverter](https://github.com/GaziYucel/latexConverter).
- Linux x86-64

## Usage

### Add submodule to your project
Add to repository
- `git submodule add https://github.com/GaziYucel/latexConverterLuatexSubmodule.git`

Commit to repository
- `git commit -m "submodule latexConverterLuatexSubmodule added"`

update submodule
- `git submodule update --recursive --remote --merge`

### Download LuaTex binaries for your environment

#### Ubuntu
Execute the script UpdateForUbuntu.sh from Terminal. 
- `sh ./ubuntu/UpdateForUbuntu.sh`
This script will install `rsync` if this is not installed. Next all binaries of LuaTex will be downloaded to the directory ubuntu.

#### Windows

### Usage in PHP in a web application
- //todo: add description here 

## Additional info
- http://luatex.org
- https://distribution.contextgarden.net/setup
- https://wiki.contextgarden.net/ConTeXt_Standalone#Apache_webserver_installation
