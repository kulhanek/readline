# ==============================================================================
# ReadLine CMake File
# ==============================================================================

SET(READLINE_LIB_SRC
        readline.c
        vi_mode.c
        funmap.c
        keymaps.c
        parens.c
        search.c
        rltty.c
        complete.c
        bind.c
        isearch.c
        display.c
        signals.c
        util.c
        kill.c
        undo.c
        macro.c
        input.c
        callback.c
        terminal.c
        text.c
        nls.c
        misc.c
        xmalloc.c
        xfree.c
        history.c
        histexpand.c
        histfile.c
        histsearch.c
        shell.c
        mbutil.c
        tilde.c
        compat.c
        )

ADD_DEFINITIONS(-DBUILD_READLINE_DLL -DHAVE_CONFIG_H)

# create shared library --------------------------------------------------------

ADD_LIBRARY(readline_shared SHARED ${READLINE_LIB_SRC})

#TARGET_LINK_LIBRARIES(readline_shared )

SET_TARGET_PROPERTIES(readline_shared PROPERTIES
                        OUTPUT_NAME ${READLINE_LIB_NAME}
                        CLEAN_DIRECT_OUTPUT 1
                        VERSION ${READLINE_VERSION})
INSTALL(TARGETS
            readline_shared
        DESTINATION
            lib
        )

#-------------------------------------------------------------------------------