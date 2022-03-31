install(FILES
        meta-data.xml
        DESTINATION drbd_cstate
        COMPONENT ha
)

install(PROGRAMS
        action
        DESTINATION drbd_cstate
        COMPONENT ha
        )