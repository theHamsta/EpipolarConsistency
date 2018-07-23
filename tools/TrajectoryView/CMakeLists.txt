find_package (Eigen3 3.2 REQUIRED NO_MODULE)
set(CMAKE_CXX_STANDARD 14)

# if(MSVC)
# set(ICON_RC icon_win.rc icon.ico)
# else()
# set(ICON_RC "")
# endif()

# The actual TrajectoryView executable
add_executable( TrajectoryView
	main_trajectoryview.cpp
	${ICON_RC}
)
target_link_libraries( TrajectoryView LibProjectiveGeometry LibUtilsQt GetSet GetSetGui Eigen3::Eigen)
qt5_use_modules(TrajectoryView Gui Svg OpenGL PrintSupport)
qt5_win32_copy_dlls(TrajectoryView "Core;Gui;Widgets;Svg;OpenGL;PrintSupport")
install(TARGETS TrajectoryView RUNTIME DESTINATION bin)
set_property(TARGET TrajectoryView PROPERTY FOLDER "Utilities") 
>>>>>>> 35729b14464c16b15632b7cc056dfee768f6314b
