
# 机票价格提醒工具（支持微信提醒）

本工具利用[携程 API](https://github.com/liangen1/-xiechengjipiao_aip)实时监控机票价格，并在价格变化超过设定值时，通过微信推送通知用户。该工具基于 `pushplus` 实现微信消息推送功能。

> **注意**：本工具仅供个人学习和研究使用，禁止用于商业用途。

## 功能特点

- 支持单程票和往返票的价格监控。
- 实时价格对比，价格变化时自动微信通知提醒。
- 配置简单，支持多日期、多城市监控。

## 快速开始

1. **环境要求**：  
   本工具依赖 `Python 3.6` 及以上版本，推荐在 `Python 3.8` 上运行。

2. **下载代码**：  
   克隆或下载本项目代码，并进入对应的目录：

   ```bash
   git clone https://github.com/davidwushi1145/flightAlert.git
   cd flightAlert
   ```

3. **创建虚拟环境**：  
   使用如下命令创建并激活 Python 虚拟环境：

   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Linux / macOS
   venv\Scripts\activate  # Windows
   ```

4. **安装依赖包**：  
   运行以下命令安装所需依赖包：

   ```bash
   pip install -r requirements.txt
   ```

5. **配置 `config.json` 文件**：  
   根据你的需求编辑 `config.json` 配置文件。详细配置说明见下文。

6. **运行程序**：  
   配置完成后，运行以下命令启动监控程序：

   ```bash
   python flightAlert.py
   ```

## `config.json` 文件配置说明

- `dateToGo`：需要监控的出发日期（日期格式为 `YYYY-MM-DD`）。
- `placeFrom`：出发城市的机场代码（见下方机场代码表）。
- `placeTo`：到达城市的机场代码（见下方机场代码表）。
- `flightWay`：机票类型，单程票用 `OneWay`，往返票用 `Roundtrip`。
- `sleepTime`：查询间隔时间，单位为秒，推荐设置为 `600` 秒（即十分钟查询一次）。
- `priceStep`：价格变化的阈值，当价格变化超过该值时触发微信提醒。
- `SCKEY`：`pushplus` 的 token，详见[pushplus 文档](https://www.pushplus.plus/doc/)获取方法。

### 机场代码对照表

以下是部分常用城市的机场代码：

| 城市   | 机场代码 | 城市   | 机场代码 |
| ------ | -------- | ------ | -------- |
| 北京   | BJS      | 上海   | SHA      |
| 广州   | CAN      | 深圳   | SZX      |
| 成都   | CTU      | 杭州   | HGH      |
| 武汉   | WUH      | 西安   | SIA      |
| 重庆   | CKG      | 青岛   | TAO      |
| 长沙   | CSX      | 南京   | NKG      |
| 厦门   | XMN      | 昆明   | KMG      |
| 济南   | TNA      | 福州   | FOC      |
| 南昌   | KHN      | 厦门   | XMN      |

更多城市机场代码请参见[完整列表](https://www.iata.org/en/publications/directories/code-search/).

## 注意事项

- 建议监控的日期不要设置太长或已经过期的日期，以免无法获取机票信息。
- `pushplus` 微信推送功能需要在 `pushplus` 平台上注册并获取 `SCKEY`。

## 参考项目

- 本工具改进自 [flightAlert](https://github.com/omegatao/flightAlert)

## 版权声明

本程序仅供个人学习研究，禁止用于商业用途。请尊重版权，不得将本工具用于任何违反相关法律法规的行为。

