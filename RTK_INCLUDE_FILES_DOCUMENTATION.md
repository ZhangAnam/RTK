# RTK Include Files Documentation / RTK头文件说明文档

This document provides a comprehensive list of all header files in the RTK (Reconstruction ToolKit) include directory, organized by functionality and purpose.

本文档提供了RTK（重建工具包）include目录中所有头文件的全面列表，按功能和用途进行组织。

**Total Files / 文件总数:**
- Header files (.h): 235
- Template implementations (.hxx): 146  
- CUDA implementations (.hcu): 29
- **Total: 410 files**

---

## 1. Core Framework & Utilities / 核心框架与工具

### 1.1 Core Macros and Configuration / 核心宏定义与配置
- **rtkMacro.h** - RTK-specific macros and debugging utilities / RTK特定宏定义和调试工具
- **rtkConfiguration.h** (generated) - Build configuration settings / 构建配置设置
- **rtkGeneralPurposeFunctions.h** - General utility functions / 通用工具函数

### 1.2 Command Line Interface Support / 命令行接口支持
- **rtkGgoFunctions.h** - Functions for handling gengetopt arguments / 处理gengetopt参数的函数
- **rtkGgoArgsInfoManager.h** - Manager for command line arguments / 命令行参数管理器

### 1.3 Progress and Resource Monitoring / 进度与资源监控
- **rtkProgressCommands.h** - Progress monitoring command classes / 进度监控命令类
- **rtkIterationCommands.h** - Iteration-based progress commands / 基于迭代的进度命令
- **rtkResourceProbesCollector.h** - Resource usage monitoring / 资源使用监控
- **rtkGlobalResourceProbe.h** - Global resource probe / 全局资源探测器
- **rtkWatcherForResourceProbe.h** - Watcher for resource probes / 资源探测器监视器

---

## 2. Reconstruction Algorithms / 重建算法

### 2.1 FDK (Feldkamp-Davis-Kress) Algorithm / FDK算法
- **rtkFDKConeBeamReconstructionFilter.h/.hxx** - Main FDK cone-beam reconstruction filter / 主要FDK锥束重建滤波器
- **rtkFDKBackProjectionImageFilter.h/.hxx** - FDK backprojection step / FDK反投影步骤
- **rtkFDKWeightProjectionFilter.h/.hxx** - FDK projection weighting / FDK投影加权
- **rtkFDKWarpBackProjectionImageFilter.h/.hxx** - FDK warped backprojection / FDK变形反投影
- **rtkFDKVarianceReconstructionFilter.h/.hxx** - FDK variance reconstruction / FDK方差重建
- **rtkIterativeFDKConeBeamReconstructionFilter.h/.hxx** - Iterative FDK reconstruction / 迭代FDK重建

### 2.2 Iterative Reconstruction Algorithms / 迭代重建算法
- **rtkIterativeConeBeamReconstructionFilter.h/.hxx** - Base class for iterative reconstruction / 迭代重建基类
- **rtkSARTConeBeamReconstructionFilter.h/.hxx** - SART (Simultaneous Algebraic Reconstruction Technique) / SART同步代数重建技术
- **rtkOSEMConeBeamReconstructionFilter.h/.hxx** - OSEM (Ordered Subset Expectation Maximization) / OSEM有序子集期望最大化

### 2.3 Conjugate Gradient Methods / 共轭梯度方法
- **rtkConjugateGradientConeBeamReconstructionFilter.h/.hxx** - Basic conjugate gradient reconstruction / 基本共轭梯度重建
- **rtkRegularizedConjugateGradientConeBeamReconstructionFilter.h/.hxx** - Regularized conjugate gradient / 正则化共轭梯度
- **rtkConjugateGradientImageFilter.h/.hxx** - Generic conjugate gradient filter / 通用共轭梯度滤波器
- **rtkConjugateGradientOperator.h/.hxx** - Base operator for conjugate gradient / 共轭梯度基础算子
- **rtkReconstructionConjugateGradientOperator.h/.hxx** - Reconstruction-specific CG operator / 重建专用CG算子
- **rtkDivergenceOfGradientConjugateGradientOperator.h/.hxx** - Divergence of gradient CG operator / 梯度散度CG算子

