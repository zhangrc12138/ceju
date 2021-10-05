# Measure-Distance-by-Using-a-Monocular-Camera
单目行车测距摄像头 用于电子科技大学“创客杯”大赛
【摘  要】 在视觉系统的研究中，始终有一个技术难题，那就是单目测距，而该技术在机器人，无人机，以及汽车自动驾驶领域都具有很高的研究价值。
本项目立足于汽车行驶场景，结合当下流行的视觉处理算法与深度学习算法，仅使用一个单目摄像头便可精准地计算出该视点与前方车辆之间的实际距离。
首先，对车载摄像头传入的每一帧图像使用冗余切图法，结合YOLOV3目标识别模型，通过改进的边界框筛选算法，对所有的候选框进行多次筛选，最终得到车辆检测的边界框以及其在图像中的像素坐标。然后，使用图像处理中常用的边缘检测算法进行道路检测，并将图像的透视点锁定为视觉范围内道路的最远点。接着，用MiDas模型得到图像的相对深度图，采用寻找垂直方向差分最值的方法，在道路最远点附近进行遍历搜索，以水平像素的平均差分最大处作为图片中公路的地平线所在的像素位置。最后，设图像底边缘中心点为视觉测量的最近距离，地平线为视觉测量的最远距离，车辆识别得到的边界框的底边中点为汽车所在的实际像素坐标，根据线性投影算法，实现像素坐标到空间坐标的转化，得到真实的空间距离。
本文对整个系统中的所有涉及到的算法进行了详细的描述，并在最后做了基于真实环境的测试和结果分析，在相对误差小于10%的范围内成功实现单目测量测距。
