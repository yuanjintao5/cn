# 同义词

## 一、接口描述

### 1. 功能描述

近义词及相关词查询

### 2. 接口使用

进入京东智联云控制台-账号管理-Access Key管理，创建并获取Access Key。整体流程详见 [调用方法](https://docs.jdcloud.com/cn/common-declaration/api/call-methods) 。

## 二、请求说明

### 1. 接口地址 ：

```
https://aiapi.jdcloud.com/jdai/corpus_synonyms
```

### 2. 请求方式：

```
 GET
```

### 3. 请求参数

#### （1）query请求参数

公共请求参数

| 名称      | 类型   | 必填 | 示例值                           | 描述                                           |
| --------- | ------ | ---- | -------------------------------- | ---------------------------------------------- |
| appkey    | string | 是   | 80d2b762ecb86593f9668526920f46c  | 您的appkey，可在买家中心控制台中获             |
| timestamp | long   | 是   | 1541491668060                    | 请求的时间戳，精确到毫秒，timestamp有效期5分钟 |
| sign      | string | 是   | 2e148773a0337a8f2200ba90d445f083 | 签名，根据规则MD5(sectetkey+timestamp)         |

#### （2）header请求参数

业务请求参数

| 名称         | 类型   | 必填 | 示例值           | 描述                       |
| ------------ | ------ | ---- | ---------------- | -------------------------- |
| Content-Type | string | 是   | application/json | 表示请求JSON格式的文本信息 |

#### （3）业务请求参数

业务请求参数

| 名称 | 类型   | 必填 | 示例值 | 描述           |
| ---- | ------ | ---- | ------ | -------------- |
| word | string | 是   | 苹果   | 要查询的近义词 |

### 3、请求代码示例

```
https://aiapi.jd.com/jdai/corpus_synonyms?word=苹果
```

## 三、返回说明

### 1、返回参数

#### （1）公共返回参数

| 名称          | 类型    | 示例值        | 描述                                                         |
| ------------- | ------- | ------------- | ------------------------------------------------------------ |
| code          | string  | 1000          | 参见下方错误码-系统级错误码                                  |
| charge        | boolean | false 或 true | false：不扣费， true：扣费                                   |
| remain        | long    | 1305          | 剩余调用次数；免费api：每天剩余调用次数；收费api：剩余次数；无限制时为-1 |
| remainTimes   | long    | 1305          | 剩余调用次数；免费api：每天剩余调用次数；收费api：剩余次数；无限制时为-1 |
| remainSeconds | long    | 1223456       | 剩余调用时间（s）；免费api：-1；收费api：剩余调用时间；无限制时为-1 |
| msg           | string  | 查询成功      | 参见下方错误码-系统级错误码数                                |
| result        | object  | {...}         | 查询结果                                                     |

#### （2）业务返回参数

| 名称 | 类型   | 示例值 | 描述     |
| ---- | ------ | ------ | -------- |
| code | string | 200    | 请求成功 |
| msg  | string | 否     |          |
| data | object | {}     | 输出内容 |

data参数信息

| 名称      | 类型     | 示例值                                                       | 描述           |
| --------- | -------- | ------------------------------------------------------------ | -------------- |
| inputText | string   | 苹果                                                         | 原始查询词语   |
| synonym   | string[] | [ "智慧果", "平安果", "超凡子", "平波", "滔婆", "天然子", "苹果公司", "小米", "黑莓", "苹果电脑", "iPad", "新产品", "产品", "洋葱", "草莓", "惠普", "巧果", "甜果", "红果", "宝诚" ] | 相关近义词列表 |

### 2、返回示例

```
{
  "code": 200,
  "msg": null,
  "data": {
    "text": "苹果",
    "synonym": [
      "智慧果",
      "平安果",
      "超凡子",
      "平波",
      "滔婆",
      "天然子",
      "苹果公司",
      "小米",
      "黑莓",
      "苹果电脑",
      "iPad",
      "新产品",
      "产品",
      "洋葱",
      "草莓",
      "惠普",
      "巧果",
      "甜果",
      "红果",
      "宝诚"
      ]
  }
}
```

## 四、错误码

### 1.系统级错误码

[详见返回码](https://aidoc.jd.com/user/returncode.html)

### 2. 业务错误码

| 返回码（code） | message | 说明（message）  |
| -------------- | ------- | ---------------- |
| 500            |         | 模型解析数据失败 |