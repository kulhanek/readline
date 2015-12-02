# ==============================================================================
# ReadLine CMake File
# ==============================================================================

SET(PDCURSES_LIB_SRC
		addch.c
		addchstr.c
		addstr.c
		attr.c
		beep.c
		bkgd.c
		border.c
		clear.c
		color.c
		debug.c
		delch.c
		deleteln.c
		deprec.c
		getch.c
		getstr.c
		getyx.c
		inch.c
		inchstr.c
		initscr.c
		inopts.c
		insch.c
		insstr.c
		instr.c
		kernel.c
		keyname.c
		mouse.c
		move.c
		outopts.c
		overlay.c
		pad.c
		panel.c
		printw.c
		refresh.c
		scanw.c
		scr_dump.c
		scroll.c
		slk.c
		termattr.c
		terminfo.c
		touch.c
		util.c
		window.c
		win32/pdcclip.c
		win32/pdcdisp.c
		win32/pdcgetsc.c
		win32/pdckbd.c
		win32/pdcscrn.c
		win32/pdcsetsc.c
		win32/pdcutil.c
        )

ADD_DEFINITIONS(-DBUILD_PDCURSES_DLL -DPDC_WIDE -DPDC_FORCE_UTF8)

# create shared library --------------------------------------------------------

ADD_LIBRARY(pdcurses_shared SHARED ${PDCURSES_LIB_SRC})

SET_TARGET_PROPERTIES(pdcurses_shared PROPERTIES
                        OUTPUT_NAME ${PDCURSES_LIB_NAME}
                        CLEAN_DIRECT_OUTPUT 1
                        VERSION ${PDCURSES_VERSION})
INSTALL(TARGETS
            pdcurses_shared
        DESTINATION
            lib
        )

#-------------------------------------------------------------------------------
