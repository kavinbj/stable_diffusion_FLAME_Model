# my_stable_diffusion


### Diffusion 解读

Stable Diffusion基于Latent Diffusion Models，专门用于文图生成任务。

目前，Stable Diffusion发布了v1版本，即Stable Diffusion v2.1，它是Latent Diffusion Models的一个具体实现，具体来说，它特指这样的一个模型架构设置：自动编码器下采样因子为8，UNet大小为860M，文本编码器为CLIP ViT-L/14。


- Diffusion model相比GAN可以取得更好的图片生成效果，然而该模型是一种自回归模型，需要反复迭代计算，因此训练和推理代价都很高。论文提出一种在潜在表示空间（latent space）上进行diffusion过程的方法，从而能够大大减少计算复杂度，同时也能达到十分不错的图片生成效果。

- 相比于其它空间压缩方法（如），论文提出的方法可以生成更细致的图像，并且在高分辨率图片生成任务（如风景图生成，百万像素图像）上表现得也很好。
论文将该模型在无条件图片生成（unconditional image synthesis）, 图片修复（inpainting）,图片超分（super-resolution）任务上进行了实验，都取得了不错的效果。

- 论文还提出了cross-attention的方法来实现多模态训练，使得条件图片生成任务也可以实现。论文中提到的条件图片生成任务包括类别条件图片生成（class-condition）, 文图生成（text-to-image）, 布局条件图片生成（layout-to-image）。这也为日后Stable Diffusion的开发奠定了基础。



![structure](https://pic2.zhimg.com/80/v2-691cbd5fe5c322a3b39b3ac2c3af2de5_1440w.webp)


### Deploying Transformers on the Apple Neural Engine
https://machinelearning.apple.com/research/neural-engine-transformers

### Core ML Stable Diffusion
Run Stable Diffusion on Apple Silicon with Core ML
https://github.com/apple/ml-stable-diffusion