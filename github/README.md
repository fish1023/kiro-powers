# kiro-powers-github

Kiro 自定义 GitHub MCP Power，标准 powers 结构，支持一键导入。

## 目录结构 (Structure)

```
kiro-powers-github/
├── POWER.md              # 必须，元数据和说明文档
├── mcp.json              # MCP server 配置 (如需集成 GitHub 工具)
└── steering/             # 可选，针对特定流程的引导文件
    └── workflow.md
```

## 快速集成 (Quick Integration)

### 方式一：通过 GitHub URL 导入（推荐）

1. 打开 kiro 控制台，进入 Powers 面板
2. 选择 “Add power from GitHub”
3. 输入本仓库地址：  
   ```
   https://github.com/holla-yushang/kiro-powers-github
   ```
4. 点击 Install。Powers panel 会自动检测并集成交付（仓库需有合法的 POWER.md）。

### 方式二：本地路径导入

1. 克隆仓库到本地：
   ```bash
   git clone https://github.com/holla-yushang/kiro-powers-github.git
   ```
2. Powers 面板选择 “Add power from Local Path”
3. 选择包含 `POWER.md` 文件的目录（如 `kiro-powers-github/` 根目录），点击 Install

## 环境变量 (Environment Variables)

- `GITHUB_ACCESS_KEY`：GitHub 访问密钥，用于 MCP server 认证

配置举例：  
```bash
export GITHUB_ACCESS_KEY=your_github_token
```
或将其放入 `.env` 文件（推荐）。

## 详细文档 (Documentation)

- 能力说明、参数和使用示例详见 [`POWER.md`](./POWER.md)
- MCP 服务器详细配置见 [`mcp.json`](./mcp.json)
- 更多官方指南见：[https://kiro.dev/docs/powers/installation/](https://kiro.dev/docs/powers/installation/)

## License

See repository license for details.