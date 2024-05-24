<h3 align="center" style="margin: 30px 0 30px;font-weight: bold;font-size:40px;">chenmo-ping</h3>
<h3 align="center">Ping</h3>

## 说明

该插件用于在 Uni-app 中执行 Ping 操作，以检测指定主机的网络连通性并获取响应时间。

## 使用说明


## 链接

- [GitHub]()

## 使用方法

### 1. 同步ping
```vue
<script setup>
import { pingSync } from "@/uni_modules/chenmo-ping"
function handlePingSync() {
	const res = pingSync({
		addr: "www.baidu.com"
	})
	console.log(res);
}
</script>
```
### 2. 异步ping
```vue
<script setup>
import { ping } from "@/uni_modules/chenmo-ping"
function handlePing() {
	ping({
		addr: "192.168.88.1",
		success: (res) => {
			console.log(res)
		},
		fail: (e) => {
			console.log(e)
		},
		complete: (res) => {
			console.log(res)
		}
	})
}
</script>
```
## 参数说明

### 1.请求参数

|    参数    |   类型   | 必填 |                       说明                       |
| :--------: | :------: | :--: | :----------------------------------------------: |
|    addr    |  String  |  是  |                    ping的地址                    |
|    time    |  Number  |  否  |                 超时时间s,默认5s                 |
|   count    |  Number  |  否  |                 ping次数,默认5次                 |
| packetSize |  Number  |  否  |                  包大小,默认32                   |
|  success   | Function |  否  |                接口调用成功的回调                |
|    fail    | Function |  否  |              接口调用失败的回调函数              |
|  complete  | Function |  否  | 接口调用结束的回调函数（调用成功、失败都会执行） |
### 2.返回值

|    参数    |  类型  |       说明        |
| :--------: | :----: | :---------------: |
|  errCode   | Number |      错误码       |
| errSubject | String |    errSubject     |
|   errMsg   | String |     错误信息      |
|    time    | Number | 平均时延,单位为ms |
| packetLoss | Number |      丢包率       |

## 捐赠

如果您认为我的插件帮到了您的开发工作，您可以捐赠我的研发工作，捐赠无门槛，哪怕是一杯可乐也好(相信这比打赏主播更有意义)。

## 版权信息
chenmo-ping遵循[MIT](https://en.wikipedia.org/wiki/MIT_License)开源协议，意味着您无需支付任何费用，也无需授权，即可将chenmo-ping应用到您的产品中。