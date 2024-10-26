
EXAMPLES       := $(EXAMPLES-yes:%=doc/examples/%$(PROGSSUF)$(EXESUF))
EXAMPLES_G     := $(EXAMPLES-yes:%=doc/examples/%$(PROGSSUF)_g$(EXESUF))
ALL_EXAMPLES   := $(EXAMPLES) $(EXAMPLES-:%=doc/examples/%$(PROGSSUF)$(EXESUF))
ALL_EXAMPLES_G := $(EXAMPLES_G) $(EXAMPLES-:%=doc/examples/%$(PROGSSUF)_g$(EXESUF))
PROGS          += $(EXAMPLES)

EXAMPLE_MAKEFILE := $(SRC_PATH)/doc/examples/Makefile
EXAMPLES_FILES := $(wildcard $(SRC_PATH)/doc/examples/*.c) $(SRC_PATH)/doc/examples/README $(EXAMPLE_MAKEFILE)

$(foreach P,$(EXAMPLES),$(eval OBJS-$(P:%$(PROGSSUF)$(EXESUF)=%) = $(P:%$(PROGSSUF)$(EXESUF)=%).o))
$(EXAMPLES_G): %$(PROGSSUF)_g$(EXESUF): %.o

examples: $(EXAMPLES)

$(EXAMPLES:%$(PROGSSUF)$(EXESUF)=%.o): | doc/examples
OUTDIRS += doc/examples

DOXY_INPUT += $(EXAMPLES:%$(PROGSSUF)$(EXESUF)=%.c)

install: install-examples

install-examples: $(EXAMPLES_FILES)
	$(Q)mkdir -p "$(DATADIR)/examples"
	$(INSTALL) -m 644 $(EXAMPLES_FILES) "$(DATADIR)/examples"
	$(INSTALL) -m 644 $(EXAMPLE_MAKEFILE:%=%.example) "$(DATADIR)/examples/Makefile"

uninstall: uninstall-examples

uninstall-examples:
	$(RM) -r "$(DATADIR)/examples"

examplesclean:
	$(RM) $(ALL_EXAMPLES) $(ALL_EXAMPLES_G)
	$(RM) $(CLEANSUFFIXES:%=doc/examples/%)

docclean:: examplesclean

-include $(wildcard $(EXAMPLES:%$(PROGSSUF)$(EXESUF)=%.d))

.PHONY: examples
