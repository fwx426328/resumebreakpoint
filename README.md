# resumebreakpoint
## 一、 断点续传方案

### 1. javascript
*作者：fwx426328*

js对文件切片，分片上传。

### 2. php
*作者：chinesexiaozhu*

1.查询切片是否在。

2.上传切片。

3.合并文件。

## 二、 接口文档
---
### 1. 文件上传接口

请求方式post
入参：
```js
{
	file: File,
	filename: "1.text",
	index: 2,
	id: 'cdee9e473d48764864028e38936bb62d'
}
```
|参数|含义|
|:---|:---|
|file|文件切片|
|filename|文件名称|
|index|切片序号|
|id|文件唯一识别，这里采用md5生成|

返回值:
```js
{
	code: '1'
}
```

|参数|含义|
|:---|:---|
|code|返回码 1-成功 0-失败|


---

### 2. 合并文件接口

请求方法post
入参:
```js
{
	filename: "1.text"
}
```
|参数|含义|
|:---|:---|
|filename|文件名称|


返回值：
```js
{
	code: '1'
}
```
|参数|含义|
|:---|:---|
|code|返回码 1-成功 0-失败|


---

### 3. 查询文件是否存在
请求方式post
入参：
```js
{
	id: 'cdee9e473d48764864028e38936bb62d',
	filename: "1.text"
}
```
|参数|含义|
|:---|:---|
|filename|文件名称|
|index|切片序号|
 
返回值：
```js
{
	code: '1',
	isExist: '1'
}
```

|参数|含义|
|:---|:---|
|code|返回码 1-成功 0-失败|
|isExist|是否存在 1-存在 0-不存在|

---

## 遇到问题
1.后台打开文件失败，提示文件损毁？猜测后台无法自动判断文件类型，故无法打开文件。前端是否可以提供文件类型参数到后台。
