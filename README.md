# Goark RabbitMQ

Goark RabbitMQ 是 Goark 生态的 RabbitMQ 集成模块，目标是提供 exchange、queue、binding、publisher、consumer 和确认语义的 Go 原生边界。

## 当前状态

本仓库已完成基础工程初始化，当前尚未承诺稳定公共 API。后续实现应按小步提交推进，每次功能变更都需要对应的 Go 测试或清晰的验证记录。

## 模块路径

```text
module github.com/goark-projects/goark-rabbitmq
```

## 规划边界

- exchange、queue、binding 和 routing key 抽象
- publisher confirm、consumer ack/nack、重试和死信边界
- TLS、认证、连接恢复和可观测插件
- 与 Goark 应用生命周期、配置和错误模型对齐

## 非目标

- 不在仓库初始化阶段实现完整 RabbitMQ 客户端封装
- 不引入 Java 风格运行时扫描、代理或复杂注解模型

## 快速检查

```bash
go test ./...
go vet ./...
```

## 工程约定

- Go 版本跟随 Goark 生态主线，当前模块声明为 `go 1.25`。
- 代码、脚本、配置和文档统一使用 UTF-8 与 LF。
- Go 代码注释使用标准简体中文，只解释非显而易见的设计意图、边界和失败语义。
- 公共 API 优先显式接口、小结构体和可组合选项，不使用 Java 风格运行时扫描或重代理模型。
- 功能实现必须包含边界条件、错误处理、上下文取消和并发安全复核。

## 许可证

本项目使用 Apache License 2.0。