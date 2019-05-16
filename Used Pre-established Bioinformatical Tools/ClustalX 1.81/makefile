all: clustalx.exe

OBJECTS = interface.obj sequence.obj showpair.obj malign.obj \
  	util.obj trees.obj gcgcheck.obj prfalign.obj pairalign.obj \
  	calcgapcoeff.obj calcprf1.obj calcprf2.obj calctree.obj \
        readmat.obj alnscore.obj random.obj xdisplay.obj xscore.obj \
	xutils.obj xmenu.obj xcolor.obj clustalx.obj

HEADERS = general.h clustalw.h

CC	= c:\PROGRA~1\devstudio\vc\bin\cl
RC	= c:\PROGRA~1\devstudio\sharedide\bin\rc
LINK	= c:\PROGRA~1\devstudio\vc\bin\link



DFLAGS = -O


INCPATH = c:\ncbi\include.32
LIBPATH = c:\ncbi\build.m32

CFLAGS  = -c  -D "WIN32" -D "_WINDOWS" $(DFLAGS) -I$(INCPATH)
LFLAGS = /SUBSYSTEM:WINDOWS /STACK:0x10240 $(LF_EXTRA) 
guilibs= oldnames.lib kernel32.lib user32.lib gdi32.lib winspool.lib comdlg32.lib advapi32.lib shell32.lib

LIB1 = $(LIBPATH)\ncbi.lib
LIB2 = $(LIBPATH)\vibrant.lib


clustalx.res : clustalx.rc ncbilogo.ico
	$(RC) -r -I$(INCPATH) $*.rc

 
clustalx.exe : $(OBJECTS) clustalx.obj clustalx.res $(LIB1) $(LIB2)
	$(LINK)  @<<
/OUT:$*.exe
/MAP:$*.map
$(OBJECTS) *.res
$(LFLAGS) $(LIB1) $(LIB2) $(guilibs)
<<



clustalx.obj  : clustalx.c $(HEADERS)
	$(CC) $(CFLAGS) $*.c

xmenu.obj  : xmenu.c $(HEADERS) param.h
	$(CC) $(CFLAGS) $*.c

xutils.obj  : xutils.c $(HEADERS) param.h
	$(CC) $(CFLAGS) $*.c

xcolor.obj  : xcolor.c $(HEADERS) param.h
	$(CC) $(CFLAGS) $*.c

amenu.obj : amenu.c $(HEADERS) param.h
	$(CC) $(CFLAGS) $*.c

readmat.obj  : readmat.c $(HEADERS) 
	$(CC) $(CFLAGS) $*.c

trees.obj : trees.c $(HEADERS) 
	$(CC) $(CFLAGS) $*.c

.c.obj :
	$(CC) $(CFLAGS) $*.c

