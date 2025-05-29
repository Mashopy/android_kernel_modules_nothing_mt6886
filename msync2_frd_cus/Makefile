all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)
ifneq (,$(wildcard ../msync2_frd_int))
	$(MAKE) -C $(KERNEL_SRC) M=$(M)/../msync2_frd_int modules $(KBUILD_OPTIONS)
	cp -r $(O)/$(M)/../msync2_frd_int/*.ko $(O)/$(M)/*.ko
endif

modules_install:
ifeq (,$(wildcard ../msync2_frd_int))
	$(MAKE) M=$(M) -C $(KERNEL_SRC) modules_install
else
	$(MAKE) M=$(M)/../msync2_frd_int -C $(KERNEL_SRC) modules_install
endif

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
ifneq (,$(wildcard ../msync2_frd_int))
	$(MAKE) -C $(KERNEL_SRC) M=$(M)/../msync2_frd_int clean
endif
