CFLAGS  := -O3 -std=c++11 -Wall -Werror -Wno-unused-result -I..
LD      := g++ -O3
LDFLAGS := ${LDFLAGS} -libverbs -lrt -lpthread -lmemcached -lnuma

APPS    := main

all: ${APPS}

main: hrd_conn.o hrd_util.o main.o
	${LD} -o $@ $^ ${LDFLAGS}

%.o: %.cc
	g++ ${CFLAGS} -c -o $@ $<

PHONY: clean
clean:
	rm -f *.o ${APPS}
