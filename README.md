# 🚀 Intro 

 

* 说明 
* 测试项目编号说明
* 测试项 



 

<section class="sel" data-key="USB">

## 2. USB

|测试项 | 说明 | 判定标准|
| -------- | ---- | ---- |
| A2C 线供电 | 测量过压保护功能（一般 6V） | 可以供电使用 |
| C2C 线供电 | 双向均需测试 | 可以供电使用 |
| A2C 线通信 | 烧录固件测试 | 可以通信 |
| C2C 线通信 | 双向均需测试 | 可以通信 |
| 带负载能力 | 测量空载电压，最大带负载能力 | 空载 ≤ 5.25V，500mA 时 ≥ 4.75V |

</section>


## 🤑 项目
* SOP
* NPI

## 🤔 硬件
* 开发说明 
	* KiCad
* 方案
	* 电源
	* 电池
	* 接口
		* TypeC
		* HDMI
		* RS485
		* CAN
	* 音频

## 😘 软件

* 规范
* 组件开发 
	* https://gitlab.m5stack.com/embedded-common-components
	* I2C 
	* SENSOR https://github.com/espressif/esp-iot-solution/tree/master/components/sensors

	使用到 I2C 设备的请使用 [i2c_bus](https://github.com/espressif/esp-iot-solution/tree/master/components/i2c_bus) 实现，具体请参考 [sensors](https://github.com/espressif/esp-iot-solution/tree/master/components/sensors) 实现，示例：[充当管理 AW32001]
* 资料
	* 显示屏
		* ST7789
		* ST7102
		* ILI9341
		* ILI9342
		* ILI9881
		* CO5300
		* GC9A01
	* 触摸屏
		* FT6336U
		* GT911
		* [<font color=#00CC66>CST3530</font>](./软件/触摸屏/CST3530.md)
		* CST820
		* CST9217
	* 电源管理
		* AW32001 (充电管理)
		* BQ27220 (电量计)
		* IP2326 (充电管理)
		* AXP192
		* AXP2101
	* MCU
		* ESP32 系列 
			* 芯片资料: https://www.espressif.com/zh-hans/products/socs
			* FAQ: https://docs.espressif.com/projects/esp-faq/zh_CN/latest/index.html
		* STM32
		* PY32
	* 传感器 
		* IMU
			* BMI270 (陀螺仪，加速度计)
				* 通信接口: I2C, 地址: 
			* BMM150 (磁力计)
			* MPU6050 (陀螺仪，加速度计)
			* MPU6886 (陀螺仪，加速度计)
		* 电源管理
		* I/O 扩展
			* PI4IOE5V6408
		* LTR-553ALS (接近传感器)
	* 摄像头
		* OV2640
		* OV3660 
		* OV7740
		* GC0308
	* RTC
		* RX8130CE  
		* BM8563 
	* 音频
		* ES8311 (ADC and DAC)
		* ES8388 (2-ch ADC, 2-ch DAC)
		* ES8389 (ADC and DAC)
		* ES7210 (4-ch ADC)
		* AW88298 (音频放大器)
		* AW87759 (音频放大器)
		* NS4150B
		* NS4168
		* 麦克风
			* SPM1423
		* 扬声器
	* 无线/射频
		* LoRa
			* SX1262
		* 4G
			* ML307R
	* LED
		* WS2812
		* SK6812
	* Others
		* LP6652 
		* INA226
		* SIT3088
		* GL852G (USB Hub)
		* LT8618SX (HDMI)
		* MP8759
		* AW32901 (负载开关)
		* ME1502 (负载开关) 
	* https://doc.weixin.qq.com/sheet/e3_AdcA8QZKAAcCNPvFxrR72RdWbTl84?scode=AGgAFgfmAAkur3oCU8
	* AEC 调试 

## 🔨 测试
* 硬件测试
	* USB
		* TypeA
		* TypeC	
			* 通信测试
			* CC 通道测试
				* CC1, CC2 连接通道测试
			* PD 协议测试 
	* MBUS
	* Grove 端口 
		* 供电电压
		* 带负载能力 
	* DC 端口 
	* 电源
	* 电池
		* 过放
		* 过充
		* 充放电时间
* 功耗测试
* 软件功能测试
* 样品测试
	* 显示屏
		* <font color=#FF0000>液晶屏</font>
			* 背光控制
			* 纯色显示
			* 分辨率
			* 坏点检查
			* 边框显示（检查贴合位置是否对齐）
			* 刷新率测试（高刷新率检查图像是否撕裂）
		* [<font color=#00CC66>墨水屏</font>](./测试/显示屏/墨水屏.md)
	* 触摸屏
		* 触摸坐标读取 --> 画点/线
		* 触摸中断测试
	* 音频
		* 录音，播放 
	* 麦克风
	* 扬声器
	* 传感器
		* IMU
		* 温湿度
	* 无线/射频
		* 发射功率
		* 接收灵敏度
		* 接收信号强度 
		* 拉距测试 
	* SD 卡
		* 兼容性测试 
* M5Stack
	* Module I2C 地址  https://docs.m5stack.com/en/product_i2c_addr
	* Unit I2C 隔离 

## 📝 产测
* 测试项要求
	* 带主控芯片的需要提供出厂固件，用于给用户快速上手体验
	* 接口类
		* Grove 端口
			* 输入 I/O：外接测试治具（读取 ADC 电压，或按键检测）
			* 通用 I/O：外接测试治具控制 LED 闪烁
			* I2C 接口：外接 I2C 设备通信测试 
		* TypeC：需要用 C2C 的 USB 线通信测试
		* CAN：测试治具收发数据包 
		* RS485：测试治具收发数据包
		* 网口
			* 入网，获取 IP 
		* MBUS
			* 外接 MBUS 测试治具，控制 LED 闪烁 
		* TF 卡
			* TF卡容量读取，读/写数据速度测试 
	* 无线/射频 
		* Wi-Fi
			* 连接指定网络，获取信号强度
		* 蓝牙
		* LoRa
			* 射频功率测量
			* 拉距测试（抽样）
		* 4G
			* CSQ 信号强度获取
			* 联网通信测试 
				* TODO： 需要搭建测试服务器
	* GPS
		* 冷启动搜星速度
		* 热启动搜星速度
		* 卫星数量
		* 时间，经纬度获取
	* 显示屏
		* 边框显示（检查屏幕贴合情况）
		* 液晶屏
			* 红绿蓝白黑颜色填充显示
			* 背光亮度控制
		* 墨水屏：全黑，全白显示（检查有无坏点）
	* 触摸屏
		* 触摸坐标获取 (有中断的需要采用中断触发读取数据方式实现)
		* 是否线性 ???
		* 是否偏移 ???
	* 摄像头
		* 
	* 麦克风
		* 暂时为录音播放测试
	* 扬声器
		* 播放音频测试 
	* 蜂鸣器	
		* 特定频率鸣响测试 
	* 按键
	* 电位器
	* 编码器
	* LED 

 
 