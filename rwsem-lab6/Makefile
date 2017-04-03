obj-m := rwsem.o

KVERSION := $(shell uname -r)
KDIR := /lib/modules/$(KVERSION)/build
PWD := $(shell pwd)

default:
	$(MAKE) -C $(KDIR) M=$(PWD) modules
	make tryit
	bash run_rwsem

clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean
	rm -f tryit
	bash close_rwsem
