---
title: OneEntity
order: 1
---

:::info{title=提示}
OneEntity相较于Entity损耗性能更大，且更适用于对单一实体精细调整使用。
:::

## <center>对象参数</center>

|       参数名        |数据类型|                  说明                  |
|:----------------:|:-:|:------------------------------------:|
|     EntityId     |str|                 实体Id                 |
| IsLogging |bool|          是否输出常规日志，默认为False           |


## <center>流式索引</center>

|                    属性/方法                    |<div style="width: 3.5em">端</div>|  类型   |       描述      | 可修改 |
|:-------------------------------------------:|:-:|:-----:|:-------------:|:---:|
|              [Health](#health)              |<font color=red>服务端</font>| float |     实体生命值     |  ✅  |
|               [Speed](#speed)               |<font color=red>服务端</font>| float |      实体速度     |  ✅  |
|            [Position](#position)            |<font color=red>服务端</font>| tuple |     实体坐标位置    |  ✅  |
|            [Rotation](#Rotation)            |<font color=red>服务端</font>| tuple |     实体旋转角度    |  ✅  |
|              [Damage](#damage)              |<font color=red>服务端</font>| float |     实体攻击力     |  ✅  |
|         [Family](#Family)         |<font color=red>服务端</font>|  list[str]  | 实体类型的type_family列表，例['cow', 'mob']，仅可读 |  ❌  |
|         [ChineseName](#chinesename)         |<font color=red>服务端</font>|  str  | 实体类型的中文名称，仅可读 |  ❌  |
|          [CustomName](#customname)          |<font color=red>服务端</font>|  str  |    实体自定义名称    |  ✅  |
|          [EffectList](#effectlist)          |<font color=red>服务端</font>| list  |    实体药水效果列表   |  ✅  |
|               [Scale](#scale)               |<font color=red>服务端</font>| float |     实体缩放倍率    |  ✅  |
|                [Size](#size)                |<font color=red>服务端</font>| tuple |    实体碰撞盒大小    |  ✅  |
|              [IsFire](#isfire)              |<font color=red>服务端</font>| bool  |    是否处于着火状态   |  ✅  |
|           [MaxHealth](#maxhealth)           |<font color=red>服务端</font>| float |    实体最大生命值    |  ✅  |
|         [BossName](#bossname)            |<font color=red>服务端</font>|  str  |  实体 Boss 血条名称 |  ✅  |
|           [BossRange](#bossrange)           |<font color=red>服务端</font>|  int  | 实体Boss血条显示范围格数 |  ✅  |
|     [UnderWaterSpeed](#underwaterspeed)     |<font color=red>服务端</font>| float |     实体水下速度    |  ✅  |
|              [Hunger](#hunger)              |<font color=red>服务端</font>| float |     实体饥饿值     |  ✅  |
|          [Saturation](#saturation)          |<font color=red>服务端</font>| float |     实体饱和值     |  ✅  |
|          [Absorption](#absorption)          |<font color=red>服务端</font>| float |    实体伤害吸收值    |  ✅  |
|           [LavaSpeed](#lavaspeed)           |<font color=red>服务端</font>| float |    实体岩浆移动速度   |  ✅  |
|                [Luck](#luck)                |<font color=red>服务端</font>| float |     实体幸运值     |  ✅  |
|         [FollowRange](#followrange)         |<font color=red>服务端</font>| float |     实体跟随距离    |  ✅  |
| [KnockBackResistance](#knockbackresistance) |<font color=red>服务端</font>| float |    实体抗击退系数    |  ✅  |
|        [JumpStrength](#jumpstrength)        |<font color=red>服务端</font>| float |    实体跳跃强度    |  ✅  |
|               [Armor](#armor)               |<font color=red>服务端</font>| float |    实体护甲值    |  ✅  |
|               [AI](#AI)               |<font color=red>服务端</font>| bool |    是否屏蔽实体原生AI    |  ✅  |
|                [Name](#name)                |<font color=red>服务端</font>|  str  |    实体名称，如minecraft:zombie    |  ❌  |
|         [DimensionId](#dimensionid)         |<font color=red>服务端</font>|  int  |    实体所在维度    |  ❌  |
|             [OwnerId](#ownerid)             |<font color=red>服务端</font>|  str  |    实体主人Id    |  ❌  |
|             [RiderId](#RiderId)             |<font color=red>服务端</font>|  str  |    实体所骑乘的实体Id    |  ❌  |
|             [BeRiderIdList](#BeRiderIdList)             |<font color=red>服务端</font>|  list[str]  |    实体被其他实体骑乘的实体列表Id    |  ❌  |
|            [TargetId](#targetid)            |<font color=red>服务端</font>|  str  |    实体目标Id    |  ✅  |

------------

### <a id="health"></a>Health
<font color=red>服务端</font><br>

- 描述<br>
实体生命值

- 类型
float

- 示例
```
entity = LASystem.OneEntity(EntityId)
currentHealth = entity.Health
entity.Health = 40.0
```
------------

### <a id="speed"></a>Speed
<font color=red>服务端</font><br>

- 描述<br>
实体速度

- 类型
float

- 示例
无
------------

### <a id="position"></a>Position
<font color=red>服务端</font><br>

- 描述<br>
实体世界坐标位置，三维坐标元组

- 类型
tuple (x, y, z)

  ||数据类型|说明|
  |:-:|:-:|:-:|
  |x|float|X坐标|
  |y|float|Y坐标|
  |z|float|Z坐标|

- 示例

```python
player = LASystem.OneEntity(EntityId)
newPos = (100, 65, 200)
player.Position = newPos
```
------------

### <a id="Rotation"></a>Rotation
<font color=red>服务端</font><br>

- 描述<br>
实体旋转角度，二维坐标元组。单位是角度而不是弧度。

- 类型
tuple (x, y)

  ||数据类型|说明|
  |:-:|:-:|:-:|
  |x|float|上下角度|
  |y|float|左右角度|

- 示例

```python
player = LASystem.OneEntity(EntityId)
player.Rotation = (0, 0)
```
------------

### <a id="damage"></a>Damage
<font color=red>服务端</font><br>

- 描述<br>
实体攻击力

- 类型
float

- 示例

```python
mob = LASystem.OneEntity(MobId)
mob.Damage = 10.0
```
------------

### <a id="Family"></a>Family
<font color=red>服务端</font><br>

- 描述<br>
实体类型的type_family列表，例['cow', 'mob']，仅可读

- 类型
list[str]

- 示例

```python
print(LASystem.OneEntity(EntityId).Family)
```
------------

### <a id="chinesename"></a>ChineseName
<font color=red>服务端</font><br>

- 描述<br>
获取实体的中文名称，仅可读

- 类型
str

- 示例

```python
print(LASystem.OneEntity(EntityId).ChineseName)
```
------------

### <a id="customname"></a>CustomName
<font color=red>服务端</font><br>

- 描述<br>
实体自定义名称（不是 EntityName）

- 类型
str

- 示例

```python
ent = LASystem.OneEntity(EntityId)
ent.CustomName = "神秘之影"
```
------------

### <a id="effectlist"></a>EffectList
<font color=red>服务端</font><br>

- 描述<br>
实体药水效果列表，会产生覆盖。

- 类型
list(dict)
- dict样式

  |key|数据类型|说明|
  |:-:|:-:|:-:|
  |effectName|str|药水效果名称|
  |duration|int|药水效果持续时间，默认为10秒|
  |amplifier|int|药水效果等级，默认为0级|
  |showParticles|bool|是否显示药水效果例子，默认为True|

- 示例

```python
Entity = LASystem.OneEntity(EntityId)
Entity.EffectList = [{
    'effectName': 'speed',
    'duration': 30,
    'amplifier': 0,
    'showParticles': False
}]
```
------------

### <a id="scale"></a>Scale
<font color=red>服务端</font><br>

- 描述<br>
实体缩放体积倍率

- 类型
float

- 示例

```python
LASystem.OneEntity(EntityId).Scale = 2.0
```
------------

### <a id="size"></a>Size
<font color=red>服务端</font><br>

- 描述<br>
实体碰撞盒尺寸宽高，单位为格，元组格式。

- 类型
tuple (width, height)

  ||数据类型|说明|
  |:-:|:-:|:-:|
  |width|float|宽|
  |height|float|高|

- 示例

```python
size = LASystem.OneEntity(EntityId).Size
```
------------

### <a id="isfire"></a>IsFire
<font color=red>服务端</font><br>

- 描述<br>
实体是否处于着火状态（True / False），支持读写。

- 类型
bool

- 示例

```python
LASystem.OneEntity(EntityId).IsFire = True
```
------------

### <a id="maxhealth"></a>MaxHealth
<font color=red>服务端</font><br>

- 描述<br>
实体的最大生命值，支持读写。

- 类型
float

- 示例

```python
LASystem.OneEntity(EntityId).MaxHealth = 200
```
------------

### <a id="bossname"></a>BossName
<font color=red>服务端</font><br>

- 描述<br>
Boss 血条名称，None的时候删除

- 类型
str, None

- 示例

```python
Boss = LASystem.OneEntity(BossEntity)
Boss.BossName = "最终审判者"
```
------------

### <a id="bossrange"></a>BossRange
<font color=red>服务端</font><br>

- 描述<br>
实体Boss血条显示范围格数

- 类型
int

- 示例
无
------------

### <a id="underwaterspeed"></a>UnderWaterSpeed
<font color=red>服务端</font><br>

- 描述<br>
实体水下速度

- 类型
float

- 示例
无
------------

### <a id="hunger"></a>Hunger
<font color=red>服务端</font><br>

- 描述<br>
实体饥饿值

- 类型
float

- 示例
无
------------

### <a id="saturation"></a>Saturation
<font color=red>服务端</font><br>

- 描述<br>
实体饱和值

- 类型
float

- 示例
无
------------

### <a id="saturation"></a>Absorption
<font color=red>服务端</font><br>

- 描述<br>
实体伤害吸收值

- 类型
float

- 示例
无
------------

### <a id="lavaspeed"></a>LavaSpeed
<font color=red>服务端</font><br>

- 描述<br>
实体岩浆移动速度

- 类型
float

- 示例
无
------------

### <a id="luck"></a>Luck
<font color=red>服务端</font><br>

- 描述<br>
实体幸运值

- 类型
float

- 示例
无
------------

### <a id="followrange"></a>FollowRange
<font color=red>服务端</font><br>

- 描述<br>
实体跟随距离

- 类型
float

- 示例
无
--------------

### <a id="knockbackresistance"></a>KnockBackResistance
<font color=red>服务端</font><br>

- 描述<br>
实体抗击退系数

- 类型
float

- 示例
无
--------------

### <a id="jumpstrength"></a>JumpStrength
<font color=red>服务端</font><br>

- 描述<br>
实体跳跃强度

- 类型
float

- 示例
无
--------------
### <a id="armor"></a>Armor
<font color=red>服务端</font><br>

- 描述<br>
实体护甲值

- 类型
float

- 示例
无
--------------
### <a id="AI"></a>AI
<font color=red>服务端</font><br>

- 描述<br>
是否屏蔽实体原生AI<br>
设置时，需要为list[bool, bool]，第一个代表是否保留AI，False为屏蔽，第二个代表屏蔽AI时是否冻结动作，默认为False，仅当isBlock为False时生效。重进世界会恢复成初始动作

- 类型
bool

- 示例
无
--------------
### <a id="name"></a>Name
<font color=red>服务端</font><br>

- 描述<br>
实体名称，如minecraft:zombie(无法更改)

- 类型
str

- 示例
无
--------------
### <a id="dimensionid"></a>DimensionId
<font color=red>服务端</font><br>

- 描述<br>
实体所在维度(无法更改)

- 类型
int

- 示例
无
--------------
### <a id="ownerid"></a>OwnerId
<font color=red>服务端</font><br>

- 描述<br>
实体主人Id(无法更改)

- 类型
str

- 示例
--------------
### <a id="RiderId"></a>RiderId
<font color=red>服务端</font><br>

- 描述<br>
实体所骑乘的实体Id(无法更改)

- 类型
str

- 示例
--------------
### <a id="BeRiderIdList"></a>BeRiderIdList
<font color=red>服务端</font><br>

- 描述<br>
实体被其他实体骑乘的实体列表Id(无法更改)

- 类型
list[str]

- 示例
无
--------------
### <a id="targetid"></a>TargetId
<font color=red>服务端</font><br>

- 描述<br>
实体目标Id

- 类型
str

- 示例
无
--------------