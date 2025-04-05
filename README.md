# Swagger-Hack

一个用于自动化测试 Swagger API 接口的安全工具。

> 本项目基于 [jayus0821/swagger-hack](https://github.com/jayus0821/swagger-hack) 进行改进，增加了代理功能支持。

## 项目简介

Swagger-Hack 是一个专门用于测试 Swagger API 文档安全性的工具。它能够自动解析 Swagger 文档，构造并发送各种类型的 HTTP 请求，帮助安全研究人员和开发人员发现 API 接口中的潜在安全问题。

## 改进功能

- 增加了代理功能支持，可以通过 `-p` 或 `--proxy` 参数指定代理服务器
- 支持 HTTP/HTTPS 代理
- 优化了代理配置的处理逻辑

## 功能特点

- 支持多种 Swagger 文档格式的解析
- 自动构造并发送 GET、POST、PUT、DELETE 等类型的请求
- 支持路径参数、查询参数和请求体参数的自动填充
- 多进程并发处理，提高测试效率
- 详细的请求日志记录
- 支持代理设置
- 结果导出为 CSV 格式

## 安装说明

1. 克隆项目到本地：
```bash
git clone https://github.com/yourusername/swagger-hack.git
cd swagger-hack
```

2. 安装依赖：
```bash
pip install -r requirements.txt
```

## 使用方法

基本用法：
```bash
python swagger-hack2.0.py -u <swagger_url>
```

参数说明：
- `-u, --url`: Swagger 文档的 URL 地址
- `-p, --proxy`: 代理服务器地址（可选，支持 HTTP/HTTPS 代理）
- `-o, --output`: 输出文件名（可选，默认为 results.csv）

示例：
```bash
# 基本使用
python swagger-hack2.0.py -u http://example.com/swagger-ui.html

# 使用 HTTP 代理
python swagger-hack2.0.py -u http://example.com/swagger-ui.html -p http://127.0.0.1:8080

# 使用 HTTPS 代理
python swagger-hack2.0.py -u http://example.com/swagger-ui.html -p https://127.0.0.1:8080

# 指定输出文件
python swagger-hack2.0.py -u http://example.com/swagger-ui.html -o my_results.csv
```

## 输出结果

工具会将测试结果保存为 CSV 文件，包含以下信息：
- API 文档 URL
- 接口描述
- 请求路径
- 请求方法
- 完整请求 URL
- 参数数量
- 请求参数
- 响应状态码
- 响应内容

## 注意事项

- 请确保在使用本工具时获得适当的授权
- 建议在测试环境中使用
- 某些 API 可能需要认证信息，请根据实际情况修改代码
- 使用代理时，请确保代理服务器可用且配置正确

## 贡献指南

欢迎提交 Issue 和 Pull Request 来帮助改进项目。

## 许可证

本项目采用 MIT 许可证。详见 [LICENSE](LICENSE) 文件。 
