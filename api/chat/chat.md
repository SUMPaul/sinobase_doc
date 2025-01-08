# 接口文档

## 数字人

- 简单数字人对话

```
Header
Authorization: token / ignored

GET /chat/basic

request

client event_type 枚举
EventType_Client_Init  = "Init"     初始化 ws 链接
EventType_Client_Chat  = "Chat"     开始对话
EventType_Client_Close = "Close"    关闭连接

Init
{
    "event_type":"Init"
}

Chat
{
    "event_type":"Chat",
    "content": "你是谁？"
}

Close
{
    "event_type":"Close"
}

response

server event_type 枚举
EventType_Server_PreData         = "PreData"
EventType_Server_SensitiveVerify = "SensitiveVerify"
EventType_Server_Chat            = "Chat"
EventType_Server_TTS             = "TTS"

PreData
初始化之后，返回相关的数字人视频uri
{
    "event_type": "PreData",
    "err_code": 0,
    "err_msg": "",
    "data": {
        "urls": [
            "url_0",    // 暂停动作视频url
            "url_1",    // 1s说话 url
            "url_2",    // 2s说话 url
            "url_3",    // 3s说话 url
            "url_4",    // 4s说话 url
            "url_5"     // 5s说话 url
        ],
        "speech_url": "wss://iat.xf-yun.com/v1?authorization=aG1hYyB1c2VybmFtZT0iMzM2ZTJlYTY2YjNiZDdkYzZmYmYxNzY0ODgwMDYwYzMiLCBhbGdvcml0aG09ImhtYWMtc2hhMjU2IiwgaGVhZGVycz0iaG9zdCBkYXRlIHJlcXVlc3QtbGluZSIsIHNpZ25hdHVyZT0ia0dra3JXRkt2Yi82VllCb3IyeEUxaFlRMW9YUHh3R3BOZWRnSFJ6blVzQT0i&date=Wed%2C+08+Jan+2025+08%3A11%3A08+UTC&host=iat.xf-yun.com"
    },
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

Chat
数字人对话的answer
{
    "event_type": "Chat",
    "err_code": 0,
    "err_msg": "",
    "data": {
        "message_id": 12,
        "content": "我是你的女朋友，同时也是一名知识渊博的女医生。我热爱医学，喜欢帮助病人，也喜欢和你一起度过每一个美好的时刻。无论是工作还是生活，我都会尽力做到最好。"
    },
    "wait_flag": true
}

TTS
tts之后的语音流
{
    "event_type": "TTS",
    "err_code": 0,
    "err_msg": "",
    "data": {
        "audio_stream": "AudioStream"
    },
    "wait_flag": false
}
```