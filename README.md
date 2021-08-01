# apue
## readme

Read the file called DISCLAIMER.

On Freebsd, type "gmake".
On other platforms, type "make" (as long as this is gnu make).

For FAQs, updated source code, and the lost chapter, see http://www.apuebook.com.
Please direct questions, suggestions, and bug reports to sar@apuebook.com.

Steve Rago
January 2013


## compile
- apt-get update
- dpkg -L libbsd-dev
- apt-get install libbsd-dev
- (option) apt-get remove libbsd-dev
- (option) apt-get remove --auto-remove libbsd-dev
- cd apue.3e
- make
- cp ./include/apue.h /usr/include/
- cp ./lib/libapue.a /usr/local/lib/
- cp ./lib/libapue.a /usr/lib/
- new error.h
- (option) cp ./error.h /usr/include/

## vscode
- (win) install vscode plugin Remote-WSL
- (wsl) code .
