# select the 3D backend for sokol_gfx.h and sokol_app.h
add_definitions(-D${sokol_backend})

if ((FIPS_WINDOWS OR FIPS_MACOS OR FIPS_LINUX) AND NOT FIPS_UWP)
fips_ide_group(Samples)
fips_begin_app(noentry-dll-sapp windowed)
    fips_vs_warning_level(3)
    fips_files(noentry-dll-sapp.c)
    #sokol_shader(noentry-dll-sapp.glsl ${slang})
    fips_deps(sokol-dll)
fips_end_app()
endif()
endif() #FIPS UWP
