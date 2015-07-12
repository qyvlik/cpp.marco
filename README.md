# c/c++ marco

## here are some marco that maybe usefule

### debug marco 

just debug, never exec the marco in program.

```c++

#define MACRO_TO_STRING(_marco) #_marco

#define DEBUG_MACRO(_marco) { \
    char  macro_string [] = MACRO_TO_STRING( (_marco) ); \
    int last =  sizeof( MACRO_TO_STRING( (_marco) )) -2; \
    macro_string[0] = ' '; \
    macro_string[last] = ' '; \
    std::cout << macro_string; \
}

```

how to use...

```c++

#include <iostream>

#define DECLARE_PRIVATE(_CLASSNAME) \
    class _CLASSNAME##Private { }
        

int main(int, char**)
{
    DEBUG_MACRO(
        /* this block code never exec. */
        /* you can use the \n to new aline. */
        DECLARE_PRIVATE(NONE); \n
        int a; \n
        int b; \n
    );
    return 0;
}

```

---

TODO