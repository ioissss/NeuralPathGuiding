# NeuralPathGuiding
截止25年，最前沿的Neural Path Guiding技术复现,沿用了论文《Neural Parametric Mixtures for Path Guiding》的代码框架，在其中复现了另外一篇论文《Online Neural Path Guiding with Normalized Anisotropic Spherical Gaussians》。
复现过程中，发现样本效率低下的问题（radiance为0的路径对训练神经网络没有贡献），遂利用《Neural Radiance Caching》的思路，利用一个神经网络预测radiance，再用预测的radiance来训练路径引导网络，以期提供训练效率。

同时，对训练效果进行了可视化：

测试场景，其中红点是测试位置：
<img width="1280" height="720" alt="a4eda5c0835a6ba25e748fe75d09548" src="https://github.com/user-attachments/assets/c489e0e7-7fa6-430e-b9be-980444caf38b" />

随着训练的进行，神经网络在测试点能够找到radiance最大的地方，颜色越重代表采样pdf越大
<img width="3184" height="2390" alt="b7349a760fd84e3463b2401162b07de" src="https://github.com/user-attachments/assets/9a25a97f-5c3b-4cb5-ac7f-0d0172a0e08f" />
