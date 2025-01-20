# 接口文档

## 产品

- 建议产品

```
Header
Authorization: token / ignored

POST https://api.aibaobao.chat/fakeman/product/suggest

request
{
    "conversation_id":"111"
}

resp
{
    "code": 200,
    "data": [
        {
            "product_id": 5089,
            "name": "諾維康豐滿秀",
            "picture": "https://sinobase.adaptivesuite.cloud/storage/goods/14/2024-12-06/PJKp2KJmLt9GVTndSJDuUIH8riJAExWjMa8kaFVN.jpg",
            "price": "280.00"
        },
        {
            "product_id": 3584,
            "name": "可萊絲膠原彈性緊緻保濕導入精華面膜 10`S",
            "picture": "https://sinobase.adaptivesuite.cloud/storage/goods/202412/2024-12-03/f6216c8da6ad21062a749dceae7099c0bsn240160-1.jpg",
            "price": "94.80"
        },
        {
            "product_id": 3840,
            "name": "男士活力保濕霜 100ML",
            "picture": "https://sinobase.adaptivesuite.cloud/storage/goods/202412/2024-12-03/4e789337257e2929d4bf49feaf2f5bb7bsn220037.jpeg",
            "price": "198.00"
        },
        {
            "product_id": 4096,
            "name": "全效UV修護霜(防敏) 50G",
            "picture": "https://sinobase.adaptivesuite.cloud/storage/goods/202412/2024-12-03/76306fdc453051af6be5245bf33daf83bsn185725-1.png",
            "price": "85.20"
        },
        {
            "product_id": 4352,
            "name": "超水感保濕溫和去角質GEL 250G",
            "picture": "https://sinobase.adaptivesuite.cloud/storage/goods/202412/2024-12-03/61d107132cd7feba726ddee52f0e4b9fbsn182924-1.png",
            "price": "139.20"
        }
    ],
    "message": "ok"
}