#domain
+ <h3> api/v1/bulletin/in/ </h3>
+ <h3> name加在後面 ex : api/v1/bulletin/in/all  </h3>

#標頭

+ 待補

#errorCode


+ <h3> 400002--> validateFail </h3>
+ <h3> 500001--> otherError </h3>


***
#name
+ all
+ GET
+ **查詢所有公告**

#參數
+ all/{page} 用來查詢第幾頁的，不加預設為第一頁
+ 之後查詢的功能都這樣處理

#Body
+ 無

#Example Request

` GET api/v1/bulletin/in/all/2 `



#Example Response

200 OK

```
{
  "result": {
    "total": 149,
    "per_page": 15,
    "current_page": 2,
    "last_page": 10,
    "next_page_url": "http://12.12.12.12/api/v1/bulletin/in/all/2?page=3",
    "prev_page_url": "http://12.12.12.12/api/v1/bulletin/in/all/2?page=1",
    "from": 16,
    "to": 30,
    "data": [
      {
        "id": 134,
        "groupId": 2,
        "authorId": 2,
        "title": "751",
        "isTop": 0,
        "dateTime": "2023-11-12 02:48:00",
        "groupName": "會議記錄"
      },
      {
        "id": 133,
        "groupId": 7,
        "authorId": 7,
        "title": "734",
        "isTop": 0,
        "dateTime": "2023-11-12 01:47:00",
        "groupName": "其他公告"
      },
      ....
    ]
  }
}
```
***
# name
+ create
+ POST
+ **建立公告**

#Body
+ **groupId** - 群組ID 1~7
+ **authorId** - 使用者ID (亦有可能是使用者名稱)
+ **title** - 標題 
+ **content** - 文章內容

#Response
+ **成功的時候** - {"result":true}
+ **失敗的時候** - {"error":{"code":errorCode,"message":"XXX"}}

#Example Request

`POST api/v1/bulletin/in/create `

{
    groupId:1
    authorId:20
    title:測試
    content:qq
}

#Example Response

200 OK
```
{
  "result": true
}
```
or

400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```
***

#name
+ search
+ POST
+ **查詢關鍵字公告**

#參數
+ 有

#Body

+ **title** - 標題

#Example Request

` POST api/v1/bulletin/in/search/4 `
{
    title:4
}

#Example Response

200 OK

```
{
  "result": {
    "total": 52,
    "per_page": 15,
    "current_page": 3,
    "last_page": 4,
    "next_page_url": "http://12.12.12.12/api/v1/bulletin/in/search/3?page=4",
    "prev_page_url": "http://12.12.12.12/api/v1/bulletin/in/search/3?page=2",
    "from": 31,
    "to": 45,
    "data": [
      {
        "id": 100,
        "groupId": 6,
        "authorId": 2,
        "title": "435",
        "content": "751",
        "isTop": 0,
        "dateTime": "2023-11-10 22:31:00",
        "groupName": "問題討論"
      },
      ...
    ]
  }
}

```

or

400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```
