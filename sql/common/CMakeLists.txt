
SET(LOCAL_FILES
    pgRouting-header.sql
    _point_toId.sql
    _startPoint.sql
    _endPoint.sql
    pgrouting_utilities.sql
    pgr_parameter_check.sql
    utilities_pgr.sql
    createIndex.sql
    )

foreach (f ${LOCAL_FILES})
    configure_file(${f} ${f})
    list(APPEND PACKAGE_SQL_FILES  ${CMAKE_CURRENT_BINARY_DIR}/${f})
endforeach()

set(PGROUTING_SQL_FILES ${PGROUTING_SQL_FILES} ${PACKAGE_SQL_FILES} PARENT_SCOPE)

configure_file(pgrouting.control pgrouting.control)