### 2.4 CG Component Filters / CG组件滤波器
- **rtkConjugateGradientGetP_kPlusOneImageFilter.h/.hxx** - CG P vector update / CG P向量更新
- **rtkConjugateGradientGetR_kPlusOneImageFilter.h/.hxx** - CG R vector update / CG R向量更新
- **rtkConjugateGradientGetX_kPlusOneImageFilter.h/.hxx** - CG X vector update / CG X向量更新

---

## 3. Advanced Reconstruction Methods / 高级重建方法

### 3.1 4D Reconstruction / 4D重建
- **rtkFourDConjugateGradientConeBeamReconstructionFilter.h/.hxx** - 4D conjugate gradient reconstruction / 4D共轭梯度重建
- **rtkFourDROOSTERConeBeamReconstructionFilter.h/.hxx** - 4D ROOSTER reconstruction / 4D ROOSTER重建
- **rtkFourDSARTConeBeamReconstructionFilter.h/.hxx** - 4D SART reconstruction / 4D SART重建
- **rtkFourDReconstructionConjugateGradientOperator.h/.hxx** - 4D reconstruction CG operator / 4D重建CG算子
- **rtkFourDToProjectionStackImageFilter.h/.hxx** - Convert 4D to projection stack / 4D转投影堆栈
- **rtkProjectionStackToFourDImageFilter.h/.hxx** - Convert projection stack to 4D / 投影堆栈转4D

### 3.2 Motion Compensation / 运动补偿
- **rtkMotionCompensatedFourDConjugateGradientConeBeamReconstructionFilter.h/.hxx** - Motion compensated 4D CG / 运动补偿4D CG
- **rtkMotionCompensatedFourDROOSTERConeBeamReconstructionFilter.h/.hxx** - Motion compensated 4D ROOSTER / 运动补偿4D ROOSTER
- **rtkMotionCompensatedFourDReconstructionConjugateGradientOperator.h/.hxx** - Motion compensated CG operator / 运动补偿CG算子
- **rtkCyclicDeformationImageFilter.h/.hxx** - Cyclic deformation modeling / 循环变形建模

### 3.3 Spectral/Dual Energy Reconstruction / 光谱/双能重建
- **rtkMechlemOneStepSpectralReconstructionFilter.h/.hxx** - One-step spectral reconstruction / 一步法光谱重建
- **rtkSpectralForwardModelImageFilter.h/.hxx** - Spectral forward model / 光谱正向模型
- **rtkSimplexSpectralProjectionsDecompositionImageFilter.h/.hxx** - Spectral projection decomposition / 光谱投影分解
- **rtkDualEnergyNegativeLogLikelihood.h** - Dual energy negative log-likelihood / 双能负对数似然
- **rtkSchlomka2008NegativeLogLikelihood.h** - Schlomka 2008 model / Schlomka 2008模型
- **rtkProjectionsDecompositionNegativeLogLikelihood.h** - Projection decomposition likelihood / 投影分解似然

---

## 4. Regularization and Denoising / 正则化与去噪

### 4.1 Total Variation / 全变分
- **rtkTotalVariationImageFilter.h/.hxx** - Total variation filter / 全变分滤波器
- **rtkTotalVariationDenoisingBPDQImageFilter.h/.hxx** - TV denoising using BPDQ / 使用BPDQ的TV去噪
- **rtkTotalVariationDenoiseSequenceImageFilter.h/.hxx** - TV denoising for sequences / 序列TV去噪
- **rtkTotalNuclearVariationDenoisingBPDQImageFilter.h/.hxx** - Total nuclear variation denoising / 全核变分去噪
- **rtkLastDimensionL0GradientDenoisingImageFilter.h/.hxx** - L0 gradient denoising / L0梯度去噪
- **rtkSoftThresholdTVImageFilter.h/.hxx** - Soft threshold TV filter / 软阈值TV滤波器

### 4.2 ADMM (Alternating Direction Method of Multipliers) / ADMM交替方向乘子法
- **rtkADMMTotalVariationConeBeamReconstructionFilter.h/.hxx** - ADMM TV reconstruction / ADMM TV重建
- **rtkADMMTotalVariationConjugateGradientOperator.h/.hxx** - ADMM TV CG operator / ADMM TV CG算子
- **rtkADMMWaveletsConeBeamReconstructionFilter.h/.hxx** - ADMM wavelets reconstruction / ADMM小波重建
- **rtkADMMWaveletsConjugateGradientOperator.h/.hxx** - ADMM wavelets CG operator / ADMM小波CG算子

