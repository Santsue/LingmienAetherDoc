---
title: Molang
order: 13
---

## <center>索引</center>

|接口|<div style="width: 3.5em">端</div>|描述|
|:-:|:-:|:-:|
|[QueryInit](#queryinit)|<font color=blue>客户端</font>|自定义Molang注册并创建|
|[QueryGet](#queryget)|<font color=blue>客户端</font>|获取自定义Molang函数的值|
|[QueryMolangGet](#querymolangget)|<font color=blue>客户端</font>|获取原版Molang函数的值|
|[QuerySet](#queryset)|<font color=orange>双端</font>|设置自定义Molang函数的值|
|[QuerySetByData](#QuerySetByData)|<font color=orange>双端</font>|根据Molang数据设置自定义Molang函数的值|

------------
### <a id="queryinit"></a>QueryInit
<font color=blue>客户端</font><br>
- 描述<br>
  自定义Molang注册并创建，需要在客户端事件'OnLocalPlayerStopLoading'下使用

- 参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|PlayerId|str|玩家id|
|QueryName|str|函数名称|
|InitValue|float|函数初始数值|

- 返回值<br>
  无

- 备注<br>
  会自动补全为query.mod.xxx

- 示例
空
------------
### <a id="QueryGet"></a>QueryGet
<font color=blue>客户端</font><br>
- 描述<br>
  获取自定义Molang函数的值

- 参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|QueryName|str|函数名称|
|EntityId|str|查询的实体Id，默认为playerId|

- 返回值<br>
  自定义Molang函数的值(float)

- 备注<br>
  无

- 示例
空
------------

### <a id="QueryMolangGet"></a>QueryMolangGet
<font color=blue>客户端</font><br>
- 描述<br>
  获取原版Molang函数的值

- 参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|QueryName|str|函数名称|

- 返回值<br>
  原版Molang函数的值(float)

- 备注<br>
  无

- 示例
空
------------

### <a id="QuerySet"></a>QuerySet
<font color=orange>双端</font><br>
- 描述<br>
  设置自定义Molang函数的值

- 服务端参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|QueryName|str|函数名称|
|Value|float|对应函数的值|
|EntityId|str|挂载实体Id，玩家使用该Molang则填写该玩家id，实体使用该Molang则填写该实体Id|

- 客户端参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|QueryName|str|函数名称|
|Value|float|对应函数的值|
|EntityId|str|挂载实体Id，默认为None则挂载该客户端玩家|

- 返回值<br>
  无

- 备注<br>
  无

- 示例
空
------------

### <a id="QuerySetByData"></a>QuerySetByData
<font color=orange>双端</font><br>
- 描述<br>
  根据Molang数据设置自定义Molang函数的值

- 服务端参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|args|dict|参数数据，key为MolangData，value放置Molang数据|

- 客户端参数

|参数名|数据类型|说明|
|:-:|:-:|:-:|
|MolangData|dict|Molang数据|
|IsBroadcast|bool|是否广播到其他玩家，默认True|

- 返回值<br>
  无

- 备注<br>
  - Molang数据类型，Key为实体Id，Value为Key为Molang变量名(简写)，Value为Molang变量值的字典。例如：
        
  ```python
  MolangData = {
      playerId : {
          'la_vehicle_position_x': -offset_x * 16 * Scale,
          'la_vehicle_position_y': offset_y * 16 * Scale,
          'la_vehicle_position_z': -offset_z * 16 * Scale,
          'la_vehicle_rotation_z': RotationValueZ,
          'la_vehicle_rotation_x': RotationValueX,
          'la_vehicle_rotation_y': RotationValueY,
      }
  }
  ```

- 示例
空
------------