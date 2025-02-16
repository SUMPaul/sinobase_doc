# 接口文档

## 敏感词

- 敏感词校验

```
Header
Authorization: token / ignored

POST https://api.aibaobao.chat/fakeman/chat/sensitiveVerify

request
{
    "content":"习近平"
    "token": "ignored / token"
}

resp
{
    "code": 200
}



{
    "code": 400,
    "message": "sensitive verify failed"
}
```