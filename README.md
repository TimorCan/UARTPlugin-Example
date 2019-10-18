# UARTPlugin-Example
UARTPlugin使用示例


## launch_plugin_
```
 Atlas.launch_plugin(unit, "AtlasPluginLibrary", "UART", "Uart", {
"parseFiles": [
]()"/Library/Atlas/Resources/parseDefinitions/CrowTemphum.md"
]})
```


## 使用
```
 //open 参数
 params = {
 "uartPortURL":"uart:///dev/cu.usbmodem14101",
 "baudRate":9600,
 "stringToSendOnOpen":""
 } 
 

 Atlas.execute_test("Dut - open", Atlas.call_plugin, "Uart", "open", params)  onError e -> finishWithError(e)
 

 //设置结尾符号
 Atlas.execute_test("Dut - changeDelimiter", Atlas.call_plugin, "Uart", "changeDelimiter",{"delimiter":">"})  onError e -> finishWithError(e)
 
 //发送命令
 output=Atlas.execute_test("Dut - sendCommand", Atlas.call_plugin, "Uart", "sendCommand", {"timeout":5, "parseCommand":"fsn"})  onError e -> finishWithError(e)
 Atlas.Log.info("output is1:" + represent(output))
 
 //{“__regex_metadata__":{"length":23.000000, "location":0.000000, "matchedPattern":"\<fsn-DLC904400APLNWK1Z\>", "regex":"\<fsn-(.*)\>"}, "fsn":"DLC904400APLNWK1Z"}

 sn = output["fsn"]()

 Atlas.Log.info("sn is ---->" + sn)


//关闭Uart
Atlas.execute_test("Dut - close", Atlas.call_plugin, "Uart", "close")  onError e -> finishWithError(e)
```

# md 定义
```
Fsn
---- -----------------
 - Command name : `fsn`  //命令名字
 - Command to send : `[FSN]` //具体发送的命令
\```
<fsn-{{fsn}}>
\```
````


