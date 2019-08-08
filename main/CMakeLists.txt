set(COMPONENT_SRCS "main.c" camera/camera.c)

set(COMPONENT_ADD_INCLUDEDIRS
  camera/include
  conversions/include
)

set(COMPONENT_PRIV_INCLUDEDIRS
  camera/private_include
  sensors/private_include
  conversions/private_include
)

register_component()
