#==============================================================================
# 
#        OpenSees -- Open System For Earthquake Engineering Simulation
#                Pacific Earthquake Engineering Research Center
#
#==============================================================================

target_sources(OPS_Domain
    PRIVATE
    Mesh3DSubdomain.cpp
    GeometricBrickDecorator.cpp
    DRMBoundaryLayerDecorator.cpp
    DRMLoadPattern.cpp
    DRMLoadPatternWrapper.cpp
    DRMInputHandler.cpp
    PlaneDRMInputHandler.cpp
    PUBLIC
    Mesh3DSubdomain.h
    GeometricBrickDecorator.h
    DRMBoundaryLayerDecorator.h
    DRMLoadPattern.h
    DRMLoadPatternWrapper.h
    DRMInputHandler.h
    PlaneDRMInputHandler.h
)

if (HDF5_FOUND)
target_sources(OPS_Domain
    PRIVATE
        H5DRM.cpp
        H5DRM2D.cpp
    PUBLIC
        H5DRM.h    
        H5DRM2D.h    
)
endif()

target_include_directories(OPS_Domain PUBLIC ${CMAKE_CURRENT_LIST_DIR})

