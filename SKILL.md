---
name: underground-flash-editorial
description: 将参考图、文字描述或已有提示词转化为 1990 年代地下时尚杂志摄影，以粗粝 35mm 胶片扫描、机顶直闪、暖红棕与轻微脏绿阴影、随拍式反时尚气质为固定风格，默认使用当前可用的 GPT 图像生成能力出图。适用于地下杂志风、粗粝胶片直闪、反时尚摄影及同风格图片改写。
---

# 地下直闪 · 反时尚影像

将用户的画面内容转写为统一的地下时尚编辑摄影。风格定义来自用户提供的两版英文提示词；沿用参考技能的组织方法，重新设计本技能的视觉内容和执行规则。

## 一、默认行为与优先级

- 接受参考图、文字描述、已有提示词，也接受三者组合。
- 默认用当前环境实际可用的 GPT 图像生成能力生成一张图片，并交付可复用提示词。用户明确指定数量时遵从其要求。
- 用户说“只要提示词”“不出图”或仅要求分析时，不调用生成工具。
- 优先级：用户本次明确要求 > 用户要求保留的参考特征 > 本技能默认风格 > 合理补充。延续同一张图的修改时，继承此前已经明确的要求；本次明确修改的部分覆盖旧要求。
- 用户已给出足够内容时直接执行，不逐项询问。只有缺失参考图、无法判断多图用途或关键要求互相矛盾时，才提出最少必要问题。
- 本技能不绑定不存在或未经确认的模型版本，不承诺固定尺寸、种子或绝对人物一致性。

## 二、固定视觉 DNA

### 1. 1990 年代地下时尚杂志

独立街头刊物的编辑摄影气质，亲近主体、有现场感、粗糙而有造型意识。默认生成完整摄影画面，不添加杂志封面、排版、标题、边框或水印。

锚点：`1990s underground fashion magazine photography`, `street zine editorial`, `underground street culture`。

### 2. 粗粝 35mm 胶片扫描

明显、有机的高感光度胶片颗粒；整体中间调与环境略欠曝，动态范围有限，但关键内容仍可辨。焦点轻微不完美，不把主体处理成失焦废片。粗粝来自颗粒、曝光和材质，不依赖污渍、破损边框、严重漏光或密集划痕。

锚点：`gritty vintage 35mm film scan look`, `high ISO organic grain`, `slight underexposure`, `soft imperfect focus`, `low dynamic range`。

### 3. 暖红棕主调与轻微脏绿阴影

红棕色主要落在肤色、高光附近、中间调和环境暖色中；脏绿只进入部分阴影与荧光环境光。两者形成轻微的胶片色彩分离，而不是普通的暖肤色配冷背景。保持肤色、服装色块和用户指定产品颜色可辨认，不以均匀红绿滤镜覆盖全部画面。

锚点：`warm red-brown tones`, `subtle dirty green shadows`, `restrained color separation`。

### 4. 机顶直接闪光

闪光与镜头方向接近，直接照亮主体，产生正面高光、快速光线衰减与可见投影；脸部可以略显苍白或平，但仍保留皮肤纹理，避免美容光塑造的精致轮廓。背景和环境相对偏暗。近墙时投影可以鲜明，远景或开阔空间不强造墙面阴影。保留环境信息，避免默认把背景压成纯黑。

锚点：`direct on-camera flash`, `point-and-shoot camera aesthetic`, `flash-lit subject against a slightly underexposed environment`。

硬直闪与轻微软焦可以共存：前者描述照明，后者描述成像。不要误把直闪当作冲突词删除。

### 5. 不修饰的真实质感

保留皮肤毛孔、自然瑕疵、衣料纹理与场地痕迹。无人物时转为强调物体和环境的真实表面。不自动添加伤痕、脏污、破损或改变人物年龄。

锚点：`raw and unretouched realism`, `natural skin and material texture`, `anti-glossy`。

### 6. 随拍式反时尚态度

画面自然、自发、不拘谨，带有偶然取景的张力。反时尚首先体现在拍摄态度、姿态与构图，不默认添加夸张服饰、怪异配饰、吸烟动作或奇怪身体姿势。

锚点：`candid anti-fashion energy`, `imperfect snapshot energy`, `rough, spontaneous, unpolished`。

### 默认强度与调整范围

默认接近用户原始提示词的强度：颗粒在皮肤、中间调和暗部都清晰可见，直闪鲜明，欠曝轻微，焦点柔化轻微，红棕能够被感知，脏绿只停留在部分阴影。它们是相对视觉目标，不是模型数值参数。

- “更粗粝”：优先增强颗粒和未经精修的表面，不自动加重模糊、划痕或欠曝。
- “直闪更强”：增强正面闪光高光与合理投影，不把脸和衣料烧成无细节白块。
- “更复古”：调整胶片色彩与扫描质感，不自动把现代场景、服装和道具换成 90 年代物品。
- “更反时尚”：先调整拍摄距离、取景和松弛感；改变服装或姿势仍需符合用户内容要求。
- “稍微”“一点”：只做局部小幅调整，不整体重设风格强度。

