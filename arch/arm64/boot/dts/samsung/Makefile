ifeq ($(CONFIG_SEC_A42XQ_PROJECT),y)
dts-dirs += a42/a42xq
else ifeq ($(CONFIG_SEC_A42XUQ_PROJECT),y)
else ifeq ($(CONFIG_SEC_A52XQ_PROJECT),y)
else ifeq ($(CONFIG_SEC_M62XQ_PROJECT),y)
else ifeq ($(CONFIG_SEC_GTS7XLLITE_PROJECT),y)
else ifeq ($(CONFIG_SEC_GTS7XLLITEWIFI_PROJECT),y)
endif

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(dtb-y))
endif

clean-files := *.dtb *.reverse.dts *.dtbo


