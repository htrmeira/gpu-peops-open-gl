gpu-peops-open-gL
=================

Peops code modification to work with epsxe-1.9.0 in ubuntu 13.10

Links:
http://sourceforge.net/p/peops/support-requests/3/

"I ran into numerous problems building this package today, but finally got it to build. Getting the GPU package required similar steps adjusting the makefile paths.
The steps I had to take to get it to build:
Rename "GL_EXT.H" to "gl_ext.h" (problem you are running into)
Remove all occurrences of "-m" options in Makefile (to build 64 bit)
Remove the BOOL #define in externals.h, and sub all occurrences of "BOOL" with "bool" in source
Fix the Makefile OBJ path for a shared library from "/usr/X11R6/lib/libXxf86vm.a" to "/usr/lib/x86_64-linux-gnu/libXxf86vm.so", as well as adjust include and library paths for most dependencies.
To biuld the cfg tools, I had to replace GTK_WINDOWS_DIALOG with GTK_WINDOW_TOPLEVEL, it seems the former is deprecated, at least with the version of GTK I compiled with (gtk+-2.0).
The plugins load but cause the game to crash / halt before bios screen exits, likely due to my 'fixes'. I'd love to use the precompiled binaries but the only ones I have found are 32 bit and do not load into pcsxr."