1990 年代指摄影语言，不默认指定故事年代。白天场景保留白天，采用日光环境中的近距离直闪；夜间场景允许更明显的明暗落差。不要为制造地下感把所有画面改成夜晚、停车场或破旧街巷。

## 三、输入拆解与保留规则

| 要素 | 提取内容 | 处理规则 |
|---|---|---|
| 主体与动作 | 人物、物品、数量、动作、表情 | 保留明确要求；无人画面不补人物 |
| 造型与识别特征 | 发型、服装、轮廓、配饰、产品结构 | 参考图中要求保留的特征优先于风格化 |
| 场景与道具 | 地点、时段、环境物件及相互关系 | 缺失可省略；补充只为让画面成立 |
| 空间与摄影 | 景别、机位、朝向、前中后景、比例 | 用户指定构图优先，不为随拍感随意裁掉关键部位 |

先区分“用户明确提供”“图中可见”“为生成补充”。影响画面内容的新增设定在简短说明中标为“补充设定”，不把推测当作图中事实。不要从模糊外貌推断身份或不可见信息。

多图输入先识别角色：主体参考、造型参考、风格参考或构图参考。用途明显则直接执行；用途冲突且影响结果时再询问。不要把风格参考中的人物、文字或道具无意复制进新画面。

## 四、执行流程

### A. 参考图风格化

1. 实际查看图片，提取上述要素与必须保留的特征。
2. 用户要求“把这张图改成该风格”时，默认保留主体、数量、动作、服装、场景和构图，只转换摄影质感。用户要求“参考这张的风格生成新内容”时，只借用风格，以新内容为准。
3. 使用支持参考图的实际生成或编辑入口，并传入图片；不能只凭文字声称已使用参考图。
4. 用户只改某一处时限定编辑范围，避免重新设计整个画面。连续修改以最近被用户接受的成图为基础；有原始人物或产品参考时同时保留其识别约束，避免逐轮漂移。

### B. 文字生成

1. 提取明确的主体、事件、造型与环境。
2. 用最少合理补充解决画面必要空缺，不强制凑齐人物和道具。
3. 注入固定视觉 DNA，保留用户内容，不让风格词淹没主体。

### C. 已有提示词改写

1. 保留内容、数量、动作及用户要求的构图。
2. 将旧有风格词替换为本技能视觉语言，去除互相矛盾的光线与精修要求。
3. 若冲突来自用户明确要求而不是旧模板，优先遵从用户；必要时说明这是风格变体。

### D. GPT 出图

1. 完成出图前检查。
2. 调用当前环境实际可用的 GPT 图像生成能力。当前环境若提供 image_gen.imagegen，使用其受支持参数传入完整提示词和适用的参考图；其他环境按实际工具说明调用。
3. 构图比例与生成数量通过工具支持的字段或自然语言表达。不得编造 size、quality、seed、output_dir 等工具未提供的参数。
4. 默认文字人像采用 3:4 构图意图，环境场景采用 4:3，独立物体可采用 1:1；参考图编辑默认沿用原比例。用户指定比例始终优先，实际输出受工具支持限制。
5. 生成工具不可用时，明确说明未生成图片，交付完整提示词；不要自行切换为其他厂商模型并声称是 GPT。
6. 本次调用失败时，按具体错误修正；不要连续盲目重试。生成成功但存在明显可修正偏差时，最多做一次定向修正。

## 五、提示词拼装公式

按以下顺序组织为自然语言，而不是堆叠重复标签：

主体与动作 → 造型及必须保留特征 → 场景道具 → 景别、机位、构图与比例 → 直闪和环境曝光关系 → 胶片颗粒、焦点与色彩 → 编辑摄影情绪 → 必要排除项。

默认提供英文生成提示词，中文简要解释。英文是本技能的交付约定，不宣称所有模型都更偏好英文。用户要求中文时可改用中文。

### 核心风格段

```text
A bold underground fashion editorial photograph with the spirit of a cheaply printed 1990s street zine. Gritty consumer 35mm color-negative film scan, coarse high-ISO organic grain clearly visible across skin, midtones and shadows, slightly underexposed ambient surroundings, soft imperfect focus while keeping defining subject details readable, and compressed low dynamic range with essential shadow detail retained. A perceptible warm red-brown bias in skin, highlights and midtones, separated from restrained dirty-green contamination in selected shadows and fluorescent ambient light. Direct on-camera flash lights the subject with blunt frontal illumination, rapid flash falloff, hard highlights and spatially plausible shadows, creating a point-and-shoot camera aesthetic. Raw, unretouched skin and material texture; candid anti-fashion energy; rough, awkward, spontaneous snapshot realism with an independent-editorial eye. Avoid cinematic lighting, studio lighting setups, beauty-light sculpting, polished luxury-fashion posing, glossy commercial retouching, plastic skin, and excessive digital sharpening. Do not add editorial text overlays, watermarks, magazine layouts, or decorative film damage unless requested. Preserve scene lettering or product marks when required by the user or reference.
```

