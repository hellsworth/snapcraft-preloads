CFLAGS += -g -O0 -Wall -Wstrict-prototypes

.PHONY: env-check clean

all: libpreload-semaphores.so

libpreload-semaphores.so: preload-semaphores.c
	${CC} \
		${CFLAGS} -fPIC -shared \
		${LDFLAGS} preload-semaphores.c \
		-o $@ -ldl

install: libpreload-semaphores.so
	install -m644 -D libpreload-semaphores.so ${DESTDIR}/lib/libpreload-semaphores.so

clean:
	rm -f \
		./lib/libpreload-semaphores.so
