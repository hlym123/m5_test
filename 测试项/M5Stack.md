# M5Stack 产品


------------------------------------------
## 主机类 

* 对于 Grove 接口 I/O 与内部 I2C 共用的设计，建议增加 I2C 隔离电路，防止外部 Unit 未上电拉死通信引脚。
* 对于其他直接暴露给用户的接口一般需要测量最大带负载能力，短路保护，反接保护功能。


------------------------------------------
## Module 系列 

* 对于使用到 I2C 的需要确认设备地址，检查与其他堆叠模块和主机相关 I2C 设备地址否有冲突。
* 对于产品元器件超出 Module 外壳的（例如：外接天线）需要考虑 Module 堆叠是否存在干涉。

<table>
  <caption style="caption-side:top; font-weight:bold; text-align:center; margin-bottom:4px;">主机兼容性</caption>
  <tr style="background-color:#00BFFF;">
    <th>测试项</th>
    <th>说明</th>
    <th>判定标准</th>
  </tr>
  <tr>
    <td>Basic</td>
    <td rowspan="7">对于使用拨码开关切换引脚的，应确保每一路I/O都测量到。</td>
    <td>可以正常使用</td>
  </tr>
  <tr>
    <td>Fire</td>
    <td>可以正常使用</td>
  </tr>
  <tr>
    <td>Core2</td>
    <td>可以正常使用</td>
  </tr>
  <tr>
    <td>Core2 v1.1</td>
    <td>可以正常使用</td>
  </tr>
  <tr>
    <td>CoreS3</td>
    <td>可以正常使用</td>
  </tr>
  <tr>
    <td>Tab5</td>
    <td>可以正常使用</td>
  </tr>
  <tr>
    <td>CoreMP135</td>
    <td>可以正常使用</td>
  </tr>
</table>

 

<table>
  <caption style="caption-side:top; font-weight:bold; text-align:center; margin-bottom:4px;">MBUS</caption>
  <tr style="background-color:#00BFFF;">
    <th>测试项</th>
    <th>说明</th>
    <th>判定标准</th>
  </tr>
  <tr>
    <td>I/O连通性</td>
    <td>MBUS I/O 测试治具测试</td>
    <td>对应I/O LED 亮灭可控</td>
  </tr>
  <tr>
    <td>ADC</td>
    <td>对于只能设为输入的引脚，例如Basic 主机的Port.B使用 Grove Port.B 测试治具测试</td>
    <td>可读取到正确的 ADC 值</td>
  </tr>
  <tr>
    <td>5V供电</td>
    <td>万用表测量3.3V供电引脚</td>
    <td>可测量到3.3V电压</td>
  </tr>
  <tr>
    <td>3.3V 供电</td>
    <td>万用表测量5V供电引脚</td>
    <td>可测量到5V电压</td>
  </tr>
  <tr>
    <td>VBAT 供电</td>
    <td>堆叠控制器和待测试Module，使用电池底座供电测试</td>
    <td>可以使用电池底座供电</td>
  </tr>
</table>


 