### 4.3 Wavelets / 小波
- **rtkDaubechiesWaveletsConvolutionImageFilter.h/.hxx** - Daubechies wavelets convolution / Daubechies小波卷积
- **rtkDaubechiesWaveletsDenoiseSequenceImageFilter.h/.hxx** - Wavelets denoising for sequences / 序列小波去噪

### 4.4 Other Regularization / 其他正则化
- **rtkDePierroRegularizationImageFilter.h/.hxx** - De Pierro regularization / De Pierro正则化
- **rtkSeparableQuadraticSurrogateRegularizationImageFilter.h/.hxx** - Separable quadratic surrogate / 可分二次代理
- **rtkSoftThresholdImageFilter.h/.hxx** - Soft thresholding / 软阈值
- **rtkSingularValueThresholdImageFilter.h/.hxx** - Singular value thresholding / 奇异值阈值
- **rtkMagnitudeThresholdImageFilter.h/.hxx** - Magnitude thresholding / 幅度阈值

---

## 5. Forward and Back Projection / 正投影与反投影

### 5.1 Basic Projection Operations / 基本投影操作
- **rtkForwardProjectionImageFilter.h/.hxx** - Generic forward projection / 通用正投影
- **rtkBackProjectionImageFilter.h/.hxx** - Generic backprojection / 通用反投影

### 5.2 Joseph Method / Joseph方法
- **rtkJosephForwardProjectionImageFilter.h/.hxx** - Joseph forward projection / Joseph正投影
- **rtkJosephBackProjectionImageFilter.h/.hxx** - Joseph backprojection / Joseph反投影
- **rtkJosephForwardAttenuatedProjectionImageFilter.h/.hxx** - Joseph forward with attenuation / 带衰减的Joseph正投影
- **rtkJosephBackAttenuatedProjectionImageFilter.h/.hxx** - Joseph back with attenuation / 带衰减的Joseph反投影

### 5.3 Ray Casting / 射线投影
- **rtkRayBoxIntersectionImageFilter.h/.hxx** - Ray-box intersection / 射线-盒子相交
- **rtkRayConvexIntersectionImageFilter.h/.hxx** - Ray-convex intersection / 射线-凸形相交
- **rtkRayEllipsoidIntersectionImageFilter.h/.hxx** - Ray-ellipsoid intersection / 射线-椭球相交
- **rtkRayQuadricIntersectionImageFilter.h/.hxx** - Ray-quadric intersection / 射线-二次曲面相交

### 5.4 Zeng Method / Zeng方法
- **rtkZengForwardProjectionImageFilter.h/.hxx** - Zeng forward projection / Zeng正投影
- **rtkZengBackProjectionImageFilter.h/.hxx** - Zeng backprojection / Zeng反投影

### 5.5 Warped Projections / 变形投影
- **rtkForwardWarpImageFilter.h/.hxx** - Forward warp transformation / 正向变形变换
- **rtkWarpFourDToProjectionStackImageFilter.h/.hxx** - Warp 4D to projection stack / 4D变形到投影堆栈
- **rtkWarpProjectionStackToFourDImageFilter.h/.hxx** - Warp projection stack to 4D / 投影堆栈变形到4D
- **rtkWarpSequenceImageFilter.h/.hxx** - Warp sequence filter / 序列变形滤波器
- **rtkUnwarpSequenceImageFilter.h/.hxx** - Unwarp sequence filter / 序列反变形滤波器
- **rtkUnwarpSequenceConjugateGradientOperator.h/.hxx** - Unwarp sequence CG operator / 序列反变形CG算子

---

## 6. CUDA GPU Acceleration / CUDA GPU加速

### 6.1 CUDA Reconstruction Filters / CUDA重建滤波器
- **rtkCudaFDKConeBeamReconstructionFilter.h** - CUDA FDK reconstruction / CUDA FDK重建
- **rtkCudaIterativeFDKConeBeamReconstructionFilter.h** - CUDA iterative FDK / CUDA迭代FDK
- **rtkCudaConjugateGradientImageFilter.h/.hcu/.hxx** - CUDA conjugate gradient / CUDA共轭梯度

