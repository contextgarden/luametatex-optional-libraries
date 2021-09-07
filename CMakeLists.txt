cmake_minimum_required(VERSION 3.5)
project(context-optional-libraries C)

include(GNUInstallDirs)

add_library(zint SHARED
	# common
	zint/backend/common.c
	zint/backend/library.c
	zint/backend/large.c
	zint/backend/reedsol.c
	zint/backend/gs1.c
	zint/backend/eci.c
	zint/backend/general_field.c
	zint/backend/sjis.c
	zint/backend/gb2312.c
	zint/backend/gb18030.c
	# one dim
	zint/backend/code.c
	zint/backend/code128.c
	zint/backend/2of5.c
	zint/backend/upcean.c
	zint/backend/telepen.c
	zint/backend/medical.c
	zint/backend/plessey.c
	zint/backend/rss.c
	# postal
	zint/backend/postal.c
	zint/backend/auspost.c
	zint/backend/imail.c
	zint/backend/mailmark.c
	# two dim
	zint/backend/code16k.c
	zint/backend/codablock.c
	zint/backend/dmatrix.c
	zint/backend/pdf417.c
	zint/backend/qr.c
	zint/backend/maxicode.c
	zint/backend/composite.c
	zint/backend/aztec.c
	zint/backend/code49.c
	zint/backend/code1.c
	zint/backend/gridmtx.c
	zint/backend/hanxin.c
	zint/backend/dotcode.c
	zint/backend/ultra.c
	# output
	zint/backend/vector.c
	zint/backend/ps.c
	zint/backend/svg.c
	zint/backend/emf.c
	zint/backend/bmp.c
	zint/backend/pcx.c
	zint/backend/gif.c
	zint/backend/png.c
	zint/backend/tif.c
	zint/backend/raster.c
	zint/backend/output.c
)
target_compile_definitions(zint PRIVATE NO_PNG)
target_link_libraries(zint -lm)

add_library(mujs SHARED
	mujs/one.c
)

install(TARGETS zint mujs
        LIBRARY
        ARCHIVE
        RUNTIME
        INCLUDES
)