将核心风格段与真实内容整合，删掉不适用于画面的词句。例如静物图不写皮肤，用户要求招牌文字时不禁止全部文字。最终提示词不得残留占位符。

### 完整示例

用户输入：一个穿黑色皮衣的人站在便利店门口，竖图。

```text
A person in a black leather jacket stands outside a convenience store, photographed in a vertical 3:4 three-quarter-length composition from close to eye level, slightly off-center, with the entrance visible behind them. A bold underground fashion editorial photograph with the spirit of a 1990s street zine. Direct on-camera flash illuminates the face and brings out the leather texture, while the store interior and ambient surroundings remain slightly underexposed. Gritty vintage 35mm film scan look, visible high ISO organic grain, soft imperfect focus with facial features still readable, low dynamic range, warm red-brown tones, and subtle dirty green shadows. Raw unretouched skin, a relaxed unposed stance, point-and-shoot immediacy, and candid anti-fashion energy. Avoid cinematic lighting, studio lighting setups, glossy commercial retouching, plastic skin, artificial film scratches, added editorial text, and watermarks.
```

示例中的景别、机位与姿态属于补充设定，不是所有请求的固定要求。

## 六、模型适配

- 默认面向 GPT 图像生成：使用自然语言描述内容、约束与视觉关系；独立负向参数不可用时，把必要排除项写入提示词。
- 不混入 Midjourney 的 --ar、--style、--v，或 Stable Diffusion 的括号权重语法。
- 不将其他模型的参数格式直接套到 GPT 工具中。
- 用户明确要求导出其他模型版本时，保留视觉 DNA，依据该目标的实际接口另行适配；不自动触发另一平台出图。
- 参考图编辑遵循实际工具的图片传入方式；无法访问原图时请求重新提供，不能假装已看图。

## 七、质量检查

### 出图前

- 主体、数量、动作、指定造型和参考保留项是否准确？
- 六组视觉 DNA 是否被合理表达，是否有不适用内容需要删除？
- 是否误混入电影布光、棚拍柔光、光滑商业精修等默认排除风格？
- 直闪主体与偏暗环境是否协调？轻微软焦是否仍保护识别特征？
- 颗粒是否也能在主体和中间调中看到，而不是只有暗部数字噪点？红棕与脏绿是否形成局部色彩分离，而非普通冷暖调色？
- 比例、景别和裁切是否满足用户要求？
- 是否有无依据增加的人物、配饰、动作、文字或损坏效果？
- 工具参数与参考图是否实际可用？

检查默认内部完成，无需每次向用户展示长清单。

### 典型请求的行为检查

修订本技能时，用以下情形核对规则是否仍成立；这些是行为预期，不代表已经通过实际出图测试：

| 请求 | 应有行为 |
|---|---|
| “白天田野里的人像，地下直闪风” | 保留白天与田野，近距离主体受直闪照亮，不强改夜景 |
| “把这张红色包的产品图改成这个风格” | 保留包的形状、红色和必要标记，不补人物，绿影不过度染色 |
| “参考这张的质感，生成便利店门口的人” | 借用摄影质感，不复制参考图主体和场景 |
| “只要提示词，颗粒稍微加一点” | 不出图，只小幅修改颗粒相关表述 |
| “脸保持清楚，其他沿用上一张” | 保持此前构图、造型与色调，局部恢复脸部清晰度 |

### 成图后

实际查看成图，检查主体和保留项、直闪效果、颗粒强度、红棕与绿影平衡、纹理与清晰度，以及肢体或物体结构是否明显异常。检查的是画面效果，不是提示词是否包含关键词。

偏差明显时只针对问题修正一次，例如减弱全画面绿色、恢复服装细节、加强闪光主体与环境的曝光差，避免重写全部内容导致主体漂移。一次修正后仍有偏差，如实指出，不无限重生成。无法查看结果时说明未完成视觉检查，不宣称检查通过。

## 八、交付规范

默认交付：

1. 展示实际生成的图片。
2. 给出本次实际用于生成的完整提示词，便于复制复用；工具另行改写且不可见时，不冒充已知改写内容。
3. 必要时用一句中文说明补充设定、定向修正或尚存偏差。
4. 能取得本地成图时，保存或交付到当前工作区允许的用户输出目录，并提供真实可用的文件链接。遵循宿主的交付目录约定，不虚构路径；只有工具原生图片结果时直接展示。

“只要提示词”模式：交付完整提示词和必要的补充设定说明，不调用图像生成，不伪造图片链接。

用户要求精简、仅图或详细解析时，按其要求调整呈现。详细解析可使用四类要素表，但不把每次出图都变成冗长报告。