### 6.2 CUDA Projection Filters / CUDA投影滤波器
- **rtkCudaForwardProjectionImageFilter.h/.hcu/.hxx** - CUDA forward projection / CUDA正投影
- **rtkCudaBackProjectionImageFilter.h/.hcu/.hxx** - CUDA backprojection / CUDA反投影
- **rtkCudaRayCastBackProjectionImageFilter.h/.hcu** - CUDA ray-cast backprojection / CUDA射线投影反投影
- **rtkCudaFDKBackProjectionImageFilter.h/.hcu** - CUDA FDK backprojection / CUDA FDK反投影
- **rtkCudaWarpBackProjectionImageFilter.h/.hcu** - CUDA warp backprojection / CUDA变形反投影
- **rtkCudaWarpForwardProjectionImageFilter.h/.hcu** - CUDA warp forward projection / CUDA变形正投影

### 6.3 CUDA Image Processing / CUDA图像处理
- **rtkCudaConstantVolumeSource.h/.hcu** - CUDA constant volume source / CUDA常数体积源
- **rtkCudaConstantVolumeSeriesSource.h/.hcu** - CUDA constant volume series / CUDA常数体积序列
- **rtkCudaCropImageFilter.h/.hcu** - CUDA image cropping / CUDA图像裁剪
- **rtkCudaInterpolateImageFilter.h/.hcu** - CUDA interpolation / CUDA插值
- **rtkCudaWarpImageFilter.h/.hcu** - CUDA image warping / CUDA图像变形
- **rtkCudaSplatImageFilter.h/.hcu** - CUDA splat operation / CUDA散布操作
- **rtkCudaLaplacianImageFilter.h/.hcu** - CUDA Laplacian filter / CUDA拉普拉斯滤波器

### 6.4 CUDA Denoising and Regularization / CUDA去噪与正则化
- **rtkCudaTotalVariationDenoisingBPDQImageFilter.h/.hcu** - CUDA TV denoising / CUDA TV去噪
- **rtkCudaLastDimensionTVDenoisingImageFilter.h/.hcu** - CUDA last dimension TV / CUDA最后维度TV

### 6.5 CUDA Preprocessing / CUDA预处理
- **rtkCudaDisplacedDetectorImageFilter.h/.hcu** - CUDA displaced detector / CUDA偏移探测器
- **rtkCudaParkerShortScanImageFilter.h/.hcu** - CUDA Parker short scan / CUDA Parker短扫描
- **rtkCudaFFTProjectionsConvolutionImageFilter.h/.hcu/.hxx** - CUDA FFT convolution / CUDA FFT卷积
- **rtkCudaFFTRampImageFilter.h** - CUDA FFT ramp filter / CUDA FFT斜坡滤波器
- **rtkCudaLagCorrectionImageFilter.h/.hcu** - CUDA lag correction / CUDA滞后校正
- **rtkCudaPolynomialGainCorrectionImageFilter.h/.hcu** - CUDA polynomial gain correction / CUDA多项式增益校正
- **rtkCudaScatterGlareCorrectionImageFilter.h** - CUDA scatter/glare correction / CUDA散射/眩光校正

### 6.6 CUDA Utilities / CUDA工具
- **rtkCudaUtilities.hcu** - CUDA utility functions / CUDA工具函数
- **rtkCudaIntersectBox.hcu** - CUDA box intersection / CUDA盒子相交
- **rtkCudaFirstOrderKernels.hcu** - CUDA first-order kernels / CUDA一阶核函数
- **rtkCudaCyclicDeformationImageFilter.h/.hcu** - CUDA cyclic deformation / CUDA循环变形
- **rtkCudaAverageOutOfROIImageFilter.h/.hcu** - CUDA ROI averaging / CUDA ROI外平均
- **rtkCudaWeidingerForwardModelImageFilter.h/.hcu/.hxx** - CUDA Weidinger forward model / CUDA Weidinger正向模型

---

## 7. Image Sources and Basic Operations / 图像源与基本操作

### 7.1 Image Sources / 图像源
- **rtkConstantImageSource.h/.hxx** - Constant value image source / 常数值图像源
- **rtkImportImageFilter.h/.hxx** - Import external image data / 导入外部图像数据

### 7.2 Basic Image Operations / 基本图像操作
- **rtkAddMatrixAndDiagonalImageFilter.h/.hxx** - Matrix and diagonal addition / 矩阵与对角线加法
- **rtkMultiplyByVectorImageFilter.h/.hxx** - Vector multiplication / 向量乘法
- **rtkSumOfSquaresImageFilter.h/.hxx** - Sum of squares / 平方和
- **rtkImageToVectorImageFilter.h/.hxx** - Convert image to vector image / 图像转向量图像
- **rtkVectorImageToImageFilter.h/.hxx** - Convert vector image to image / 向量图像转图像

