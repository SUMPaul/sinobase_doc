# 接口文档

## queue

- 查询队列

1. 高级版数字人在 ws 进行 init 事件之后，会加入到聊天队列中，3s 有效期，所以App端需要每隔2s查询一次，若3s超时则踢出队列
2. 在关闭ws事件后，停止该接口的查询
3. 后台会定时清理过期的队列

如果 found == true && position >=0 && position < range
则说明可以进行高级版数字人聊天
```
GET https://api.aibaobao.chat/fakeman/chat/queue?token=token

resp
{
    "code": 200,
    "data": {
        "found": false,
        "position": -1,
        "range": 1
    }
}
```