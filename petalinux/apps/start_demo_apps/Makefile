ifndef PETALINUX
$(error "Error: PETALINUX environment variable not set.  Change to the root of your PetaLinux install, and source the settings.sh file")
endif

include apps.common.mk

APP = start_demo_apps.sh

# Add any other object files to this list below
APP_OBJS = $(APP).o

all: build install

build: $(APP)

clean:

.PHONY: install image

install: $(APP)
	$(TARGETINST) -d -p 0755 $(APP) /home/root/$(APP)

%.o: %.sh

help:
	@echo ""
	@echo "Quick reference for various supported build targets for $(INSTANCE)."
	@echo "----------------------------------------------------"
	@echo "  clean                  clean out build objects"
	@echo "  all                    build $(INSTANCE) and install to rootfs host copy"
	@echo "  build                  build subsystem"
	@echo "  install                install built objects to rootfs host copy"