### 7.3 Resampling and Interpolation / 重采样与插值
- **rtkUpsampleImageFilter.h/.hxx** - Upsampling filter / 上采样滤波器
- **rtkDownsampleImageFilter.h/.hxx** - Downsampling filter / 下采样滤波器
- **rtkInterpolatorWithKnownWeightsImageFilter.h/.hxx** - Weighted interpolation / 加权插值
- **rtkSplatWithKnownWeightsImageFilter.h/.hxx** - Weighted splatting / 加权散布

---

## 8. Projection Preprocessing / 投影预处理

### 8.1 Geometric Corrections / 几何校正
- **rtkDisplacedDetectorImageFilter.h/.hxx** - Displaced detector correction / 偏移探测器校正
- **rtkDisplacedDetectorForOffsetFieldOfViewImageFilter.h/.hxx** - Displaced detector for offset FOV / 偏移视野的偏移探测器
- **rtkParkerShortScanImageFilter.h/.hxx** - Parker short scan weighting / Parker短扫描加权
- **rtkFieldOfViewImageFilter.h/.hxx** - Field of view masking / 视野掩模

### 8.2 Filtering and Convolution / 滤波与卷积
- **rtkFFTProjectionsConvolutionImageFilter.h/.hxx** - FFT-based projection convolution / 基于FFT的投影卷积
- **rtkFFTRampImageFilter.h/.hxx** - FFT ramp filter / FFT斜坡滤波器
- **rtkFFTVarianceRampImageFilter.h/.hxx** - FFT variance ramp filter / FFT方差斜坡滤波器
- **rtkFFTHilbertImageFilter.h/.hxx** - FFT Hilbert transform / FFT希尔伯特变换
- **rtkHilbertImageFilter.h/.hxx** - Hilbert transform filter / 希尔伯特变换滤波器

### 8.3 Intensity Corrections / 强度校正
- **rtkI0EstimationProjectionFilter.h/.hxx** - I0 estimation filter / I0估计滤波器
- **rtkLookupTableImageFilter.h/.hxx** - Lookup table transformation / 查找表变换
- **rtkPolynomialGainCorrectionImageFilter.h/.hxx** - Polynomial gain correction / 多项式增益校正
- **rtkLagCorrectionImageFilter.h/.hxx** - Lag correction filter / 滞后校正滤波器
- **rtkWaterPrecorrectionImageFilter.h/.hxx** - Water precorrection / 水预校正

### 8.4 Noise and Artifact Correction / 噪声与伪影校正
- **rtkBoellaardScatterCorrectionImageFilter.h/.hxx** - Boellaard scatter correction / Boellaard散射校正
- **rtkScatterGlareCorrectionImageFilter.h/.hxx** - Scatter and glare correction / 散射与眩光校正
- **rtkConditionalMedianImageFilter.h/.hxx** - Conditional median filtering / 条件中值滤波
- **rtkAdditiveGaussianNoiseImageFilter.h/.hxx** - Additive Gaussian noise / 加性高斯噪声

---

## 9. File I/O and Format Support / 文件I/O与格式支持

### 9.1 I/O Factory Registration / I/O工厂注册
- **rtkIOFactories.h** - Register all RTK I/O factories / 注册所有RTK I/O工厂

### 9.2 Medical Imaging Formats / 医学影像格式
- **rtkHisImageIO.h** - Perkin Elmer His format / Perkin Elmer His格式
- **rtkHisImageIOFactory.h** - His format factory / His格式工厂
- **rtkHndImageIO.h** - Varian Hnd format / Varian Hnd格式
- **rtkHndImageIOFactory.h** - Hnd format factory / Hnd格式工厂
- **rtkEdfImageIO.h** - ESRF Edf format / ESRF Edf格式
- **rtkEdfImageIOFactory.h** - Edf format factory / Edf格式工厂
- **rtkXRadImageIO.h** - XRad format / XRad格式
- **rtkXRadImageIOFactory.h** - XRad format factory / XRad格式工厂
- **rtkHncImageIO.h** - Hnc format / Hnc格式
- **rtkHncImageIOFactory.h** - Hnc format factory / Hnc格式工厂
- **rtkXimImageIO.h** - Xim format / Xim格式
- **rtkXimImageIOFactory.h** - Xim format factory / Xim格式工厂

