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
- (wsl) filedir/devrdev.c add "#include <sys/sysmacros.h>"
- (wsl) stdio/buf.c
   - delete 
    ```c
    #ifdef _LP64
    #define _flag __pad[4]
    #define _ptr __pad[1]
    #define _base __pad[2]
    #endif
    ```
   - change
    ```c
    int
    is_unbuffered(FILE *fp)
    {
        return(fp->_flags & _IONBF);
    }

    int
    is_linebuffered(FILE *fp)
    {
        return(fp->_flags & _IOLBF);
    }

    int
    buffer_size(FILE *fp)
    {
    #ifdef _LP64
        return(fp->_IO_buf_end - fp->_IO_buf_base);
    #else
        return(BUFSIZ);	/* just a guess */
    #endif
    }
    ```
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
