find_package (Eigen3 3.2 REQUIRED NO_MODULE)
set(CMAKE_CXX_STANDARD 14)
if(MSVC)
set(ICON_RC icon_win.rc icon.ico)
else()
set(ICON_RC "")
endif()

add_executable( nrrdView
	nrrdView.cpp
	${ICON_RC}
)
target_link_libraries( nrrdView LibProjectiveGeometry LibUtilsQt GetSet GetSetGui Eigen3::Eigen)
install(TARGETS nrrdView RUNTIME DESTINATION bin)
set_property(TARGET nrrdView PROPERTY FOLDER "Utilities") 