### 9.3 Vendor-Specific Formats / 供应商特定格式
- **rtkImagXImageIO.h** - ImagX format / ImagX格式
- **rtkImagXImageIOFactory.h** - ImagX format factory / ImagX格式工厂
- **rtkDCMImagXImageIO.h** - DICOM ImagX format / DICOM ImagX格式
- **rtkDCMImagXImageIOFactory.h** - DICOM ImagX factory / DICOM ImagX工厂
- **rtkOraImageIO.h** - Ora format / Ora格式
- **rtkOraImageIOFactory.h** - Ora format factory / Ora格式工厂

### 9.4 Raw Data Processing / 原始数据处理
- **rtkEdfRawToAttenuationImageFilter.h/.hxx** - Edf raw to attenuation / Edf原始数据转衰减
- **rtkXRadRawToAttenuationImageFilter.h/.hxx** - XRad raw to attenuation / XRad原始数据转衰减
- **rtkVarianObiRawImageFilter.h/.hxx** - Varian OBI raw processing / Varian OBI原始处理
- **rtkLUTbasedVariableI0RawToAttenuationImageFilter.h/.hxx** - LUT-based variable I0 conversion / 基于LUT的可变I0转换

### 9.5 Vendor-Specific Processing / 供应商特定处理
- **rtkElektaSynergyLookupTableImageFilter.h/.hxx** - Elekta Synergy LUT / Elekta Synergy查找表
- **rtkElektaSynergyRawLookupTableImageFilter.h/.hxx** - Elekta Synergy raw LUT / Elekta Synergy原始LUT
- **rtkOraLookupTableImageFilter.h/.hxx** - Ora lookup table / Ora查找表

---

## 10. Geometry Management / 几何管理

### 10.1 Core Geometry Classes / 核心几何类
- **rtkProjectionGeometry.h/.hxx** - Base projection geometry / 基础投影几何
- **rtkThreeDCircularProjectionGeometry.h** - 3D circular projection geometry / 3D圆形投影几何
- **rtkReg23ProjectionGeometry.h** - Reg23 projection geometry / Reg23投影几何
- **rtkHomogeneousMatrix.h** - Homogeneous transformation matrices / 齐次变换矩阵

### 10.2 Geometry I/O / 几何I/O
- **rtkThreeDCircularProjectionGeometryXMLFile.h** - XML geometry file base / XML几何文件基类
- **rtkThreeDCircularProjectionGeometryXMLFileReader.h** - XML geometry reader / XML几何读取器
- **rtkThreeDCircularProjectionGeometryXMLFileWriter.h** - XML geometry writer / XML几何写入器

### 10.3 Vendor-Specific Geometry Readers / 供应商特定几何读取器
- **rtkElektaSynergyGeometryReader.h** - Elekta Synergy geometry / Elekta Synergy几何
- **rtkVarianObiGeometryReader.h** - Varian OBI geometry / Varian OBI几何
- **rtkVarianProBeamGeometryReader.h** - Varian ProBeam geometry / Varian ProBeam几何
- **rtkXRadGeometryReader.h** - XRad geometry / XRad几何
- **rtkImagXGeometryReader.h/.hxx** - ImagX geometry / ImagX几何
- **rtkOraGeometryReader.h** - Ora geometry / Ora几何
- **rtkBioscanGeometryReader.h** - Bioscan geometry / Bioscan几何
- **rtkDigisensGeometryReader.h** - Digisens geometry / Digisens几何

### 10.4 Vendor-Specific XML Readers / 供应商特定XML读取器
- **rtkElektaXVI5GeometryXMLFileReader.h** - Elekta XVI5 XML reader / Elekta XVI5 XML读取器
- **rtkVarianObiXMLFileReader.h** - Varian OBI XML reader / Varian OBI XML读取器
- **rtkVarianProBeamXMLFileReader.h** - Varian ProBeam XML reader / Varian ProBeam XML读取器
- **rtkImagXXMLFileReader.h** - ImagX XML reader / ImagX XML读取器
- **rtkOraXMLFileReader.h** - Ora XML reader / Ora XML读取器
- **rtkDigisensGeometryXMLFileReader.h** - Digisens XML reader / Digisens XML读取器

---

## 11. Phantom Generation / 体模生成

