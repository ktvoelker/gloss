MAKEFLAGS=--warn-undefined-variables

SDL2_CFLAGS	= -I/usr/local/include/SDL2 -D_THREAD_SAFE
SDL2_LIBS	= -L/usr/local/lib -lSDL2 -lSDL2_ttf

sources_test_c	= $(shell find src -name "*.c")
objects_test_c	= $(patsubst %.c,%.o,${sources_test_c})

bin/test: ${objects_test_c}
	clang -Wall -std=c99 -g ${SDL2_CFLAGS} ${SDL2_LIBS} $^ -o $@

.PHONY: clean
clean:
	find . -name "*.o" | xargs rm
	rm -f bin/test

%.o : %.c
	clang -Wall -Werror -std=c99 -O2 ${SDL2_CFLAGS} -c $< -o $@


