# 接口文档

## 数字人

- 硅基数字人对话

```
Header
GET https://api.aibaobao.chat/fakeman/callback/shengjiAvatarClone

request

client event_type 枚举
EventType_Client_Init  = "Init"
EventType_Client_Sensitive  = "Sensitive"
EventType_Client_ChatSave  = "ChatSave"
EventType_Client_Close = "Close"

Init    // 返回硅基数字人 sign 签名
{
    "event_type":"Init",
    "model_id": 62,
    "role_type": 1,
    "temperaments": [1,2]
}

Sensitive // 校验是否违规
{
    "event_type":"Sensitive",
    "content": "你是谁？"
}

ChatSave // 保存对话
{
    "event_type": "ChatSave",
    "messages": [
        {
            "message_uid": 1212,
            "message_from": 1,
            "content": "1212",
            "voice_url": "1212"
        },
        {
            "message_uid": 1213,
            "message_from": 2,
            "content": "1212",
            "voice_url": "1212"
        }
    ]
}

Close // 关闭语聊
{
    "event_type":"Close"
}

response

server event_type 枚举
EventType_Server_PreData         = "PreData"
EventType_Server_SensitiveVerify = "SensitiveVerify"
EventType_Server_ChatSaved        = "ChatSaved"

PreData
初始化之后，返回相关的数字人视频uri
{
    "event_type": "PreData",
    "err_code": 0,
    "err_msg": "",
    "data": {
        "chat_id":"1111",
        "round": 1,
        "sign": "sign",
        "prompt":"prompt"
    }
    "wait_flag": false
}

SensitiveVerify
输入文本的敏感词校验，若不通过会有报错
{
    "event_type": "SensitiveVerify",
    "err_code": 0,
    "err_msg": "",
    "data": {
        "verify_result": true
    },
    "wait_flag": false
}

ChatSaved
数字人对话的answer
{
    "event_type": "ChatSaved",
    "err_code": 0,
    "err_msg": "",
    "data": {
        "round": 3,
    }
    "wait_flag": false
}
```