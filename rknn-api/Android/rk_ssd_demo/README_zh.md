# rk_ssd_demo

## 简介

- rk_ssd_demo 是 3399pro 上如何调用 NPU 的 demo，该 demo 的基础模型是 ssd-mobilenetv1

## 使用说明

- 可以使用 Android Studio 编译该工程
- ssd.rknn 是使用 rknn toolkit 将 ssd-mobilenetv1.pb 转换而来，具体转换方法参考 rknn toolkit 的[参考文档](<https://dl.radxa.com/rockpin10/docs/sw/rknn-toolkit/Rockchip_User_Guide_RKNN_Toolkit_V1.3.0_CN.pdf>)

## 代码说明

代码分为三大部分：

- JAVA: com.rockchip.gpadc.ssddemo: 读取 camera 输入，并调用 jni 进行 inference，并将结果显示出来
- JAVA: com.rockchip.gdapc.demo.glhelper: 封装的 opengl 处理函数，用于 2D 纹理渲染，格式转换等，主要目的是降低 CPU 使用率
- JNI: 调用 rknn_api 进行实际 inference
