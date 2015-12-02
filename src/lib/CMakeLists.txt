# ==============================================================================
# ReadLine CMake File
# ==============================================================================

# include subdirectories -------------------------------------------------------
IF(DEFINED WIN32)
	INCLUDE_DIRECTORIES("pdcurses")
	ADD_SUBDIRECTORY(pdcurses)
ENDIF(DEFINED WIN32)

INCLUDE_DIRECTORIES("readline")
ADD_SUBDIRECTORY(readline)

