# 《绣枕》文学侦探社 — 互动学习网站

以凌叔华《绣枕》为文本的 **15 分钟个别化教学** 示范网站。学生自由选择任务难度、独立完成回答，再由教师检查，并可继续挑战更高层级。

## 功能

- **Level 1 故事侦探**：梳理绣枕制作、送出、最终遭遇的情节。
- **Level 2 心理侦探**：根据语言、动作或神态推断大小姐的情绪，并寻找文本证据。
- **Level 3 文学侦探**：分析绣枕的象征、反差和借物写人的效果。
- 15 分钟计时器（开始 / 暂停 / 重置）。
- 分关提示、答题框、进度条、教师在现场确认通过按钮。
- 学生答案保存在**当前设备的浏览器 localStorage**，可下载 `.txt` 学习记录。
- 提供 A4 打印视图；自适应手机与电脑。

## 项目结构

```text
xiuzhen-literary-detective/
├── index.html         # 网页内容
├── assets/
│   ├── style.css      # 视觉样式
│   └── app.js         # 互动逻辑
├── .nojekyll
├── .gitignore
└── README.md
```

## 本地预览

直接双击 `index.html` 即可打开（无需安装依赖或启动服务器）。也可使用：

```bash
python -m http.server 8000
```

然后打开 `http://localhost:8000`。

## 发布到 GitHub Pages（最简单方法）

1. 登录 GitHub，创建一个 **Public** repository，例如 `xiuzhen-literary-detective`。
2. 将本项目的 **全部文件和 `assets` 文件夹** 上传到仓库根目录并提交（Commit changes）；不要只上传 ZIP 压缩包。
3. 打开仓库 **Settings → Pages**。
4. 在 **Build and deployment** 中设置 **Source: Deploy from a branch**、**Branch: main**、目录 **/(root)**，点击 **Save**。
5. 发布完成后，网站通常可通过 `https://你的用户名.github.io/xiuzhen-literary-detective/` 打开（实际地址以 Pages 页面显示为准）。

也可以用 Git 命令上传（在项目文件夹中执行，并把 URL 改成你自己的仓库地址）：

```bash
git init
git add .
git commit -m "Initial commit: literary detective learning site"
git branch -M main
git remote add origin https://github.com/你的用户名/xiuzhen-literary-detective.git
git push -u origin main
```

## 教师使用流程（15 分钟）

| 时间 | 操作 |
|---|---|
| 0–2 分钟 | 说明玩法；学生选择关卡 |
| 2–9 分钟 | 独立作答；教师巡视与提供提示 |
| 9–12 分钟 | 教师检查答案；完成者继续挑战 |
| 12–14 分钟 | 学生分享发现 |
| 14–15 分钟 | 结案反思和导出答案 |

## 数据和安全说明

- **纯静态网站**：不需要服务器、数据库、API Key 或账号。
- 作答记录只保存在学生**当前浏览器的本地存储**；不会自动同步到教师或 GitHub。
- “提交供教师检查”和“教师确认通过”是**设备上的课堂流程标记，不是有身份验证的在线审批**。教师应在现场查看屏幕或让学生下载学习记录交给老师。
- 学生若清理浏览器数据、切换设备、或使用隐私模式，原答题记录可能无法恢复。建议及时导出。
- 若把仓库设为 Public，网页的**源代码及题目内容**可公开查看；学生答案不会因为发布网页而被公开上传。
- 本站不内置《绣枕》小说原文；学生需自备课堂提供的合法文本或节选。

## 自定义

- 修改题目：编辑 `index.html` 中 `work0` / `work1` / `work2` 三个区域。
- 修改提示：编辑 `hint0` / `hint1` / `hint2`。
- 修改颜色 / 排版：编辑 `assets/style.css`。
- 修改计时与交互：编辑 `assets/app.js`（默认 900 秒，即 15 分钟）。

网站适合课堂示范与学生自学；如果未来需要**教师后台集中收取所有学生答案**，则须增加有权限控制的服务器/数据库服务，不能单凭 GitHub Pages 实现。
