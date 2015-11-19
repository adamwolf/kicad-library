file(GLOB brd_files "*.brd")
file(GLOB equ_files "*.equ")
file(GLOB mod_files "*.mod")

install(FILES ${brd_files}
        DESTINATION ${KICAD_MODULES}
        COMPONENT resources)

install(FILES ${equ_files}
        DESTINATION ${KICAD_MODULES}
        COMPONENT resources)

install(FILES ${mod_files}
        DESTINATION ${KICAD_MODULES}
        COMPONENT resources)

if( APPLE )
    install(DIRECTORY packages3d
            DESTINATION ${KICAD_MODULES}/..
            COMPONENT resources
            PATTERN ".svn" EXCLUDE)
else()
    install(DIRECTORY packages3d
            DESTINATION ${KICAD_MODULES}
            COMPONENT resources
            PATTERN ".svn" EXCLUDE)
endif()
install(DIRECTORY footprints_doc
        DESTINATION ${KICAD_MODULES}
        COMPONENT resources
        PATTERN ".svn" EXCLUDE)
