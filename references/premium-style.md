# 高级感六法则 + i2i 生图模板

参考真实“专辑花束”项目提炼的成品高级感共性。六法则缺一不可，否则成品会“普通、像零售花束”。

## 六法则详解

### 1. 构图 + 放大
默认构图（用户已确认的首选）：
- **背景纯黑、无纹理、无反光**（不要丝绒/布纹，平涂哑光黑）。
- **花束正放（不斜）、居中、整体放大**，占画面大部分，只留窄边留白。
- 封面缩略图放**左上或右上角**（用户需求，默认左上），缩略图文字与图案保持清晰可辨。
- 缎带可向下垂落点缀。
- 也可按用户临时指令切换为“非对称斜放 + 大面积留白”的杂志风构图。

### 2. 纯黑背景
- 纯黑、哑光、无反光、无纹理、无渐变、无暗角，平涂干净黑。
- 背景只做基底，把花朵颜色“托”出来。

### 3. 硬侧光做明暗层次
- 方向性侧上方硬光，在花瓣/纸面打出明确明暗面。
- 阴影干净（压在深底里），亮部精准落在花头、包装纸、封面。
- 不做均匀平铺的“柔亮平光”。

### 4. 重结构轻饱满
- 三角立体结构：最高枝在顶，中段过渡，底部收束。
- 高低、疏密、质感差明确（亮面珠光 / 绒面哑光 / 蓬松雾感 / 硬挺平面叠加）。
- **拒绝圆滚滚花球**。

### 5. 尖角几何感包装
- 硬挺卡纸折利落尖角、不对称、挺括平整。
- 避免软塌、多层、褶皱多的“网红花束”感。

### 6. 色调克制
- 2–3 色主导 + 点睛色，零杂色、零无关渐变。
- 封面颜色跨元素呼应：花材 / 包装 / 背景 / 缎带 / 缩略图。
- 精确比例，例如 70% 深基底 + 25% 主色 + 5% 点睛。

## i2i 生图 prompt 模板（直接套用）

以“Album Cover”为底图，花束图（可选）为花材参考：

```text
Base image: Image 1 is the album cover (describe its colors, title, and key visual).
[Image 2 is a bouquet photo, use only as flower/packaging material reference.]

Compose a premium editorial-style flower bouquet photograph inspired by the album:

COMPOSITION: (default) bouquet UPRIGHT and CENTERED, enlarged to fill most of the frame
with only a thin margin. Pure solid black background (matte, no texture, no reflection,
no gradient). Place the EXACT album cover as a small framed inset in the TOP-LEFT corner,
keeping its title text and key visual readable and recognizable. A ribbon trails down
the bouquet.

LIGHTING: hard directional side light from upper-left, clear light/shadow modeling on
petals and paper, clean shadows, highlights landing on the bouquet head and packaging.

BOUQUET STRUCTURE: airy, loose, natural triangular silhouette, visible negative space inside,
a few tall line stems reaching upward. Elegant and breathable, NOT a round ball, NOT dense.
Use only 3-5 flower types + 1-2 foliage, a modest arrangement realistically buildable in a shop.

FLOWERS (all real, dyed or spray-painted where needed to match the cover): [list only 3-5 concrete
real flowers + colors; specify spray-painted/dyed for any color that has no natural match].

PACKAGING: crisp folded paper, sharp angular asymmetric points, stiff matte [main color]
outer wrap with [secondary color] inner liner; [accent color] ribbon. On the wrapping
paper / backer card, add the album title and artist name in the cover's own lettering
style and exact colors (e.g. colorful cut-out letters matching the cover typography).

COLOR: restrained palette echoing the cover — [cover colors] on [base color] with pure
black background. Album text on the wrap must use the cover's own colors.

STYLE: premium florist editorial photography, magazine quality, high detail, sharp
focus, shallow depth of field, portrait orientation.
```

调用示例（Windows）：

```powershell
python "D:\...\image-gen\scripts\generate_image.py" --prompt-file "<prompt>.txt" --filename "<out>.jpg" --size 1024x1536 -i "<cover.png>" -i "<previous_bouquet.jpg>"
```

## 验证清单（生成后自查）

- [ ] 花束正放、居中、适度大小，只留窄边留白（不要填满）
- [ ] 背景纯黑、无反光、无纹理/丝绒残留
- [ ] 左上/右上角有可辨识的封面缩略图
- [ ] 包装纸/背板上有专辑文字，且用封面配色
- [ ] 花材 3–5 种、疏密有致、可实际制作（不堆砌）
- [ ] 难匹配的颜色用了喷漆/染色（dyed/spray-painted）
- [ ] 花束三角错落/疏朗透气而非圆球
- [ ] 包装尖角挺括
- [ ] 配色克制且与封面呼应，无杂色