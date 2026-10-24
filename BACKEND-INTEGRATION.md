# 后台接入说明

当前 `index.html` 是自包含静态前端。现有对练回复由规则生成，真实 AI 接入时可保留页面状态管理，只替换回复生成部分。

## 推荐接口

`POST /api/practice/reply`

请求：
```json
{"scene":"conflict","messages":[{"role":"assistant","content":"这两项都挺急的。你打算怎么安排？"},{"role":"user","content":"我建议先保证关键部分。"}],"userInput":"我建议先保证关键部分。","context":{"existing":"A 项目 · 明天下午交付","added":"B 方案 · 明天完成","constraint":"两项合计还需 2 天，目前只剩 1 天"}}
```
响应：
```json
{"reply":"如果先保证关键部分，另一项的时间或范围是否可以调整？"}
```

## 前端替换位置

- 发送后立即使用现有 `pendingChat` / `typingMessage()` 等待状态。
- 请求成功后，将返回的 `reply` 作为 `role: 'boss'` 消息加入 `state.messages`。
- 失败时清除等待状态，在 `#reply-error` 显示错误并允许重试。
- API Key 只能放在后端或密钥管理服务，不能放进 HTML、localStorage 或 URL。

`scene: "unclear"` 对应“要求不明确”，将 context 换成 `original`、`known` 和已选确认问题即可。保持发送按钮防重复提交、草稿保留、回看和反馈流程。
