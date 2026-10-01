# 专家包踩坑清单（2026-09 实测）

1. `plugin` 字段必须是**字符串**（填 "" 即可），写对象会报 cannot unmarshal object into ... of type string
2. `displayName` / `profession` / `displayDescription` / `defaultInitPrompt` 均为 **i18nField**：{ "en": "...", "zh": "..." }
3. `tags` 是 **i18nField 数组**：[ {en,zh}, {en,zh}, {en,zh} ]，固定 3 个
4. `quickPrompts` 同为 i18nField 数组，固定 3 个；`defaultInitPrompt` 的 zh 必须与 quickPrompts[0].zh 完全一致
5. `displayDescription` 中文长度 **40-50 字**（含标点，逐字数）
6. 内置技能：`plugin.json.skills` 路径必须写 `./skills/<name>`，且技能目录（含 SKILL.md）真实打进 zip
7. 头像 avatars/expert.png：512×512，≤500KB，PNG/JPG
8. agents/*.md frontmatter：name（同文件名）、description（英文）、displayName{en,zh}、profession{en,zh} 必填；maxTurns 默认 50
9. 开发者不可自行加 tools；工具权限由系统分配
10. zip 根目录为专家文件夹（与 name 同名），plugin.json 放在 .codebuddy-plugin/ 子目录下
