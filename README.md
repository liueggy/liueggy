# LiuEggy

> 机械工程背景的机器人与嵌入式开发者，正在把硬件、ROS、云端服务和前端控制台连接成真正可运行的系统。

<p align="left">
  <a href="https://liueggy.live">
    <img src="https://img.shields.io/badge/Website-liueggy.live-1677ff?style=for-the-badge&logo=google-chrome&logoColor=white" />
  </a>
  <a href="https://github.com/liueggy">
    <img src="https://img.shields.io/badge/GitHub-liueggy-181717?style=for-the-badge&logo=github" />
  </a>
</p>

---

## 关于我

我是一名机械工程专业学生，也是一名偏工程实践型的嵌入式与机器人开发者。

相比只停留在单个模块，我更关注**系统能不能真正跑起来**：

- 从 STM32 底盘控制、串口协议、传感器接入，到 ROS 节点开发；
- 从 RPLIDAR、IMU、里程计数据，到建图、定位、运动控制；
- 从 Firefly Linux 主板，到云服务器中转、WebSocket、HTTPS、前端控制台；
- 从本地调试，到 systemd 自启、日志、数据保存、远程运维。

我的当前定位是：

> **机器人 / 嵌入式 / 云端控制台方向的工程型开发者**  
> 用机械背景理解真实设备，用软件能力把系统做成可部署、可调试、可迭代的产品原型。

---

## 当前重点方向

### 🤖 ROS 机器人系统

正在开发一台基于 Firefly 控制主板的麦克纳姆轮 ROS 小车：

- ROS Noetic 工作空间搭建与维护
- STM32 底盘串口协议解析与 C++ 驱动开发
- RPLIDAR A1 激光雷达接入与方向标定
- 外接十轴 IMU 驱动、TF 外参配置与闭环旋转控制
- `/cmd_vel`、`/odom`、`/scan`、`/tf`、`/map` 等核心话题联调
- `gmapping` 建图、地图保存、rosbag 数据采集
- 基于 systemd/tmux 的机器人后台运行与运维脚本

### 🔧 嵌入式与硬件控制

- STM32 / FreeRTOS / 串口通信 / 底层驱动
- 传感器数据采集与协议解析
- 运动控制、里程计、IMU 姿态数据处理
- 多模块硬件系统集成与问题定位

### 🌐 云端中继与远程控制

最近完成了一个真实可用的三点式机器人远程控制链路：

```text
Web / App Client
  ⇄ HTTPS / WebSocket
Cloud Relay Server
  ⇄ WebSocket
Robot Agent
  ⇄ rosbridge
ROS / Hardware
```

当前公网入口：

```text
https://liueggy.live
```

涉及能力：

- FastAPI / WebSocket 中转服务
- Robot Agent 数据采集与命令转发
- Nginx 反向代理与 HTTPS 证书配置
- DigitalOcean Linux 服务器部署与 systemd 服务管理
- 前端实时状态、地图、诊断、日志与手动遥控页面

### 🖥️ 前端与工程工具

我也在做一些面向工程效率的工具和控制台：

- React + TypeScript + Ant Design 控制台
- 机器人状态可视化、地图画布、话题诊断、日志面板
- STM32 代码生成工具 / 工程辅助工具
- 个人网站与技术文档平台

---

## 技术栈

### Languages

![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=flat-square&logo=swift&logoColor=white)

### Robotics / Embedded

![ROS](https://img.shields.io/badge/ROS-Noetic-22314E?style=flat-square&logo=ros&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-03234B?style=flat-square&logo=stmicroelectronics&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white)

### Web / Cloud / Tools

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

---

## 代表项目

### 🤖 Firefly ROS 麦克纳姆轮小车

一个从硬件到底层驱动、从 ROS 到云端控制台的完整机器人项目。

已完成：

- STM32 底盘驱动与串口协议适配
- RPLIDAR A1、外接 IMU、里程计数据接入
- IMU 闭环旋转、指定距离前进控制
- `gmapping` 建图与地图保存
- 机器人端 systemd 自启栈
- 云服务器中继与 Web 控制台
- rosbag 手动录制与数据管理

项目特点：不是只写 Demo，而是持续解决真实设备中的电源、网络、串口、进程残留、日志、数据堆积和远程运维问题。

### 🌐 ROS Cloud Relay / Robot Console

公网远程控制与监控系统：

- 云端 relay：App/Web ⇄ Robot
- Robot Agent：rosbridge ⇄ cloud relay
- 前端：React + Ant Design 实时控制台
- HTTPS 域名：`liueggy.live`
- 支持 Lite / Map 数据模式，避免大地图数据导致连接不稳定

### 🔧 STM32 Code Weaver

基于 Web 的 STM32 嵌入式系统代码生成工具。

目标是把常见外设配置、工程模板和代码规范沉淀成可复用工具，降低重复劳动，提高嵌入式开发效率。

### 🗑️ 智能垃圾分类系统

基于 STM32F103ZET6 的嵌入式控制系统，完成传感器数据采集、多模块协同控制和自动分类逻辑，是我早期嵌入式工程实践之一。

### 🧠 AI Vision / K230 探索

关注边缘 AI 与视觉应用，包括目标检测、图像识别、K230 AI SoC 应用开发等方向。

---

## 我重视的工程能力

- **能跑起来**：硬件、驱动、系统、网络、前端要形成闭环。
- **能定位问题**：日志、话题、进程、串口、网络链路都要可检查。
- **能长期维护**：systemd、自启策略、数据目录、清理命令、README 都要写清楚。
- **能持续迭代**：先做 MVP，再逐步优化性能、稳定性和体验。

---

## 近期计划

- 完善 ROS 小车的定位与导航闭环：`map_server + amcl + move_base`
- 优化 Web 控制台的地图显示、驾驶体验和诊断信息
- 将机器人项目整理成更规范的开源/展示仓库
- 继续沉淀 STM32 与机器人开发工具链
- 探索 K230 / 边缘 AI 与移动机器人结合的应用

---

## 联系我

- Website: [liueggy.live](https://liueggy.live)
- GitHub: [github.com/liueggy](https://github.com/liueggy)

---

<p align="center">
  <strong>从机械结构到嵌入式控制，从 ROS 到云端控制台，把想法做成真正运行的系统。</strong>
</p>
