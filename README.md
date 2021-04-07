### Cross-compile GSL lib for MIPS uclibc
Run configure
```
./configure \
--prefix=$HOME/aws-install \
--target=mips-linux-uclibc-gnu \
-host=x86_64-linux-gnu \
CC=mips-linux-uclibc-gnu-gcc \
CFLAGS="-march=mips32r2 -O3 -DNDEBUG"
```

Edit `config.h`
```
# Comment out HAVE_GNUX86_IEEE_INTERFACE (line 213)

- #define HAVE_GNUX86_IEEE_INTERFACE 1
+ //#define HAVE_GNUX86_IEEE_INTERFACE 1
```

Build the project
```
make -j8
make install
``` 
