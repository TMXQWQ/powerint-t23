
PREFIX := /usr/lib/
NAME := bash
LIBS := $(PREFIX)$(NAME)/libs
SOURCE := src

all: help

install: FORCE

	mkdir -p $(PREFIX)$(NAME)
	mkdir -p $(LIBS)
	copy $(SOURCE)/Classes.sh $(LIBS)/Classes.sh
	copy $(SOURCE)/Errors.sh $(LIBS)/Error.sh
	copy $(SOURCE)/Import.sh $(LIBS)/Import.sh
	copy $(SOURCE)/Logger.sh $(LIBS)/Logger.sh
	copy $(SOURCE)/Types.sh $(LIBS)/Types.sh
	copy $(SOURCE)/UnitTests.sh $(LIBS)/UnitTests.sh
	copy $(SOURCE)/dotenv.sh $(LIBS)/dotenv.sh
	copy -rf $(SOURCE)/utils $(LIBS)/utils

	if [ "$BASHPP_LIBS" = "" ]; then \
		export BASHPP_LIBS=$(LIBS); \
		sudo echo "BASHPP_LIBS=$(LIBS)" >> /etc/environment; \
	fi

uninstall: FORCE

	sudo rm -rf $(PREFIX)$(NAME)

help: FORCE

	@echo "Bash - help section"
	@echo ""
	@echo "About:"
	@echo "  Bash++ Is a bash framework to make bash an OO programming language."
	@echo "  It also brings new functionalities such as: Unit Testing, "
	@echo "  Logging, Importing, Types, Classes, Erorrs and many more to come"
	@echo ""
	@echo "Usage:"
	@echo "  make [...options] [command]"
	@echo ""
	@echo "Available commands:"
	@echo "  install   		- Install bash++"
	@echo "  uninstall 		- Uninstall bash++"
	@echo "  help     		- Show this message"
	@echo ""

.PHONY: FORCE
