obj-m := given.o
obj-m += queue_a.o

KVERSION := $(shell uname -r)
KDIR := /lib/modules/$(KVERSION)/build
PWD := $(shell pwd)

JC = javac
.SUFFIXES: .java .class
.java.class: $(JC) $(JFLAGS) $*.java

default: cfiles jfiles

jfiles:
	$(JC) Batt.java

cfiles:
	$(MAKE) -C $(KDIR) M=$(PWD) modules

clean:
	$(MAKE) -C $(KDIR) M=$(PWD) clean
	$(RM) *.class
install:
	$(MAKE) -C $(KDIR) M=$(PWD) modules_install

