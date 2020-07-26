# pynq-skynet
项目内容：在PYNQ-Z2这样的资源受限平台上，实现无人机场景下的单一目标识别系统，达到实时检测帧率和可接受的识别准确率。由于不具备摄像头等外设，目前计划将待识别的图片存入SD卡，通过PS读取，传输到PL端进行实时处理，处理部分使用HLS实现，目标检测出的边界框和分类结果通过hdmi显示。

预期结果：实现无人机目标的实时精确识别，指标达到0.6mAP和30fps以上

技术方案：参考今年DAC比赛亚军SkrSkr团队的设计，将skynet部署到pynq-z2的pl上，对于明显的资源限制，我们将压缩算法的并行度，做更激进的剪枝量化操作，在资源、速度和精度间进行仔细权衡。

知识点：卷积神经网络、剪枝、量化、HLS程序设计和优化、SD卡读写和HDMI显示的vivado设计流程

![image](https://github.com/silverfly1992/pynq-skynet/blob/master/images/2020Xilinx.JPG)
