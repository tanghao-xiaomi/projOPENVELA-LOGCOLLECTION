# projOPENVELA-LOGCOLLECTION

## 项目背景

[openvela](https://github.com/open-vela/docs/blob/dev/README_zh-cn.md) 操作系统专为 AIoT 领域量身定制，以轻量化、标准兼容、安全性和高度可扩展性为核心特点。openvela 以其卓越的技术优势，已成为众多物联网设备和 AI 硬件的技术首选，涵盖了智能手表、运动手环、智能音箱、耳机、智能家居设备以及机器人等多个领域。

嵌入式设备通常需定期采集数据并记录存储，同时支持任务并发处理。请基于 openvela 实时操作系统，实现一个定时任务采集系统。通过本项目，可锻炼学生对线程、定时器及文件系统的综合应用能力。

## 导师信息

张晓伟 zhangxiaowei16@xiaomi.com

## 难度

中

## 分类

系统维护工具

## 项目描述

请你基于 openvela 操作系统，完成一个简单的定时采集日志系统，实现以下功能：

1. 创建两个独立线程（任务）：
   1. 采集任务：在定时器触发下，将模拟采集数据（如递增数字或时间戳）写入文件。
   2. 读取任务：定时从文件中读取采集的数据并输出到串口或终端。
2. 配置并使用软件定时器，周期性触发采集任务执行。
3. 实现文件写操作和读操作，保证文件完整以及线程安全。
4. 在系统启动后，两个任务并发运行，采集数据持续写入文件，读取任务定时打印文件内容。

## 功能细节要求

- 线程
  - 采集线程挂起等待定时器触发信号（信号量或消息队列等方式）；
  - 读取线程周期性唤醒，读取文件数据，输出日志。
- 定时器
  - 软件定时器周期时间可配置（如 1 秒或 5 秒）。
  - 定时器回调函数向采集线程发送执行信号。
- 文件系统
  - 文件名固定（例如 /data/log.txt）。
  - 写入模式追加写入采集数据，每条数据后包含时间戳或序号。
  - 读取模式读取整个文件内容并打印。

## 评测点

- 线程创建及切换正确性；
- 定时器触发准确；
- 文件读写正常且无数据混乱；
- 程序稳定执行，能持续写入和读取；
- 代码规范及注释清晰。

## 所属赛道

2025年全国大学生操作系统比赛的“OS功能挑战”赛道

## 参考资料

- 源码地址：[Github](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2Fopen-vela)
- 文档地址：[GitHub docs](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2Fopen-vela%2Fdocs)
- 代码贡献指南：[GitHub](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2Fopen-vela%2Fdocs%2Fblob%2Fdev%2FCONTRIBUTING.md)
- 文档贡献指南：[GitHub](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2Fopen-vela%2Fdocs%2Fblob%2Ftrunk%2Fzh-cn%2Fcontribute%2Fprocess%2Fdoc_dev_process.md)
