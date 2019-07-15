2 接口方式
2.1 数字签名
为保证接口双方在数据传输过程中的数据真实性和完整性，接口请求方需要对数据进行数字签名，接口接收方在接受签名数据后进行签名校验。
2.1.1 签名算法
签名规则：
	按参数名ASCII码从小到大排序（字典序）；
	如果参数的值为空，则此参数不参与签名；
	参数名区分大小写；
	设所有发送或者接收到的数据为集合M，将集合M内非空参数值的参数按照参数名ASCII码从小到大排序（字典序），使用URL键值对的格式（即key1=value1&key2=value2…）拼接成字符串

如：某接口有以下参数：
参数名	参数值
version	1.0
portalType	WAP
portalId	100
respTime	2016-04-08 18:39:00
transactionId	20160408183900000001
funcCode	queryUserPrizeSum
retCode	0
retMsg	成功
sumDetails	[{“prizeType”:“CREDIT”,“prizeTypeName”:“流量币”,“prizeNum”:“20”},{“prizeType”:“COUPON”,“prizeTypeName”:“电子券”,“prizeNum”: “6” }]

排序后的参数顺序：funcCode、portalId、portalType、respTime、retCode、retMsg、transactionId、sumDetails、version
那么签名数据明文就是：
funcCode=queryUserPrizeSum&portalId=100&portalType=WAP&respTime=2016-04-08 18:39:00&retCode=0&retMsg=成功
&transactionId=20160408183900000001&sumDetails=[{“prizeType”:“CREDIT”,“prizeTypeName”:“流量币”,“prizeNum”:“20”},{“prizeType”:“COUPON”,“prizeTypeName”:
“电子券”,“prizeNum”: “6” }]&version=1.0

