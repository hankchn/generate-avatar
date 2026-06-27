<p align="center"><b>简体中文</b> | <a href="./README_en.md">English</a></p>

# generate-avatar

一句话说明：这个 Skill 帮你把真人照片、风格参考或文字设定，生成适合小红书、X、GitHub 等平台使用的卡通头像。

## 这个版本能做什么

- 根据目标平台和使用场景，整理头像风格、构图、背景和导出要求。
- 支持三种输入方式：真人照片、照片加风格参考、纯文字人物设定。
- 生成 4 个方形头像候选，并围绕用户选择的一张继续精修。
- 在用户不确定风格时，展示内置风格板，帮助快速选择方向。
- 输出最终头像，并可继续准备圆形预览、平台尺寸和可复用生成提示词。

## 适合谁

- 想给小红书、X、GitHub、知识账号或个人品牌换头像的人。
- 需要从照片生成卡通头像，但不想自己写复杂提示词的人。
- 想保留人物识别特征，同时获得更简洁社交头像的人。

## 使用示例

风格选择可以参考这张内置风格板：

![头像风格板](./assets/avatar-style-board.png)

示例请求：

```text
使用 generate-avatar，帮我把这张照片做成适合 GitHub 的卡通头像。
风格要干净、专业，不要加文字和复杂背景。
```

预期结果：

- 先得到 4 个方形候选头像。
- 选择其中一个后，可以继续要求“背景更浅一点”“眼镜更明显一点”“做圆形预览”。
- 最终交付一张高质量方形头像，必要时附带平台尺寸版本。

## 快速开始

作为 Codex Skill 安装：

```bash
git clone https://github.com/hankchn/generate-avatar.git
mkdir -p ~/.codex/skills/generate-avatar
cp -R generate-avatar/{SKILL.md,agents,assets,references} ~/.codex/skills/generate-avatar/
```

重新打开 Codex 会话后，可以直接说：

```text
使用 generate-avatar，帮我生成一张适合小红书头像的卡通头像。
```

## 常见用法

- 上传一张真人照片，让 Skill 保留脸型、发型、眼镜、肤色和主要识别特征。
- 上传一张人物照片和一张风格参考图，让 Skill 区分“身份参考”和“风格参考”。
- 不上传照片，只用文字创建一个虚构人物头像。
- 在最终头像确定后，继续导出圆形预览或平台尺寸 PNG。

## 当前限制

- 没有真人照片时，不能声称头像像用户本人。
- 头像生成依赖当前会话可用的图像生成能力，不同模型可能有轻微风格差异。
- 默认只交付头像，不会自动制作完整社交主页视觉系统。
- 对模糊、遮挡严重或角度过大的照片，身份保留效果会下降。

## 安全与隐私说明

- 不要把生成结果用于身份验证、证件、冒充他人或误导性场景。
- 如果使用真人照片，请确认你有权使用这张照片。
- Skill 不需要保存账号密码、API key 或平台登录信息。

## 技术实现

- `SKILL.md` 定义头像生成工作流、澄清规则和安全边界。
- `assets/avatar-style-board.png` 用于帮助选择头像风格。
- `references/` 保存平台尺寸、提示词模板和风格说明。

## License

[MIT](./LICENSE)

## Contributors

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/hankchn">
        <img src="https://github.com/hankchn.png" width="64" height="64" style="border-radius:50%;" alt="hankchn" />
        <br />
        <sub><b>hankchn</b></sub>
      </a>
      <br />
      <sub>Hank Yang</sub>
    </td>
    <td align="center">
      <a href="https://openai.com/codex">
        <img src="https://github.com/openai.png" width="64" height="64" style="border-radius:50%;" alt="Codex" />
        <br />
        <sub><b>Codex</b></sub>
      </a>
      <br />
      <sub>OpenAI Codex</sub>
    </td>
  </tr>
</table>
