ERI parsing definition file
===========================

Version Info
------------
AUGUST 22, 2015 ver01

[TOC]

Commands that can be parsed
===========================

Get_DC_Power_Voltage_Current
--------
- Command name: `Get_DC_Power_Voltage_Current`
- Command to send: `get dc_power 100`
```
DC power input = {{power}} W ({{voltage}}V x {{current}}A)
```

Get_Inverter_Power_Voltage_Current
--------
- Command name: `Get_Inverter_Power_Voltage_Current`
- Command to send: `wct dc_power 10`
```
Inverter DC power input = {{power}} W ({{voltage}}V x {{current}}A)
```

Get_Inverter_Power_Voltage_Current_2
--------
- Command name: `Get_Inverter_Power_Voltage_Current_2`
- Command to send: `get inv_input_power`
```
{{ANYTHING}}DC Inverter input power = {{power}} W ({{voltage}}V x {{current}}A)
```


Temperature_and_humidity
---------------------
 - Command name : `Temperature_and_humidity`
 - Command to send : `read\n`

```
{{res}}
```

Fsn
---------------------
 - Command name : `fsn`
 - Command to send : `[FSN]`
```
<fsn-{{fsn}}>
```


Get_Ginger_temperatrue
--------
- Command name: `Get_Ginger_temperatrue`
- Command to send: `get temp`
```
Internal Temperature {{tx_board_temp}}ºC
External Temperature {{external_temp}}ºC
```
