# 珍珠网页钱包修复版

这是一个用于 Pearl L1（PRL）和以太坊 Wrapped PRL（WPRL）的非托管网页钱包。

本仓库主要记录我修复珍珠网页钱包无法访问钱包、无法交易的问题。

## 我修复的 Bug 点

- 修复珍珠网页钱包打开后一直加载，无法正常进入钱包的问题。
- 修复 PRL 余额无法加载的问题。
- 修复近期活动一直卡在“正在扫描珍珠+以太”，导致页面无法继续使用的问题。
- 修复因为浏览器无法直接访问外部 Pearl RPC，导致发送 PRL 交易失败的问题。
- 新增同源 PRL RPC 接口 `/api/pearl-rpc`，让网页钱包通过同源接口访问 Pearl 数据。
- 增加 RPC 超时、重试和备用节点处理，避免钱包一直卡死在加载状态。

## 修复后的效果

修复后可以正常：

- 打开珍珠网页钱包。
- 加载 PRL 钱包余额。
- 查看近期活动。
- 发送 PRL。
- 使用 PearlBridge 相关功能。

## 使用教程

### 1. 下载修复版

```powershell
git clone https://github.com/160037lk/pearlwallet.git
cd pearlwallet
```

### 2. 安装依赖

```powershell
npm install
```

### 3. 本地运行

```powershell
npm run dev
```

启动后，根据终端显示的地址打开钱包，通常是：

```text
http://localhost:5173
```

如果你使用的是已经打包好的本地钱包页面，也可以打开：

```text
http://127.0.0.1:8765/wallet.html
```

### 4. 构建发布文件

```powershell
npm run build
```

如果需要生成单文件离线 HTML：

```powershell
npm run build:offline
```

### 5. 进入钱包

- 创建新钱包，或导入已有助记词。
- 输入钱包密码解锁。
- 等待 PRL 余额和近期活动加载完成。

### 6. 发送 PRL

- 点击“发送 PRL”。
- 输入接收地址。
- 输入发送数量。
- 确认交易信息。
- 点击发送。

### 7. 注意事项

- 这是非托管钱包，助记词只保存在你自己手里。
- 助记词丢失后无法找回资产。
- 发送交易前一定要确认接收地址正确。
- 如果页面长时间加载，可以刷新页面后重新解锁钱包。

## PR

修复已提交到：

```text
https://github.com/PearlBridgeXYZ/pearlwallet/pull/2
```
