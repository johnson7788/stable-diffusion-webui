# Stable Diffusion web UI
基于Gradio库的用于 Stable Diffusion的浏览器接口.

![](screenshot.png)

## Features
[Detailed feature showcase with images](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features):
- 原始的txt2img和img2img模式
- 一键安装和运行脚本（但你仍然必须安装python和git）。
- 画外画
- 画中画
- 颜色素描
- 提示矩阵
- Stable Diffusion上调比例  
- 注意，指定模型应该更加注意的文本部分
    - a man in a ((tuxedo))--将更多地关注燕尾服tuxedo
    - a man in a (tuxedo:1.21) - 替代句法
    - 选择文本并按ctrl+up或ctrl+down来自动调整对所选文本的关注（代码由匿名用户贡献）
- Loopback，多次运行img2img处理程序
- X/Y/Z图，一种绘制不同参数的图像的3维图的方法
- 文本倒置
    - 有多少个嵌入就有多少个，可以用任何你喜欢的名字来命名它们
    - 使用多个嵌入，每个token有不同数量的向量
    - 可使用半精度浮点数字
    - 在8GB上训练嵌入（也有6GB的报告）。  
- 额外的tab与。
    - GFPGAN，修复面部的神经网络
    - CodeFormer, 面部修复工具，作为GFPGAN的替代品
    - RealESRGAN, 神经网络增强器
    - ESRGAN，具有大量第三方模型的神经网络增强器
    - SwinIR和Swin2SR([见这里](https://github.com/AUTOMATIC1111/stable-diffusion-webui/pull/2092))，神经网络提升器
    - LDSR, 潜在扩散超级分辨率升频器
- 调整长宽比选项
- 采样方法选择
    - 调整采样器Eta值（噪声乘数）
    - 更高级的噪声设置选项
- 在任何时候中断处理
- 支持4GB显卡（也有报告称2GB可以使用）
- 批次的正确种子
- 实时提示token长度验证  
- 生成参数
     - 你用来生成图像的参数将与该图像一起保存
     - 对于PNG，保存在PNG块中，对于JPEG，保存在EXIF中
     - 可以将图像拖到PNG信息标签，以恢复生成参数并自动复制到UI中
     - 可以在设置中禁用
     - 拖放图像/文本参数到提示框中
- 读取生成参数按钮，将提示框中的参数加载至用户界面
- 设置页面
- 从用户界面运行任意的Python代码（必须用--allow-code运行才能启用）
- 大多数用户界面元素的鼠标悬停提示
- 可以通过文本配置来改变UI元素的默认值/混合值/最大值/步长值
- 支持tiling，一个复选框用来创建可以像纹理一样tiling的图像
- 进度条和实时图像生成预览
    - 可以使用一个单独的神经网络来生成预览，几乎不需要VRAM或计算要求
- 负面提示，一个额外的文本字段，允许你列出你不希望在生成的图像中看到的内容。
- 样式，一种保存部分提示的方法，以后可以通过下拉菜单轻松应用它们
- 变化，一种生成相同图像但有微小差异的方法
- 种子大小调整，一种生成相同图像但分辨率略有不同的方法
- CLIP审讯器，一个试图从图像中猜测提示的按钮
- 提示编辑，一种在生成过程中改变提示的方法，比如说开始制作一个西瓜，中途切换到动漫女孩。
- 批次处理，用Img2img处理一组文件
- Img2img替代品，反向欧拉法的交叉注意力控制
- Highres Fix，一个方便的选项，一键生成高分辨率的图片，没有通常的失真。
- 即时重新加载checkpoint
- checkpoint合并，一个允许你将最多3个checkpoint合并成一个的选项。

- [Custom scripts](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Custom-Scripts) with many extensions from community
- [Composable-Diffusion](https://energy-based-model.github.io/Compositional-Visual-Generation-with-Composable-Diffusion-Models/), a way to use multiple prompts at once
     - separate prompts using uppercase `AND`
     - also supports weights for prompts: `a cat :1.2 AND a dog AND a penguin :2.2`
- 提示语没有token限制（原来的稳定扩散让你最多使用75个token）
- DeepDanbooru integration, creates danbooru style tags for anime prompts
- [xformers](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Xformers), major speed increase for select cards: (add --xformers to commandline args)
- via extension: [History tab](https://github.com/yfszzx/stable-diffusion-webui-images-browser): view, direct and delete images conveniently within the UI
- 生成永远的选项
- 训练选项卡
     - 超网络和嵌入选项
     - 预处理图像：裁剪、镜像、使用BLIP或deepdanbooru（用于动漫）进行自动标注
- 片段跳过
- 超网络
- Loras（与Hypernetworks相同，但更漂亮）
- 一个拼写的用户界面，你可以通过预览选择哪些嵌入、超网络或Loras来添加到你的提示。
- 可以在设置屏幕上选择加载不同的VAE
- 在进度条中估计完成时间
- API
- Support for dedicated [inpainting model](https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion) by RunwayML.
- via extension: [Aesthetic Gradients](https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients), a way to generate images with a specific aesthetic by using clip images embeds (implementation of [https://github.com/vicgalle/stable-diffusion-aesthetic-gradients](https://github.com/vicgalle/stable-diffusion-aesthetic-gradients))
- [Stable Diffusion 2.0](https://github.com/Stability-AI/stablediffusion) support - see [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#stable-diffusion-20) for instructions
- [Alt-Diffusion](https://arxiv.org/abs/2211.06679) support - see [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#alt-diffusion) for instructions
- 现在没有任何坏的字母了!
- 以safetensors格式加载checkpoint
- 放宽了分辨率的限制：生成的图像的尺寸必须是8的倍数，而不是64。
- 现在有了许可证!
- 在设置屏幕上重新排列用户界面的元素
- 

## Installation and Running
Make sure the required [dependencies](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Dependencies) are met and follow the instructions available for both [NVidia](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs) (recommended) and [AMD](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-AMD-GPUs) GPUs.

Alternatively, use online services (like Google Colab):

- [List of Online Services](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Online-Services)

### Automatic Installation on Windows
1. Install [Python 3.10.6](https://www.python.org/downloads/windows/), checking "Add Python to PATH"
2. Install [git](https://git-scm.com/download/win).
3. Download the stable-diffusion-webui repository, for example by running `git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git`.
4. Run `webui-user.bat` from Windows Explorer as normal, non-administrator, user.

### Automatic Installation on Linux
1. Install the dependencies:
```bash
# Debian-based:
sudo apt install wget git python3 python3-venv
# Red Hat-based:
sudo dnf install wget git python3
# Arch-based:
sudo pacman -S wget git python3
```
2. To install in `/home/$(whoami)/stable-diffusion-webui/`, run:
```bash
bash <(wget -qO- https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh)
```
3. Run `webui.sh`.
### Installation on Apple Silicon

Find the instructions [here](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon).

## Contributing
Here's how to add code to this repo: [Contributing](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Contributing)

## Documentation
The documentation was moved from this README over to the project's [wiki](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki).

## Credits
Licenses for borrowed code can be found in `Settings -> Licenses` screen, and also in `html/licenses.html` file.

- Stable Diffusion - https://github.com/CompVis/stable-diffusion, https://github.com/CompVis/taming-transformers
- k-diffusion - https://github.com/crowsonkb/k-diffusion.git
- GFPGAN - https://github.com/TencentARC/GFPGAN.git
- CodeFormer - https://github.com/sczhou/CodeFormer
- ESRGAN - https://github.com/xinntao/ESRGAN
- SwinIR - https://github.com/JingyunLiang/SwinIR
- Swin2SR - https://github.com/mv-lab/swin2sr
- LDSR - https://github.com/Hafiidz/latent-diffusion
- MiDaS - https://github.com/isl-org/MiDaS
- Ideas for optimizations - https://github.com/basujindal/stable-diffusion
- Cross Attention layer optimization - Doggettx - https://github.com/Doggettx/stable-diffusion, original idea for prompt editing.
- Cross Attention layer optimization - InvokeAI, lstein - https://github.com/invoke-ai/InvokeAI (originally http://github.com/lstein/stable-diffusion)
- Sub-quadratic Cross Attention layer optimization - Alex Birch (https://github.com/Birch-san/diffusers/pull/1), Amin Rezaei (https://github.com/AminRezaei0x443/memory-efficient-attention)
- Textual Inversion - Rinon Gal - https://github.com/rinongal/textual_inversion (we're not using his code, but we are using his ideas).
- Idea for SD upscale - https://github.com/jquesnelle/txt2imghd
- Noise generation for outpainting mk2 - https://github.com/parlance-zz/g-diffuser-bot
- CLIP interrogator idea and borrowing some code - https://github.com/pharmapsychotic/clip-interrogator
- Idea for Composable Diffusion - https://github.com/energy-based-model/Compositional-Visual-Generation-with-Composable-Diffusion-Models-PyTorch
- xformers - https://github.com/facebookresearch/xformers
- DeepDanbooru - interrogator for anime diffusers https://github.com/KichangKim/DeepDanbooru
- Sampling in float32 precision from a float16 UNet - marunine for the idea, Birch-san for the example Diffusers implementation (https://github.com/Birch-san/diffusers-play/tree/92feee6)
- Instruct pix2pix - Tim Brooks (star), Aleksander Holynski (star), Alexei A. Efros (no star) - https://github.com/timothybrooks/instruct-pix2pix
- Security advice - RyotaK
- Initial Gradio script - posted on 4chan by an Anonymous user. Thank you Anonymous user.
- (You)
