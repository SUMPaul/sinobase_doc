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
校验通过
{
    "code": 200
}


校验不通过
{
    "code": 400,
    "message": "sensitive verify failed"
}
```