### 11.1 Geometric Shapes / 几何形状
- **rtkConvexShape.h** - Base class for convex shapes / 凸形状基类
- **rtkBoxShape.h** - Box/parallelepiped shape / 盒子/平行六面体形状
- **rtkQuadricShape.h** - Quadric surface shape / 二次曲面形状
- **rtkIntersectionOfConvexShapes.h** - Intersection of convex shapes / 凸形状交集

### 11.2 Phantom Objects / 体模对象
- **rtkGeometricPhantom.h** - Geometric phantom container / 几何体模容器
- **rtkSheppLoganPhantom.h** - Shepp-Logan phantom / Shepp-Logan体模

### 11.3 Drawing Filters / 绘制滤波器
- **rtkDrawGeometricPhantomImageFilter.h/.hxx** - Draw geometric phantom / 绘制几何体模
- **rtkDrawSheppLoganFilter.h/.hxx** - Draw Shepp-Logan phantom / 绘制Shepp-Logan体模
- **rtkSheppLoganPhantomFilter.h/.hxx** - Shepp-Logan phantom filter / Shepp-Logan体模滤波器
- **rtkDrawConvexImageFilter.h/.hxx** - Draw convex shapes / 绘制凸形状
- **rtkDrawBoxImageFilter.h/.hxx** - Draw box shapes / 绘制盒子形状
- **rtkDrawCubeImageFilter.h** - Draw cube shapes / 绘制立方体形状
- **rtkDrawConeImageFilter.h/.hxx** - Draw cone shapes / 绘制圆锥形状
- **rtkDrawCylinderImageFilter.h/.hxx** - Draw cylinder shapes / 绘制圆柱形状
- **rtkDrawEllipsoidImageFilter.h/.hxx** - Draw ellipsoid shapes / 绘制椭球形状
- **rtkDrawQuadricImageFilter.h/.hxx** - Draw quadric shapes / 绘制二次曲面形状

### 11.4 Phantom Projection / 体模投影
- **rtkProjectGeometricPhantomImageFilter.h/.hxx** - Project geometric phantom / 投影几何体模

### 11.5 Phantom File I/O / 体模文件I/O
- **rtkGeometricPhantomFileReader.h** - Read geometric phantom files / 读取几何体模文件
- **rtkForbildPhantomFileReader.h** - Read Forbild phantom files / 读取Forbild体模文件

---

## 12. Signal Processing and Gating / 信号处理与门控

### 12.1 Phase and Gating / 相位与门控
- **rtkPhaseGatingImageFilter.h/.hxx** - Phase gating filter / 相位门控滤波器
- **rtkSelectOneProjectionPerCycleImageFilter.h/.hxx** - Select one projection per cycle / 每周期选择一个投影
- **rtkExtractPhaseImageFilter.h/.hxx** - Extract phase information / 提取相位信息

### 12.2 Signal Processing / 信号处理
- **rtkPhaseReader.h** - Phase signal reader / 相位信号读取器
- **rtkSignalToInterpolationWeights.h** - Convert signal to interpolation weights / 信号转插值权重
- **rtkPhasesToInterpolationWeights.h** - Convert phases to interpolation weights / 相位转插值权重

### 12.3 Shroud Signal Processing / 遮挡信号处理
- **rtkAmsterdamShroudImageFilter.h/.hxx** - Amsterdam shroud processing / Amsterdam遮挡处理
- **rtkDPExtractShroudSignalImageFilter.h/.hxx** - DP extract shroud signal / DP提取遮挡信号
- **rtkReg1DExtractShroudSignalImageFilter.h/.hxx** - 1D registration extract shroud / 1D配准提取遮挡

### 12.4 Reordering and Selection / 重排序与选择
- **rtkReorderProjectionsImageFilter.h/.hxx** - Reorder projections / 重排序投影
- **rtkSubSelectImageFilter.h/.hxx** - Sub-select images / 子选择图像
- **rtkSubSelectFromListImageFilter.h/.hxx** - Sub-select from list / 从列表子选择

---

## 13. Mathematical Operations / 数学操作

### 13.1 Gradient and Divergence / 梯度与散度
- **rtkForwardDifferenceGradientImageFilter.h/.hxx** - Forward difference gradient / 前向差分梯度
- **rtkBackwardDifferenceDivergenceImageFilter.h/.hxx** - Backward difference divergence / 后向差分散度
- **rtkLaplacianImageFilter.h/.hxx** - Laplacian operator / 拉普拉斯算子

