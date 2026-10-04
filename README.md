# YouTube 播放列表观看计划

![推广图](assets/promo.png)

把 YouTube 播放列表按你的每日可用时间整理成一份只读观看草稿：得到视频顺序、可见时长预算、每日建议、逐条来源和明确的缺失信息。列表受限或时长未知时，Skill 不会假装完整，也不会改动收藏或观看队列。

## 输入与结果

输入：一个播放列表 URL、每天可用分钟数，以及用户明确指定的 Easy WebBridge `browserId`。单次最多读取页面可见的 10 条视频。

结果：Markdown 表格，包含原始顺序、标题、可见时长、建议观看日、来源链接、已知总时长与待确认项。只把页面实际可见信息计入预算；私密、受限、登录验证或无时长项目会原样标记。

## 安装

```bash
npx skills add xxjrq/youtube-playlist-watch-plan-free
```

## 浏览器前置依赖

本 Skill 依赖可安装的 [Easy WebBridge（GitHub 主下载）](https://github.com/xxjrq/easy-webbridge)，GitHub 不可用时可用 [Gitee 备用地址](https://gitee.com/xxjrq/easy-webbridge)。先在目标浏览器加载其扩展并确认已连接；运行时必须由用户传入一个 `browserId`。

每次读取创建独立 session/标签组，只在该组内复用标签页，完成后仅关闭本 Skill 创建的组；不会广播到所有账号或接管既有页面。登录、验证码或风控页面会暂停，绝不绕过。

## 使用示例

```text
使用 browserId 读取 https://www.youtube.com/playlist?list=...，我每天有 30 分钟。
请生成最多 10 条的只读观看计划，保留每条来源和缺失信息；不要改动收藏或观看队列。
```

本仓库的 fixtures 是离线页面资料模拟，仅用于结构验证，不是在线采集结果。

## 本地验证

```bash
node scripts/self-test.mjs
```

## 来源与许可

业务用途参考：[OpenCLI](https://github.com/jackwener/OpenCLI) 及其 [YouTube adapter 文档](https://github.com/jackwener/OpenCLI/blob/main/docs/adapters/browser/youtube.md)。本 Skill 的说明、流程和 fixtures 为原创，未复制其实现；本仓库以 [MIT](LICENSE) 发布。
