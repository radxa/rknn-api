# rk_ssd_demo

## Introduction

- rk_ssd_demo is a dome of how to use NPU on 3399pro, the model of demo based on ssd-mobilenetv1

## Compilation

- Open the project file by Android Studio, build and generate apk (need NDK support, verified on android-ndk-r16b)
- ssd.rknn is converted from ssd-mobilenetv1.pb using RKNN Toolkit，refer to the [reference](<https://dl.radxa.com/rockpin10/docs/sw/rknn-toolkit/Rockchip_User_Guide_RKNN_Toolkit_V1.3.0_EN.pdf>) of RKNN Toolkit for conversion methods

## Code Structure

The code has three main parts：

- JAVA: com.rockchip.gpadc.ssddemo: Read the camera input, call jin for inference, and display the results
- JAVA: com.rockchip.gdapc.demo.glhelper: Wrapper of opengl function, used for 2D rendering, format conversion, etc., the main purpose is to reduce CPU usage
- JNI: Call rknn_api for the actual inference