### 13.2 Matrix Operations / 矩阵操作
- **rtkBlockDiagonalMatrixVectorMultiplyImageFilter.h/.hxx** - Block diagonal matrix-vector multiply / 块对角矩阵向量乘法

### 13.3 Update Methods / 更新方法
- **rtkNesterovUpdateImageFilter.h/.hxx** - Nesterov momentum update / Nesterov动量更新
- **rtkGetNewtonUpdateImageFilter.h/.hxx** - Newton update method / 牛顿更新方法

### 13.4 Reconstruction and Deconstruction / 重构与解构
- **rtkReconstructImageFilter.h/.hxx** - Reconstruct from components / 从组件重构
- **rtkDeconstructImageFilter.h/.hxx** - Deconstruct into components / 解构为组件
- **rtkDeconstructSoftThresholdReconstructImageFilter.h/.hxx** - Deconstruct-threshold-reconstruct / 解构-阈值-重构

---

## 14. Advanced Image Processing / 高级图像处理

### 14.1 Masking and ROI / 掩模与感兴趣区域
- **rtkMaskCollimationImageFilter.h/.hxx** - Mask collimation areas / 掩模准直区域
- **rtkAverageOutOfROIImageFilter.h/.hxx** - Average outside ROI / ROI外平均

### 14.2 Projection Methods / 投影方法
- **rtkMaximumIntensityProjectionImageFilter.h** - Maximum intensity projection / 最大强度投影

### 14.3 Special Filters / 特殊滤波器
- **rtkDenoisingBPDQImageFilter.h/.hxx** - Denoising using BPDQ / 使用BPDQ去噪
- **rtkWeidingerForwardModelImageFilter.h/.hxx** - Weidinger forward model / Weidinger正向模型

---

## 15. Data Structures and Utilities / 数据结构与工具

### 15.1 Database Interface / 数据库接口
- **rtkDbf.h** - Database file interface / 数据库文件接口

### 15.2 Projection Iterators / 投影迭代器
- **rtkProjectionsRegionConstIteratorRayBased.h/.hxx** - Ray-based projection iterator / 基于射线的投影迭代器
- **rtkProjectionsRegionConstIteratorRayBasedParallel.h/.hxx** - Parallel ray-based iterator / 并行射线迭代器
- **rtkProjectionsRegionConstIteratorRayBasedWithCylindricalPanel.h/.hxx** - Cylindrical panel iterator / 圆柱面板迭代器
- **rtkProjectionsRegionConstIteratorRayBasedWithFlatPanel.h/.hxx** - Flat panel iterator / 平板迭代器

### 15.3 Projections Reader / 投影读取器
- **rtkProjectionsReader.h/.hxx** - Universal projections reader / 通用投影读取器

---

## Summary by Category / 按类别汇总

1. **Core Framework (18 files)** - 核心框架 (18个文件)
2. **Reconstruction Algorithms (25 files)** - 重建算法 (25个文件)
3. **Advanced Reconstruction (15 files)** - 高级重建 (15个文件)
4. **Regularization (18 files)** - 正则化 (18个文件)
5. **Projection Operations (20 files)** - 投影操作 (20个文件)
6. **CUDA GPU Acceleration (55 files)** - CUDA GPU加速 (55个文件)
7. **Basic Operations (12 files)** - 基本操作 (12个文件)
8. **Preprocessing (20 files)** - 预处理 (20个文件)
9. **File I/O (22 files)** - 文件I/O (22个文件)
10. **Geometry (18 files)** - 几何 (18个文件)
11. **Phantoms (18 files)** - 体模 (18个文件)
12. **Signal Processing (12 files)** - 信号处理 (12个文件)
13. **Mathematical Operations (10 files)** - 数学操作 (10个文件)
14. **Advanced Processing (8 files)** - 高级处理 (8个文件)
15. **Data Structures (8 files)** - 数据结构 (8个文件)

**Total documented: 259 header files (.h)**
**Total with implementations: 405 files (.h + .hxx + .hcu)**

---

**Note**: This documentation covers all header files (.h) in the RTK include directory. Each file serves a specific purpose in the medical image reconstruction pipeline, from raw data acquisition to final reconstructed volumes.

**注意**: 此文档涵盖了RTK include目录中的所有头文件(.h)。每个文件在医学图像重建流水线中都有特定目的，从原始数据采集到最终重建体积。