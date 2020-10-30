# 通讯模块

## 安装

```shell script
eco plugin install https://github.com/kjeco/communication
```

## 卸载

```shell script
eco plugin uninstall https://github.com/kjeco/communication
```

## 引用

```js
const communication = app.requireModule("eco/communication");
```

### call(to, callback) 拨打电话

#### 参数

1.  `to` (String)

2.  [`callback`] (Function)

#### 示例

```
communication.call('415-736-0000')
```

```
communication.call('415-736-0000', () => {
    console.log('called')
})
```

* * *

### mail(to, options, callback) 发送邮件

#### 参数

1.  `to` (String | Array)

2.  [`options`] (Object)
    *   `subject` (String)

    *   `body` (String)

3.  [`callback`] (Function)

#### 示例

```
communication.mail('hi@natjs.com')
```

```
communication.mail(['hi@natjs.com', 'dev@natjs.com'], {
    subject: 'Subject',
    body: 'content goes here'
}, () => {
    console.log('email popup')
})
```

* * *

### sms(to, message, callback) 发送短信

#### 参数

1.  `to` (String | Array)

2.  [`message`] (String)

3.  [`callback`] (Function)

#### 示例

```
communication.sms('415-736-0000')
```

```
communication.sms(['415-736-0000', '425736-32'], 'message goes here', () => {
    console.log('sms popup')
})
```

* * *

> **Error**<br/>
> CALL_PHONE_PERMISSION_DENIED<br/>
> SEND_SMS_PERMISSION_DENIED<br/>
> CALL_INVALID_ARGUMENT<br/>
> SMS_INVALID_ARGUMENT<br/>
> MAIL_INVALID_ARGUMENT
