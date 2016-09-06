---
title: MCPL hooks in McStas
underconstruction: true
weight: 40
---

This page has yet to be fully written. For now, in addition to the few notes
below, refer to the almost complete information in: {% include linkpaper.html
subsection=3.3 %}.

Users of McStas do not need to download MCPL themselves, as it is included
inside McStas already since version 2.3. This gives access to two components,
MCPL_input and MCPL_output as described in {% include linkpaper.html
subsection=3.3 %}, as well as the mcpltool command described
[here](LOCAL:usage_cmdline).

## Notes for users of McStas version 2.3

Additionally, be aware that if you are using McStas version 2.3, you should
download updated versions of the component you will be using and place it in
your run directory:

* [MCPL_input.comp](https://github.com/McStasMcXtrace/McCode/raw/master/mcstas-comps/misc/MCPL_input.comp)
* [MCPL_output.comp](https://github.com/McStasMcXtrace/McCode/raw/master/mcstas-comps/misc/MCPL_output.comp)

This is because several important issues were identified and fixed in the
component codes after the release.

## Notes for users running in special environments

As from release 2.3 of McStas, linking to the MCPL-library
distributed with McStas is **automatic when using the GUI or the utility
scripts like mcrun**. If neither is available, such as may be the case in an HPC-environment,
library and include paths must be added to the build step. An example of this
could be (assuming McStas is installed in /usr/share/mcstas/2.3):

```shell
mcstas -t MyInstrument.instr 
cc -o MyInstrument.out MyInstrument.c \
   -I/usr/share/mcstas/2.3/libs/mcpl -L/usr/share/mcstas/2.3/libs/mcpl \
   -lmcpl -lm -O2
```