# Copyright (C) Eta Scale AB. Licensed under the Eta Scale Open Source License. See the LICENSE file for details.

BENCHMARKS= myBenchmark


.SECONDEXPANSION:

DAE: BINDIR
	$(foreach bench, $(BENCHMARKS), \
	$(MAKE) -C $(bench)/src 2>&1 | tee $(bench)/bin/log.txt;)

BINDIR: $$(foreach bench, $$(BENCHMARKS), $$(bench)/bin)

%/bin:
	mkdir -p $@

clean:
	$(foreach bench, $(BENCHMARKS), \
	$(MAKE) -C $(bench)/src clean;)
