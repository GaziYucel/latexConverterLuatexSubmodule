# Install LuaTex compiler for use on a webserver

If we want to use LuaTex in a web application, it's recommended to install the compiler in the public tree within the web application such as OJS.
As the web application is run with an user which do not have login shell and cannot use the compiler using the single-user or system-wide installation.
LuaTex has a script which does the installation, by downloading all dependencies to a given directory. 
For this script to work, `rsync` is used. This is not a standard package in Debian and needs to installed separately.

## Environment
- Platform: Debian GNU/Linux 11 bullseye (x86-64)
- Webserver: Apache or Nginx
- Web application: OJS
- Plugin name: laTexConverter

## Remarks
- Installing `rsync` package needs elevated shell access, such as `sudo`.

## Install rsync
rsync is a file-copying tool which can copy locally and to/from a remote host. As rsync is not installed by default, this needs to be installed separately.
- `sudo apt update`
- `sudo apt install rsync`

## Create directory in webserver public folder
The installation directory could be within the plugin which will use LuaTex. We could also choose to install this in a more generic directory in the web application such as `/var/www/html/public`, assuming ojs is installed in `/var/www/html`. In this
example we will use the plugin directory, thus `/var/www/html/plugins/generic/laTexConverter/luatex`
- `cd /var/www/html/plugins/generic/laTexConverter`
- `sudo mkdir luatex`
- `cd luatex`

## Install the LuaTex compiler

## Download install script
- `sudo rsync -ptv rsync://contextgarden.net/standalone/setup/first-setup.sh ./first-setup.sh`

## Execute install script
This script will download all parts of the application to the current directory.
- `sudo ./first-setup.sh`

## Execute install script from PHP
This is a simple example of how we could install the compiler from within PHP. This should be useful if we would install LuaTex as part of installing the plugin.
```
echo "<pre>";
$luatexDir = 'luatex';
if(!file_exists($luatexDir)){
    mkdir($luatexDir, 755);
    exec("cd $luatexDir; rsync -ptv rsync://contextgarden.net/standalone/setup/first-setup.sh ./first-setup.sh; ./first-setup.sh", $execOutput);
    echo implode(PHP_EOL, $execOutput) . PHP_EOL;
}
echo "</pre>";
```

## Usage from within PHP
- //todo: add description here

## References
- https://distribution.contextgarden.net/setup
- https://wiki.contextgarden.net/ConTeXt_Standalone#Apache_webserver_installation
