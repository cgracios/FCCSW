################################################################################
# Package: DataObjects
################################################################################
gaudi_subdir(DataObjects v1r0)

# this declaration will not be needed in the future
gaudi_depends_on_subdirs(GaudiAlg)

find_package(HepMC)
find_package(FastJet)
find_package(ALBERS)

gaudi_add_dictionary(DataObjects dict/dictionary.h  dict/dictionary.xml
                     INCLUDE_DIRS DataObjects ALBERS
                     LINK_LIBRARIES DataObjects ALBERS)

gaudi_add_library(DataObjects
		  src/*.cc
                  INCLUDE_DIRS HepMC FastJet 
                  LINK_LIBRARIES HepMC GaudiAlgLib
		  PUBLIC_HEADERS DataObjects)
