# 中国身份证


## 描述
中国身份证

## 请求方式

POST

## 请求地址

```apl
https://aiapi.jd.com/jdai/maskInsurance
```

## 请求参数

| 参数名称          | 参数类型 | 是否必填 | 参数说明                                                     |
| :---------------- | :------- | :------- | :----------------------------------------------------------- |
| `serialNo`        | string   | N        | 请求流水号, 不传接口自动生成                                 |
| `appName`         | string   | Y        | 授权appName, 申请分配                                        |
| `appAuthorityKey` | string   | Y        | 授权key, 申请分配                                            |
| `businessId`      | string   | Y        | 业务id, 申请分配                                             |
| `idcardItem`      | object   | Y        | 采集的图片[公共请求参数实体#公共请求参数实体-4.图片信息](https://cf.jd.com/pages/viewpage.action?pageId=138528176#id-公共请求参数实体-公共请求参数实体-4.图片信息) |
| `idcardType`      | enum     |          | `/** * 身份证检测结果(正面, 反面) */`` ``P("身份证正面"),N("身份证反面");` |
| `extMap`          | map      | N        | 附加信息, 特殊需求处理                                       |







# 返回实体

| 参数名称             | 参数类型 | 是否必填 | 参数说明         |      |
| :------------------- | :------- | :------- | :--------------- | :--- |
| `code`               | int      |          | 返回code码0:成功 |      |
| `msg`                | string   |          | msg              |      |
| `serialNo`           | string   |          | 交互的流水号     |      |
| `idCardInfo`         | object   |          | 正面信息         |      |
| `--name`             | `String` |          | `身份证号`       |      |
| `--cardNo`           | `String` |          | `姓名`           |      |
| `--sex`              | `String` |          | `性别`           |      |
| `--nation`           | `String` |          | `名族`           |      |
| `--address`          | `String` |          | `户籍地址`       |      |
| `--brith`            | `String` |          | 生日yyyymmdd     |      |
| `idCardBackInfo`     | object   |          | 反面信息         |      |
| `--singDate`         | `String` |          | `签发时间`       |      |
| `--expirationDate`   | `String` |          | `过期时间`       |      |
| `--issuingAuthority` | `String` |          | `签证机关`       |      |
| `--overdue`          | `String` |          | `是否过期`       |      |
| `extMap`             | map      |          | 返回身份证url    |      |
| `--idCardUrl`        | `String` |          | 身份证正面url    |      |
| `--idCardBackUrl`    | `String` |          | 身份证反面url    |      |



## 请求参数示例

```
{
	"businessId": "XXX",
	"appName": "XXX",
	"appAuthorityKey": "XXX",
	"idcardType": "P",
	"idcardItem": {
		"imgType": "IDP",
		"imgBase64": "图片se64",
		"encryptionType": "NON"
	}
}
```



## 返回样例

```
{
    "code": 0,
    "idCardInfo": {
        "name": "张素芳",
        "address": "山西省忻州市忻府区董村镇太延村二组215号",
        "nation": "汉",
        "cardNo": "142201199003272740",
        "sex": "女"
    },
    "serialNo": "w1232",
    "timestamp": 1547524786490
}
```

