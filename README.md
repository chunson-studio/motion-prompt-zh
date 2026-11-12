# Motion Prompt 中文版

基于 [Shohei Ohtaki 的 Motion Prompt](https://github.com/showheyohtaki/motion-prompt) 制作的非官方简体中文适配。

原版的 192 个动态示例、8 个分类、效果编号、Canvas 绘制逻辑和 MIT 版权声明均保留。本版补齐了简体中文界面、详细参数、适用场景、提示词和中文搜索，保留英文与日文界面。画布内部的 167 个日文标签也已中文化，涉及 194 处字符串；逐字动画的关键字符数量保持不变，英文设计样字保留。

## 使用

打开网页 → 按中文、英文或编号搜索 → 查看效果或加入选择 → 写创作备注 → 复制提示词并粘贴给 AI。

无需安装 skill。页面上的安装命令安装原作者的 skill，该 skill 默认打开原版图库，不会自动改为本中文版。本版默认使用复制工作流；兼容的本地 skill 会话可使用原版回传机制。

提示词完整内嵌中文规格，并链接原项目公开的英文参考代码，避免依赖私有网站的访问权限。选择链接指向当前站点，保留效果编号、语言和创作备注；站点访问权限保持不变。

## 本地运行

本项目无第三方运行时依赖，无需 npm install。用任意静态服务器托管 `./`。

```bash
python3 -m http.server 8000 --directory dist
```

然后打开 `http://localhost:8000/`。请使用静态服务器；`file://` 模式下浏览器可能阻止加载参考代码。

## 修改与构建

- 内容源：`./packs/*/meta.json`
- 原始动画：`./packs/*/pack.js`
- 中文界面：`./assets/zh-ui.js`
- 中文排版：`./assets/zh.css`
- 页面逻辑：`./assets/site.js`

修改内容源后生成目录与中文 API：

```bash
node ./tools/build.mjs
node ./tools/build.mjs --check
```

`api/v1/zh-Hans/catalog.tsv` 是中文目录；`api/v1/zh-Hans/e/001.txt` 是带中文规格的示例代码；`api/v1/zh-Hans/p/001.txt` 是中文提示词。编号范围为 001–192。

保留 `./LICENSE` 和 `./THIRD-PARTY-NOTICES.md`。原作者为 Shohei Ohtaki；原始简体中文术语沿用原项目贡献者的翻译。中文适配并非原作者的官方版本。

上游基线提交：7819d3879eb7d5a1475c11c001bedffb5cab64af。
