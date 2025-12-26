# Opinion 圣诞活动达标查询工具 - 本地独立版

[English](#english-version) | [中文](#中文版本) | 联系作者：[Mocoonin](https://x.com/Mocoonin)

---

## 中文版本

### 📋 简介
<img width="3786" height="1936" alt="image" src="https://github.com/user-attachments/assets/dc035922-4cd3-481e-9afe-1f7cc1f1b755" />


这是 Opinion.trade 假日活动数据查询工具的**纯前端本地版本**，无需安装Node.js或任何后端服务器，直接在浏览器中运行。

**适用场景：**
- ✅ 个人快速查询
- ✅ 无法运行Node.js环境
- ✅ 临时使用或测试

**不适用场景：**
- ❌ 需要查询大量地址（建议使用服务器版本）
- ❌ 需要定时自动查询
- ❌ 浏览器有严格的CORS限制

---

### ⚠️ 重要说明

#### CORS跨域限制
由于浏览器安全限制，本地版本可能无法直接访问Opinion.trade的API。如果遇到 **"Failed to fetch"** 错误，请：

1. **推荐方案：使用服务器版本**
   - 下载 `opinion_trade_v2.0_final.tar.gz`
   - 按照服务器版本文档部署

2. **临时方案：安装浏览器扩展**（仅用于测试）
   - Chrome/Edge: 安装 [CORS Unblock](https://chromewebstore.google.com/detail/cors-unblock/lfhmikememgdcahcdlaciloancbhjino)
   - Firefox: 安装 [CORS Everywhere](https://addons.mozilla.org/zh-CN/firefox/addon/cors-everywhere/)
   - ⚠️ 使用后记得关闭扩展

3. **替代方案：使用支持CORS的浏览器设置**
   - 不推荐，因为会降低浏览器安全性

#### 交易笔数说明
**关于交易笔数有争议，目前工具只能查询到链上交易记录的笔数。**

🔴 **强烈建议以官网里面的"已关闭订单"为准！**

如果你不记得你做了几笔，最好去登录查询。

💡 **建议：** 交易时记录下自己提交订单的次数，以便核对。

---

### 🚀 快速开始

#### 第1步：获取API Key

1. 访问 [Opinion.trade API申请页面](https://docs.opinion.trade/developer-guide/opinion-open-api/overview)
2. 填写申请表单获取API Key
3. API Key格式类似：`sk_xxxxxxxxxxxxxxxxxxxxxxxx`

#### 第2步：打开工具

1. 下载 `index_local_standalone.html` 文件
2. 双击文件，或右键选择"用浏览器打开"
3. 推荐使用Chrome、Edge或Firefox浏览器

#### 第3步：配置

首次打开会自动弹出配置窗口：

```
┌─────────────────────────────────────────────┐
│  🔑 钱包配置                                │
├─────────────────────────────────────────────┤
│  🔐 API Key:                                │
│  ┌─────────────────────────────────────┐   │
│  │ sk_your_api_key_here                │   │
│  └─────────────────────────────────────┘   │
│                                             │
│  💼 钱包地址 (每行一个):                    │
│  ┌─────────────────────────────────────┐   │
│  │ 0x1234567890abcdef...                │   │
│  │ 0xabcdef1234567890... Alice          │   │
│  │ 0x9876543210fedcba... Bob            │   │
│  └─────────────────────────────────────┘   │
│                                             │
│              [取消]  [保存]                 │
└─────────────────────────────────────────────┘
```

**配置说明：**
- **API Key：** 必填，输入你申请的Opinion API Key
- **钱包地址：** 每行一个，格式：`地址 备注`（备注可选）
- **最多100个地址**

#### 第4步：查询

保存配置后，工具会自动开始查询并显示结果。

---

### 🔧 功能说明

#### 主要功能
- ✅ 批量查询多个钱包地址
- ✅ 自动计算每日达标情况
- ✅ 智能缓存（过去的已达标天数）
- ✅ 展开/折叠详细数据
- ✅ 中英文切换
- ✅ 本地数据缓存

#### 达标规则
- **活动时间：** 2025-12-22 至 2026-01-05
- **每日标准：** 
  - 交易次数 ≥ 4次
  - 交易金额 ≥ $2000
- **达标要求：** 任意10天达标即可
- **奖励：**
  - 🏆 每日战士：10天达标
  - 💰 交易量王者：10天达标

#### 缓存机制
- ✅ 只缓存**过去**已达标的天数
- ✅ **今天**的数据每次都会重新查询
- ✅ 手动清除：点击"清空缓存"按钮

---

### 🔒 隐私与安全

#### 数据存储位置
- **API Key：** 存储在浏览器 `localStorage`
- **钱包配置：** 存储在浏览器 `localStorage`
- **查询缓存：** 存储在浏览器 `localStorage`

#### 安全说明
- ✅ 所有数据仅保存在**你的浏览器本地**
- ✅ 不会上传到任何服务器（除了调用Opinion API）
- ✅ 只有你能访问这些数据
- ✅ 清除浏览器数据会同时清除所有配置

#### 清除数据
如需完全清除：
1. 点击工具右上角的"清空缓存"按钮
2. 或在浏览器中清除网站数据：
   - Chrome: F12 → Application → Storage → Clear site data
   - Firefox: F12 → Storage → Local Storage → 右键删除

---

### 💡 使用技巧

#### 1. 快速刷新
点击右上角"刷新数据"按钮重新查询所有地址

#### 2. 展开/折叠
- 点击"查看"按钮查看单个地址的详细数据
- 使用右侧悬浮按钮展开/折叠所有地址

#### 3. 语言切换
点击右上角"中文"/"EN"按钮切换界面语言

#### 4. 修改配置
点击右上角"钱包"图标重新打开配置窗口

---

### ❌ 常见问题

#### Q1: 显示 "HTTP 404" 错误？
**原因：** API端点不存在或已变更

**解决方案：**
1. **推荐：** 使用服务器版本（`opinion_trade_v2.0_final.tar.gz`）
   - 服务器版本会自动适配API变更
   - 无CORS限制
   - 性能更好

2. **检查API Key：** 确保API Key有效且已通过审核

3. **查看控制台日志：**
   ```
   按 F12 打开浏览器开发者工具
   → Console 标签
   → 查看详细的错误信息和尝试的端点
   ```

4. **联系技术支持：** 如果问题持续，可能是API已更新

#### Q2: 显示 "Failed to fetch" 错误？
**原因：** 浏览器CORS跨域限制

**解决方案：**
1. **推荐：** 使用服务器版本（`opinion_trade_v2.0_final.tar.gz`）
2. 安装CORS扩展（仅测试用）
3. 检查API Key是否正确

#### Q2: API Key 无效？
**检查：**
- ✅ API Key格式正确（以`sk_`开头）
- ✅ API Key未过期
- ✅ 已通过Opinion.trade审核

#### Q3: 查询很慢？
**原因：**
- 地址太多
- 网络延迟
- API限流

**建议：**
- 减少同时查询的地址数量
- 使用服务器版本（性能更好）

#### Q4: 数据不准确？
**交易笔数争议：**

本工具查询的是**链上交易记录**，与官网的**已关闭订单**可能不一致。

🔴 **强烈建议以官网"已关闭订单"为准！**

#### Q5: 如何备份配置？
浏览器localStorage数据可通过开发者工具导出：
```javascript
// F12 打开控制台，执行：
console.log(localStorage.getItem('opinion_api_key'));
console.log(localStorage.getItem('opinion_addresses'));
```

---

### 📊 与服务器版本对比

| 特性 | 本地版 | 服务器版 |
|------|--------|----------|
| 部署难度 | ⭐ 简单 | ⭐⭐⭐ 需要Node.js |
| 使用方式 | 双击打开 | 需要启动服务器 |
| CORS限制 | ❌ 有限制 | ✅ 无限制 |
| 性能 | 一般 | 优秀 |
| 批量查询 | 适合<20个地址 | 适合大量地址 |
| API Key安全 | 浏览器本地 | 服务器.env文件 |
| 适用场景 | 个人临时使用 | 团队持续使用 |

---

### 🔄 更新日志

#### v1.0 (2025-12-26)
- ✅ 纯前端实现
- ✅ API Key本地配置
- ✅ 智能缓存机制
- ✅ 交易笔数争议提示
- ✅ 中英文双语支持
- ✅ 多API端点自动切换

---

### 📞 支持

遇到问题？
1. 查看本README的[常见问题](#常见问题)部分
2. 检查浏览器控制台（F12）的错误信息
3. 考虑使用服务器版本

---

### ⚖️ 免责声明

本工具仅用于查询Opinion.trade公开数据，不保证数据的准确性。交易笔数请以官网为准。使用本工具即表示同意自行承担使用风险。

---

## English Version

### 📋 Introduction
<img width="3774" height="1938" alt="image" src="https://github.com/user-attachments/assets/6aefbe63-9af8-43b6-849e-48c731744001" />


This is a **pure frontend standalone version** of the Opinion.trade Holiday Event data query tool. No Node.js or backend server required - runs directly in your browser.

**Suitable for:**
- ✅ Personal quick queries
- ✅ Cannot run Node.js environment
- ✅ Temporary use or testing

**Not suitable for:**
- ❌ Large number of addresses (use server version)
- ❌ Scheduled automated queries
- ❌ Browsers with strict CORS restrictions

---

### ⚠️ Important Notes

#### CORS Cross-Origin Restrictions
Due to browser security restrictions, the local version may not directly access Opinion.trade's API. If you encounter **"Failed to fetch"** errors:

1. **Recommended: Use Server Version**
   - Download `opinion_trade_v2.0_final.tar.gz`
   - Deploy according to server version documentation

2. **Temporary: Install Browser Extension** (Testing only)
   - Chrome/Edge: Install [CORS Unblock](https://chromewebstore.google.com/detail/cors-unblock/lfhmikememgdcahcdlaciloancbhjino)
   - Firefox: Install [CORS Everywhere](https://addons.mozilla.org/en-US/firefox/addon/cors-everywhere/)
   - ⚠️ Remember to disable after use

3. **Alternative: Browser CORS Settings**
   - Not recommended as it reduces browser security

#### Trade Count Disclaimer
**There is a dispute about trade count. This tool can only query on-chain transaction records.**

🔴 **Strongly recommended to use "Closed Orders" on the official website as the standard!**

If you don't remember your trade count, please login to check.

💡 **Tip:** Record your order submission count when trading for verification.

---

### 🚀 Quick Start

#### Step 1: Get API Key

1. Visit [Opinion.trade API Application Page](https://docs.opinion.trade/developer-guide/opinion-open-api/overview)
2. Fill out the application form to get API Key
3. API Key format: `sk_xxxxxxxxxxxxxxxxxxxxxxxx`

#### Step 2: Open Tool

1. Download `index_local_standalone.html` file
2. Double-click the file, or right-click and select "Open with Browser"
3. Recommended browsers: Chrome, Edge, or Firefox

#### Step 3: Configuration

A configuration window will pop up automatically on first launch:

```
┌─────────────────────────────────────────────┐
│  🔑 Wallet Config                           │
├─────────────────────────────────────────────┤
│  🔐 API Key:                                │
│  ┌─────────────────────────────────────┐   │
│  │ sk_your_api_key_here                │   │
│  └─────────────────────────────────────┘   │
│                                             │
│  💼 Wallet Addresses (one per line):        │
│  ┌─────────────────────────────────────┐   │
│  │ 0x1234567890abcdef...                │   │
│  │ 0xabcdef1234567890... Alice          │   │
│  │ 0x9876543210fedcba... Bob            │   │
│  └─────────────────────────────────────┘   │
│                                             │
│              [Cancel]  [Save]               │
└─────────────────────────────────────────────┘
```

**Configuration Details:**
- **API Key:** Required, enter your Opinion API Key
- **Wallet Addresses:** One per line, format: `address remark` (remark optional)
- **Maximum 100 addresses**

#### Step 4: Query

After saving configuration, the tool will automatically start querying and display results.

---

### 🔧 Features

#### Main Features
- ✅ Batch query multiple wallet addresses
- ✅ Auto-calculate daily qualification status
- ✅ Smart caching (past qualified days)
- ✅ Expand/collapse detailed data
- ✅ Chinese/English language toggle
- ✅ Local data caching

#### Qualification Rules
- **Event Period:** 2025-12-22 to 2026-01-05
- **Daily Standards:**
  - Trade count ≥ 4 times
  - Trade volume ≥ $2000
- **Qualification:** Any 10 days meeting standards
- **Rewards:**
  - 🏆 Daily Warrior: 10 days qualified
  - 💰 Volume King: 10 days qualified

#### Caching Mechanism
- ✅ Only caches **past** qualified days
- ✅ **Today's** data is re-queried every time
- ✅ Manual clear: Click "Clear Cache" button

---

### 🔒 Privacy & Security

#### Data Storage Location
- **API Key:** Stored in browser `localStorage`
- **Wallet Config:** Stored in browser `localStorage`
- **Query Cache:** Stored in browser `localStorage`

#### Security Notes
- ✅ All data saved **locally in your browser only**
- ✅ Not uploaded to any server (except Opinion API calls)
- ✅ Only you can access this data
- ✅ Clearing browser data also clears all configurations

#### Clear Data
To completely clear:
1. Click "Clear Cache" button in top right corner
2. Or clear site data in browser:
   - Chrome: F12 → Application → Storage → Clear site data
   - Firefox: F12 → Storage → Local Storage → Right-click delete

---

### 💡 Usage Tips

#### 1. Quick Refresh
Click "Refresh" button in top right to re-query all addresses

#### 2. Expand/Collapse
- Click "View" button to see detailed data for single address
- Use floating buttons on right to expand/collapse all addresses

#### 3. Language Toggle
Click "中文"/"EN" button in top right to switch interface language

#### 4. Modify Config
Click wallet icon in top right to reopen configuration window

---

### ❌ FAQ

#### Q1: "HTTP 404" error?
**Reason:** API endpoint not found or has changed

**Solutions:**
1. **Recommended:** Use server version (`opinion_trade_v2.0_final.tar.gz`)
   - Server version auto-adapts to API changes
   - No CORS restrictions
   - Better performance

2. **Check API Key:** Ensure API Key is valid and approved

3. **Check Console Logs:**
   ```
   Press F12 to open browser developer tools
   → Console tab
   → View detailed error messages and attempted endpoints
   ```

4. **Contact Support:** If issue persists, API may have been updated

#### Q2: "Failed to fetch" error?
**Reason:** Browser CORS cross-origin restriction

**Solutions:**
1. **Recommended:** Use server version (`opinion_trade_v2.0_final.tar.gz`)
2. Install CORS extension (testing only)
3. Check if API Key is correct

#### Q2: API Key invalid?
**Check:**
- ✅ API Key format correct (starts with `sk_`)
- ✅ API Key not expired
- ✅ Approved by Opinion.trade

#### Q3: Query very slow?
**Reasons:**
- Too many addresses
- Network latency
- API rate limiting

**Suggestions:**
- Reduce number of addresses queried simultaneously
- Use server version (better performance)

#### Q4: Data inaccurate?
**Trade Count Dispute:**

This tool queries **on-chain transaction records**, which may differ from **Closed Orders** on the official website.

🔴 **Strongly recommended to use official website "Closed Orders" as standard!**

#### Q5: How to backup config?
Browser localStorage data can be exported via developer tools:
```javascript
// Open console with F12, execute:
console.log(localStorage.getItem('opinion_api_key'));
console.log(localStorage.getItem('opinion_addresses'));
```

---

### 📊 Comparison with Server Version

| Feature | Local Version | Server Version |
|---------|---------------|----------------|
| Deployment | ⭐ Simple | ⭐⭐⭐ Requires Node.js |
| Usage | Double-click open | Needs server startup |
| CORS Limits | ❌ Has limits | ✅ No limits |
| Performance | Fair | Excellent |
| Batch Query | <20 addresses | Large volumes |
| API Key Security | Browser local | Server .env file |
| Use Case | Personal temporary | Team continuous |

---

### 🔄 Changelog

#### v1.0 (2025-12-26)
- ✅ Pure frontend implementation
- ✅ Local API Key configuration
- ✅ Smart caching mechanism
- ✅ Trade count dispute notice
- ✅ Chinese/English bilingual support
- ✅ Auto-switch multiple API endpoints

---

### 📞 Support

Having issues?
1. Check [FAQ](#faq) section in this README
2. Check browser console (F12) for error messages
3. Consider using server version

---

### ⚖️ Disclaimer

This tool is only for querying Opinion.trade public data and does not guarantee data accuracy. Please refer to the official website for trade counts. Using this tool means you agree to assume the risks yourself.

---

## 📦 Version Info

- **Version:** Local Standalone v1.0
- **Release Date:** 2025-12-26
- **File:** `index_local_standalone.html`
- **Size:** ~90KB
- **Requirements:** Modern browser (Chrome/Edge/Firefox recommended)

---

**Made with ❤️ for Opinion.trade Community**
