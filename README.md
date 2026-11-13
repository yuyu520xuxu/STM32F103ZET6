# STM32F103ZET6 Blank Template (EIDE)

这是一个基于 **STM32F103ZET6** (Cortex-M3 大容量系列) 的空白工程模板，使用标准外设库 (Standard Peripheral Library) 编写，专为 VS Code + EIDE 开发环境配置。

## 🛠️ 开发环境

- **编写与编译**：VS Code + EIDE (Embedded IDE) 插件
- **编译器**：ARM GNU Toolchain (arm-none-eabi-gcc)
- **烧录工具**：Keil MDK (通过 ST-Link 或 CMSIS-DAP 烧录)
  *(注：由于部分 WCH-Link 探针与 OpenOCD 0.12 存在兼容性问题，本模板推荐在 VS Code 中完成编译，随后使用 Keil 软件下载 `.hex` 文件)*

## ⚙️ 工程配置说明

针对 `STM32F103ZET6` 大容量芯片，关键配置已预先设定完成：
- **全局宏定义**：`STM32F10X_HD` 和 `USE_STDPERIPH_DRIVER`
- **链接脚本**：`STM32F103ZETX_FLASH.ld`（已修正路径，正确识别 512KB Flash 和 64KB RAM）
- **启动文件**：`startup_stm32f10x_hd.s`（GCC 版本，大容量专用）

## 📂 目录结构

- `Libraries/`：STM32 标准外设库文件
- `Start/`：核心文件及 GCC 启动文件
- `User/`：用户代码区 (`main.c`, `stm32f10x_it.c` 等)
- `STM32F103ZET6/`：EIDE 工程配置文件夹 (包含 `.eide`, `.vscode` 及 `.ld` 文件)
- `.gitignore`：Git 忽略文件配置（已过滤 `build/` 和 `.pack/` 等编译缓存）

## 🚀 如何使用

1. 克隆本仓库到本地：
   ```bash
   git clone https://github.com/yuyu520xuxu/STM32F103ZET6.git
