# vim: syntax=cmake
include_directories(.)
include_directories(../../common/h264/)
include_directories(../../../codec/enc/h264/)

# hal h264 header
set(HAL_H264E_HDR
    hal_h264e_vepu.h
   )

# hal h264 encoder sourse
set(HAL_H264E_SRC
    hal_h264e_vepu2_v2.c
    hal_h264e_vepu_v2.c
    hal_h264e_vpu_tbl.c
    hal_h264e_vepu2.c
    hal_h264e_vepu1.c
    hal_h264e_header.c
    hal_h264e_rc.c
   )

add_library(hal_h264e_vpu STATIC
            ${HAL_H264E_HDR}
            ${HAL_H264E_SRC}
           )

target_link_libraries(hal_h264e_vpu hal_h264e ${CODEC_H264E})
set_target_properties(hal_h264e_vpu PROPERTIES FOLDER "mpp/hal")
