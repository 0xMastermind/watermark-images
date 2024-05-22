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

# 示例用法
为图像添加全透明度的图像水印，放置在右下角，缩放为图像宽度的10%
```python
python watermark_script.py ./images ./logo.png --pos bottomright --scale 10
```
为图像添加半透明度的文字水印，放置在图像中央，字体大小为50
```python
python watermark_script.py ./images --text "Sample Watermark" --fontsize 50 --text_opacity 0.5
```
为图像同时添加图像和文字水印，图像水印放置在左上角，文字水印放置在右下角
```python
python watermark_script.py ./images ./logo.png --text "Sample Watermark" --pos topleft --padding 10 --scale 15 --text_opacity 0.8 --fontsize 40 --font ./path/to/font.ttf
```
#注意事项

确保字体文件路径（`--font`）有效且存在。

如果添加的水印图像路径（`WatermarkLogoPath`）与源目录中的图像名称冲突，脚本会跳过该图像。

如果未指定`--new_dir`，源目录中的原始图像将被覆盖。

该脚本支持JPEG、PNG、TIFF格式的图像。
