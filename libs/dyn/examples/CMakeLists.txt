cmake_minimum_required(VERSION 3.15)

add_executable(app_dyn)

set_target_properties(app_dyn PROPERTIES 
    FOLDER "examples"
)

target_sources(app_dyn 
	PRIVATE  app_dyn.cpp
)

find_package(Qt5 COMPONENTS Core REQUIRED)
target_link_libraries(app_dyn 
	PRIVATE ${PROJECT_NAME}::dyn 
	PRIVATE Qt5::Core
)

##��������ʱ����
deploy_dependencies(TARGET app_dyn
    SEARCH_PATHS ${QT5_BINARIES_SEARCH_PATH}
)
