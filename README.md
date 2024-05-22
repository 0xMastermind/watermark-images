# watermark-images
使用python脚本为图片添加水印

欢迎PR!

Adding watermarks to images using python scripts

Welcome to pull requests!

🥰

# 基本用法
需要安装库
```bash
pip install tqdm pillow
```
添加图像水印
```python
python watermark.py SourceDirectory WatermarkLogoPath --pos POSITION --new_dir DestinationDirectory --padding PADDING --scale SCALE --opacity OPACITY
```
添加文字水印
```python
python watermark.py SourceDirectory --text "Your Watermark Text" --pos POSITION --new_dir DestinationDirectory --padding PADDING --fontsize FONT_SIZE --text_opacity TEXT_OPACITY --font FontPath
```
同时添加图像和文字水印
```python
python watermark_script.py SourceDirectory WatermarkLogoPath --text "Your Watermark Text" --pos POSITION --new_dir DestinationDirectory --padding PADDING --scale SCALE --opacity OPACITY --fontsize FONT_SIZE --text_opacity TEXT_OPACITY --font FontPath
```
# 参数说明
`SourceDirectory`：

包含要添加水印的图像的目录。脚本会递归遍历此目录中的所有图像。

`WatermarkLogoPath`：

用作水印的图像路径（可选）。

`--text "Your Watermark Text"`：文字水印的内容（可选）。

`--pos POSITION`：水印的位置。可选值为'topleft'、'topright'、'bottomleft'、'bottomright'、'center'。默认值为'center'。

`--new_dir DestinationDirectory`：保存添加水印后的图像的目录。如果未提供，将覆盖源目录中的原始图像。

`--padding PADDING`：水印周围的填充（以像素为单位）。默认值为0。

`--scale SCALE`：水印相对于图像宽度的比例（百分比）。默认值为20。

`--opacity OPACITY`：水印的不透明度（0.0 到 1.0）。默认值为1.0（完全不透明）。

`--font FontPath`：文字水印所使用的字体文件路径。默认值为"arial.ttf"。

`--fontsize FONT_SIZE`：文字水印的字体大小。默认值为36。

`--text_opacity TEXT_OPACITY`：文字水印的不透明度（0.0 到 1.0）。默认值为1.0（完全不透明）。
