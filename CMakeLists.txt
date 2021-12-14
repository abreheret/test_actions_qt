cmake_minimum_required(VERSION 3.2)
project(QtNotepad)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt5Widgets REQUIRED)
find_package(Qt5Gui REQUIRED)

qt5_wrap_ui(UI_HDRS notepad.ui )
qt5_add_resources(MOCED_RESOURCES notepad.qrc)

include_directories(${CMAKE_CURRENT_BINARY_DIR})

add_executable(QtNotepad MACOSX_BUNDLE WIN32
    main.cpp notepad.cpp notepad.h notepad.ui
	${MOCED_RESOURCES}
	${UI_HDRS})
target_link_libraries(QtNotepad Qt5::Gui Qt5::Widgets) # Qt5::Core)	

# qt_add_executable(notepad
    # main.cpp
    # notepad.cpp notepad.h notepad.ui
# )

# set_target_properties(notepad PROPERTIES
    # WIN32_EXECUTABLE TRUE
    # MACOSX_BUNDLE TRUE
# )
# target_link_libraries(notepad PUBLIC
    # Qt::Core
    # Qt::Gui
    # Qt::Widgets
# )


# Resources:
# set(notepad_resource_files
    # "images/bold.png"
    # "images/copy.png"
    # "images/create.png"
    # "images/cut.png"
    # "images/edit_redo.png"
    # "images/edit_undo.png"
    # "images/exit.png"
    # "images/font.png"
    # "images/info.png"
    # "images/italic.png"
    # "images/new.png"
    # "images/open.png"
    # "images/paste.png"
    # "images/pencil.png"
    # "images/print.png"
    # "images/save.png"
    # "images/save_as.png"
    # "images/underline.png"
# )

# qt6_add_resources(notepad "notepad"
    # PREFIX
        # "/"
    # FILES
        # ${notepad_resource_files}
# )
