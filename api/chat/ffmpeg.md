# 接口文档

## ffmpeg

- 随机视频帧

```
Header
Authorization: token / ignored

POST https://api.aibaobao.chat/fakeman/ffmpeg/randomFrame

request
{
    "url":"https://fcdn.shengjiai.com/temp/digital_human/2025-01-23/0cb675ad-7937-4750-bb12-6902f6c2f92c.mp4"
}

resp
{
    "code": 200,
    "data": [
        "https://sinobase-dev-1331363974.cos.ap-guangzhou.myqcloud.com/image/random_frame/0cb675ad-7937-4750-bb12-6902f6c2f92c_0.png",
        "https://sinobase-dev-1331363974.cos.ap-guangzhou.myqcloud.com/image/random_frame/0cb675ad-7937-4750-bb12-6902f6c2f92c_1.png",
        "https://sinobase-dev-1331363974.cos.ap-guangzhou.myqcloud.com/image/random_frame/0cb675ad-7937-4750-bb12-6902f6c2f92c_2.png"
    ]
}