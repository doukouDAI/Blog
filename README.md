- [FGUI](#fgui)
- [制品管理](#制品管理)
  - [出包](#出包)
  - [Andriod](#andriod)
  - [IOS](#ios)
- [配置](#配置)
  - [游戏配置](#游戏配置)
    - [资源加载模式](#资源加载模式)
    - [打包参数](#打包参数)
    - [默认多语言配置](#默认多语言配置)
    - [网络通信参数](#网络通信参数)
  - [策划配置](#策划配置)
- [美术资源](#美术资源)
- [C#层](#c层)
  - [功能](#功能)
    - [入口（`Entrance`)](#入口entrance)
      - [初始化](#初始化)
      - [驱动Lua入口(core/entrance)](#驱动lua入口coreentrance)
    - [多语言（Language）](#多语言language)
      - [说明](#说明)
      - [API](#api)
    - [Lua（`LuaManager`）](#lualuamanager)
      - [说明](#说明-1)
      - [API](#api-1)
    - [场景](#场景)
      - [说明](#说明-2)
      - [API](#api-2)
    - [本地存储](#本地存储)
      - [说明](#说明-3)
      - [API](#api-3)
  - [资源](#资源)
    - [资源打包](#资源打包)
    - [资源导入](#资源导入)
    - [资源管理](#资源管理)
      - [内部资源](#内部资源)
      - [外部资源](#外部资源)
    - [资源加载（`AssetLoader`）](#资源加载assetloader)
      - [说明](#说明-4)
      - [API](#api-4)
    - [资源更新](#资源更新)
      - [版本管理](#版本管理)
      - [更新流程](#更新流程)
    - [资源下载](#资源下载)
      - [说明](#说明-5)
      - [API](#api-5)
  - [网络](#网络)
    - [Soket（`H2WebSocketClient`、`LSClient`、`GSClient`）](#soketh2websocketclientlsclientgsclient)
      - [说明](#说明-6)
    - [字节流（`ALProtocolCommon`）](#字节流alprotocolcommon)
      - [说明](#说明-7)
      - [接口](#接口)
  - [UI](#ui)
    - [加载](#加载)
    - [初始化](#初始化-1)
      - [Lua动态绑定 (GComponent)](#lua动态绑定-gcomponent)
  - [ThirdPart](#thirdpart)
    - [WebSocket](#websocket)
    - [XLua](#xlua)
    - [FlatBuffer](#flatbuffer)
    - [ZString](#zstring)
    - [LitJoson](#litjoson)
    - [FGUI](#fgui-1)
    - [Spine](#spine)
    - [SQLite](#sqlite)
- [Lua层](#lua层)
  - [功能](#功能-1)
    - [入口](#入口)
      - [说明](#说明-8)
    - [驱动(`loops`)](#驱动loops)
      - [说明](#说明-9)
      - [API](#api-6)
    - [事件(`MessageManager`)](#事件messagemanager)
      - [说明](#说明-10)
      - [API](#api-7)
    - [场景(`unitySceneManager`)](#场景unityscenemanager)
      - [说明](#说明-11)
      - [流程](#流程)
      - [API](#api-8)
    - [SDK](#sdk)
      - [说明](#说明-12)
      - [API](#api-9)
    - [本地存储](#本地存储-1)
      - [说明](#说明-13)
    - [类（`class`）](#类class)
      - [说明](#说明-14)
      - [API](#api-10)
    - [协程(`LuaCoroutine`)](#协程luacoroutine)
      - [说明](#说明-15)
      - [API](#api-11)
    - [模块](#模块)
      - [说明](#说明-16)
      - [API](#api-12)
  - [网络](#网络-1)
    - [协议](#协议)
      - [结构](#结构)
      - [编码](#编码)
      - [透传协议](#透传协议)
      - [会话流程](#会话流程)
    - [登录服（LS）](#登录服ls)
      - [连接](#连接)
    - [游戏服（GS）](#游戏服gs)
      - [登录](#登录)
  - [资源](#资源-1)
    - [特效](#特效)
      - [说明](#说明-17)
      - [API](#api-13)
    - [音效](#音效)
      - [说明](#说明-18)
      - [API](#api-14)
      - [Sprite](#sprite)
      - [说明](#说明-19)
      - [API](#api-15)
  - [UI](#ui-1)
    - [规则](#规则)
      - [结构](#结构-1)
      - [显示层级](#显示层级)
      - [功能](#功能-2)
      - [打开规则](#打开规则)
      - [关闭规则](#关闭规则)
    - [UI管理（`UIManager`）](#ui管理uimanager)
      - [说明](#说明-20)
      - [轮询](#轮询)
      - [API](#api-16)



# FGUI



# 制品管理

## 出包

## Andriod

## IOS

# 配置

## 游戏配置 

### 资源加载模式

* Resource
* AssetBundle

### 打包参数

* 编译方式（Release、Debug）
* GameID
* 版本号
* 运行平台

### 默认多语言配置 

### 网络通信参数

* 登陆服地址，端口号

## 策划配置

# 美术资源



# C#层

## 功能

### 入口（`Entrance`)

#### 初始化	

* ##### 初始化资源加载器

  * 筛选出内部资源

* ##### 创建新的Lua虚拟机


* ##### ThirdPart

  * ZString（提前开辟内存块）

#### 驱动Lua入口(core/entrance)

------

### 多语言（Language）

#### 说明

* 使用SQLite数据库存储数据
* 采用懒加载的方式读取数据(在数据库中只读取需要的部分然后缓存在内存中)
* 按照参数化读取(format),当复数多语言会自动根据数量匹配适应的语言描述

#### API

* 根据多语言Key获取多语言

  ```c#
  public static string Get(string _key)
  ```

------

### Lua（`LuaManager`）

#### 说明

* ##### 和Lua通信的中间件

* ##### 接口

  * 根据开发平台和环境确定Lua脚本的路径(LuaPath)
  * 提供获取Lua Chunk的操作（LoadFile）
  * 将Lua Chunk注册到当前Lua虚拟机（Require）
  * 在当前Lua虚拟机中生成新的Table（NewTable）
  * 负责 Debug Lua端的协议

#### API

------

### 场景

#### 说明

#### API

------

### 本地存储

#### 说明

#### API

------


## 资源

### 	资源打包

* Bundle包采用增量和ChunkBased压缩的方式
* 计算每一个新版本Bundle文件的CRC校验并序列化为Josn文件
* 拷贝所有新版本的Bundle文件到`streamingAssets`目录下（除了`Manifest`文件）
* 把所有的缓存文件放到资源版本管理库中留存
* 把新老版本的Bundle文件做CRC校验对比，记录差异化文件（新增、修改、这里没有删除）用作后续更新使用

------

### 资源导入

------

### 资源管理

#### 内部资源

* 随包资源，只包括运行所必须的基础内容

#### 外部资源

* 不随包的资源，开启游戏后可以通过热更的方式下载，或者后台下载
* 目前只是按照资源类型区分

------

### 资源加载（`AssetLoader`）

#### 说明

* ##### 加载方式

  * 同步
  * 异步

* ##### 加载器

  * Load
    * 引用计数增加
    * 缓存到记录中稍后可以直接使用

  * Release
    * 引用计数减少
    * 如果引用计数小于一，记录Rlease的时间，存放到没有使用的资源列表中（Unused）

* ##### 自动回收资源

  * 每间隔一个周期自动运行或者外部调用强制运行
  * 检查资源过期的时间是否满足要求
  * 回收所有没有使用的过期资源（RemoveList）

#### API

* 加载本地资源（Load）

  ```c#
  public static AssetLoader Load(string url,
              OnAssetLoadFinished callback = null,
              EnumLoadMode mode = EnumLoadMode.Sync)
  ```

------

### 资源更新

#### 版本管理

* 所有版本的资源都存放在不同归档文件夹中
* 在做新旧版本比对的时候

#### 更新流程

* 记录所有的本地资源

------

### 资源下载

#### 说明

* ##### 原子操作

  * ##### 执行下载任务（`DownloadTask`）

    * 接受下载数据，同时负责传输传输下载的数据
      * 如果数据长度小与接收数据的大小需要做粘包处理
      * 如果数据长度等于节接收数据的大小代表下载成功

    * 下载完成
      * 失败5次下载失败
      * 继续执行其他下载任务

#### API

* 提供远程URL和目标路径下载一个资源（Download）

------

## 网络

### Soket（`H2WebSocketClient`、`LSClient`、`GSClient`）

#### 说明

* 利用WebSocket建立长连接
* 收发数据
* 异常处理
* 推送原始数据到Lua层



### 字节流（`ALProtocolCommon`）

#### 说明

#### 接口

* 读写Byte
* 读写Short
* 读写Int32
* 读写Float
* 读写Long
* 读写Double
* 读写String
* 读写数组Byte

## UI

### 加载

### 初始化

#### Lua动态绑定 (GComponent)

* 在FGUI中除了自动命名的(n10这种形式)都会自动在运行时把组件和控制器绑定到view中,在view中直接获取就可以了

## ThirdPart

### WebSocket

### XLua

### FlatBuffer

### ZString

### LitJoson

### FGUI

### Spine

### SQLite


# Lua层

## 功能

### 入口

#### 说明

* ##### 注册全局工具到环境中(\_ENV.\_G)中

  * C#端相关函数
  * 单例工具

* ##### 全局变量定义专门的chunck（core.globals），而不使用\_ENV.\_G

  * 防止误操作
  * 防止全局引用造成内存泄露

------

### 驱动(`loops`)

#### 说明

* 由C#驱动
* 负责监听并执行Untiy MonoBehaviour周期更新回调Update、LateUpdate、FixedUpdate和application回调函数OnApplicationQuit,OnApplicationPause,OnApplicationFocus,可以选择不同的方式来驱动自己的逻辑

#### API

* update

  ```lua
  function loops.addUpdateEvent(_action)
  function loops.removeUpdateEvent(_action)
  ```

* lateUpdate

  ```lua
  function loops.addLateUpdateEvent(_action) 
  function loops.removeLateUpdateEvent(_action)
  ```

* fixedUdate

  ```lua
  function loops.addFixedUpdateEvent(_action)
  function loops.removeFixedUpdateEvent(_action)
  ```

* AppQuit

  ```lua
  function loops.addAppQuitEvent(_action)
  function loops.removeAppQuitEvent(_action)  
  ```

* AppPause

  ```lua
  function loops.addAppPause(_action)
  function loops.removeAppPause(_action)
  ```

* AppFcous

  ```lua
  function loops.OnApplicationFocus(hasFocus)
  function loops.removeAppFocus(_action)
  ```

------

### 事件(`MessageManager`)

#### 说明

* 处理游戏内事件的注册，注销，分发

#### API

* 注册事件

  ```lua
  function MessageManager:Regist(_key, _func)
  ```

* 注销事件

  ```lua
  function MessageManager:UnRegist(_key, _func)
  ```

* 触发事件

  ```lua
  function MessageManager:Invoke(_key, ...)
  ```

------

### 场景(`unitySceneManager`)

#### 说明

* 执行场景转换，特别是大型功能模块切换的时候需要转场，比如关卡模块和主场景模块以及一些大型玩法模块地切换
* 需要先卸载旧资源再加载新场景和新资源
* 有利于内存优化和资源管理
* 由于过程比较久需要专门的加载界面做缓冲

#### 流程

1. 加载一个空场景，为了更加有效干净地清理旧场景的资源
2. 执行一次Lua层的全量垃圾回收
3. 卸载所有未使用的动态资源
4. 执行一次C#层的全量垃圾回收
5. 加载新场景

#### API

* 加载

  ```lua
  --异步加载场景(协程)
  ---@public
  function SceneManager.LoadAsync(_mainId, _subId)
  ```

  

  ```lua
  --异步加载场景(callback)
  ---@public
  function SceneManager.Load(_mainId, _subId, _onComplete)
  ```

------

### SDK

#### 说明

#### API

------

### 本地存储

#### 说明

* 通过serverID，和用户pid包装为一个查询Key
* 使用PlayerPrefs作为本地存储手段

------

### 类（`class`）

#### 说明

* 只用来标识Table，并不用来做面向对象的建模，接近函数式编程

#### API

------

### 协程(`LuaCoroutine`)

#### 说明

处理异步逻辑时可以同步化流程操作,比如等待加载完成,等待指定时间,等待场景加载完毕等等

#### API	

* Start

  ```lua
  --传入一个处理函数开启一个协程,这个处理函数的所有调用栈都执行在这个协程内
  ---@param func fun(...) 协程处理函数
  local function start(func, ...)
  ```

* WaitforSecond

  ```lua
  --等待时间
  ---@param secondCnt number 等待的时间(以秒为单位)
  local function waitForSeconds(secondCnt)
  ```

* waitForFrames

  ```lua
  --等待帧(update)
  ---@param frameCnt number 等待的帧数
  local function waitForFrames(frameCnt)
  ```

* waitForEndOfFrame

  ```lua
  --等待帧(lateupdate)
  ---@param frameCnt number 等待的帧数
  local function waitForEndOfFrame(frameCnt)
  ```

* waitForFixedUpdate

  ```lua
  --等待帧(fixedupdate)
  ---@param frameCnt number 等待的帧数
  local function waitForFixedUpdate(frameCnt)
  ```

* waitUntil

  ```lua
  --等待处理逻辑直到返回true
  ---@param func fun(...):boolean
  local function waitUntil(func, ...)
  ```

* waitWhile

  ```lua
  --等待处理逻辑直到返回false
  ---@param func fun(...):boolean
  local function waitWhile(func, ...)
  ```

* waitForAsyncOp

  ```lua
  --等待一个异步处理对象,直到对象的IsDone为True
  ---@param async_operation AsyncOperation 异步对象
  ---@param callback fun(async_op:AsyncOperation, co:thread) 在没有结束前轮询时的回调
  ---@return boolean 异步逻辑执行失败与否,如果执行成功返回true,失败返回false
  local function waitForAsyncOp(async_operation, callback)
  ```

* stopWaiting

  ```lua
  --让一个已知的协程立即结束
  ---@param co thread
  local function stopWaiting(co, ...)
  ```

------

### 模块

#### 说明

#### API

------

## 网络

### 协议

#### 结构

* Write

  * 填充目标协议的包体
  * 发送包
  * 接受一个回调（_callback）和一个透传参数（_extra）

* Proto

  * 目标协议的解析和打包

#### 编码

* 协议类型（byte）

  * 请求（Req）	

    * 客户端发出的
    * 命名为*`R_XXX_XXX_Xxx`*
    * 任何请求都可能失败，导致应答*A_000_002_OpNg*
    * 一个请求一般都对应多种应答
    * 请求与应答以会话ID相关联

  * 应答（Resp）
    * 客户端收到的
    * 命名为*`A_XXX_XXX_Xxx`*

  * 推送（Notify）

    * 客户端收到的
    * 服务器没有经过客户端请求自动发送的
    * 命名为*`N_XXX_XXX_Xxx`*

  * 自动应答（AutoResp 类似推送，只是处理异常行为）

* 主协议号（`ID`）

* 子协议号（`SubID`）

* 会话ID（`SID`）

* 哈希值（`UID id * 65536 + subId`）

* 包体（`Obj`）

  * 值类型
  * 引用类型
  * 数组

#### 透传协议

* ###### 概念

  * 如果比较轻量的协议（比如查询），先包装到一个共同的协议里（*`R_007_010_Req`*）再发送，服务端可以大大减少并发的处理请求

* ###### 流程

  * 先请求*`R_007_010_Req`*协议
  * 往里面的passReq字段填充具体的协议内容
  * 以*`R_007_010_Req`*这个协议作为主体发送

#### 会话流程

* ##### 发送

  * 获取目标协议的Write（`getWriter`），传入参数
  * 打包成数据流
  * Client进入会话循环，当前会话进入会话队列
  * Soket发送元数据

* ##### 接收

  * Soket收到元数据
  * Client解包，提取当前会话上下文
  * 分发调用目标用户回调

* ##### 处理

  * 根据返回协议号处理相应的业务逻辑
  * 直接从解析出来的包体中获取服务端的返回值

------

### 登录服（LS）

#### 连接

* ##### PHP后台登入

  * 选择最优PHP后台地址（根据Ping的时间）
  * 设置cdn地址，公共远程api地址，主要用于后续通信
  * 获取平台信息

* ##### 更新App

  * 如果平台数据不满足要求需要
  * 如果需要强行更新

* ##### PHP后台通信

  * 获取区服信息
    * 大区列表
      * 区服ID，名字
      * 登录服信息
        * IP
        * Port
      * 推荐游戏服信息
  * 获取公告信息

* ##### [根据需求走资源热更新流程]( #更新流程)


------

### 游戏服（GS）

#### 登录

* 连接登录服
* 从PHP后台获取游戏内公告
* 从登录服获取目标游戏服的Host和port，用户的pid和令牌
* 断开登录服的连接
* 连接游戏服
* 获取游戏登录数据

------

## 资源

### 特效

#### 说明

* 池化特效对象（当特效对象使用完毕归还到池中）
* 场景特效 
* UI特效

* 在场景中播放

* 在FGUI上播放
  * 由于特效的显示会产生层级问题，所以添加一个Graph占位
  * 使用GWapper包裹特效资源

#### API

------

### 音效

#### 说明

* 音乐

* 效果音

#### API

------

#### Sprite

#### 说明

* 根据对象ID（mainID + subID）转换成FGUI的资源URL（SpriteIdToURLConfig）
* FGUI的Gloader会自动根据最新的资源URL加载最新的资源

#### API

* 通过对象数据获取FGUI的资源URL（getImageUrlWithStruct）

------

## UI

### 规则

#### 结构

* Model （存放建模数据）

* View  （与FGUI组件绑定，并链接到`ViewModle`，可以起到内存隔离的作用）

* View Modle  （系统界面逻辑，提供全周期Hook）

#### 显示层级

* Base

* Normal

* Tip

* System

#### 功能

* 在FGUI界面创建完毕后，会根据对应额外配置参数（KeyValue）执行某项功能 

#### 打开规则

#### 关闭规则

------

### UI管理（`UIManager`）

#### 说明

* ###### 原子操作

  * ###### 执行命令（从池中获取和归还)

    * viewModle名字
    * 参数（透传给目标viewModle的data)
    * 回执（Call back)

  * ##### 开（UIManager.doOpen

    * 执行显示前逻辑，比如绑定按钮事件和一些初始化操作
    * 设置当前层级
    * 适配全屏
    * 如果是模态窗，更新模态窗的层级
    * 执行动画调用前逻辑
    * 执行打开动画
    * 执行动画调用后逻辑

  * ##### 关闭（UIManager.doClose）

    * 执行关闭前逻辑，比如解除绑定和一些逆初始化操作
    * 执行关闭动画
    * 执行关闭后逻辑，这里主要是一些销毁操作

  * ##### 层级

    * ###### 添加到层级

      * 添加到层级记录中

    * ###### 从层级移除

      * 从层级记录中移除
      * 如果是模态窗，更新模态窗的层级

#### 轮询

* ##### 执行关闭操作队列

  * 执行关闭流程

    * [执行关闭原子操作](#关闭)

  * ##### 全屏View处理（因为全屏View关闭后需要返回上一个全屏View）

  * ##### 执行开启操作队列

    * 注册ViewModel

    * 设置透传参数 

    * 如果已经打开，执行重打开接口（doReOpen）

    * 如果没有打开，执行打开流程（doOpen）

      * ##### 创建View

        * 添加FGUI Package([执行C#侧的加载操作](#加载))
        * 设置并记录View（[通过Lua动态绑定](#Lua动态绑定)）
        * 提取View的UserData（通过FGUI编辑器设置的键值对参数）
        * 如果View是全屏的，立即关闭上一个全屏View
        * 如果是主界面，手动强制清理全屏View记录栈（这里可能是因为有些全屏界面没有正常的关闭比如断线线重连或者未知错误需要强制回到主界面，所以这里添加保护措施)

      * [执行打开原子操作](#打开（UIManager.doOpen）)

#### API

* ##### 行为

  * 打开（show）
  * 立即打开（openImmediately）
  * 关闭（hide）
  * 立即关闭（hideImmediately）
  * 关闭全部（hideAll）
  * 销毁（destroy）

* ##### 查询

  * 获得层级列表（getLayer）
  * 获得view（getView）
  * 获得viewModel（getViewModel）
  * 可见性（IsVisible）

* ##### 效果

  * 背景模糊

------

