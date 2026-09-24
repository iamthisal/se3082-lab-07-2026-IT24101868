CC = mpicc
CFLAGS = -Wall
TARGETS = ex1 sum_scatter sum_gather sum_reduce allreduce sum_scan
NP = 4

all: $(TARGETS)

ex1: ex1.c
	$(CC) $(CFLAGS) -o $@ $

sum_scatter: sum_scatter.c
	$(CC) $(CFLAGS) -o $@ $

sum_gather: sum_gather.c
	$(CC) $(CFLAGS) -o $@ $

sum_reduce: sum_reduce.c
	$(CC) $(CFLAGS) -o $@ $

allreduce: allreduce.c
	$(CC) $(CFLAGS) -o $@ $

sum_scan: sum_scan.c
	$(CC) $(CFLAGS) -o $@ $

run: all
	@for prog in $(TARGETS); do \
		echo "===== $$prog ====="; \
		mpirun -np $(NP) ./$$prog; \
		echo; \
	done

clean:
	rm -f $(TARGETS)

.PHONY: all run clean
