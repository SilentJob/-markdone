# Admin API Reference Guide

1. [創建公告](#CreateBulletin)
2. [修改公告](#alter)
3. [刪除公告](#delete)
4. [公告留言](#comment)
5. [刪除留言](#deleteComment)

## 1.<a name="CreateBulletin">創建公告</a>

<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">POST</td>
        <td style="width:400px">/api/v1/bulletin/in/create</td>
    </tr>
</table>

### Input Parameter

<table>
    <tr>
        <td style="width:50px">Type</td>
        <td style="width:150px">Name</td>
        <td style="width:50px">Require</td>
        <td style="width:100px">Remark</td>
    </tr>
    <tr>
        <td style="width:50px">Integer</td>
        <td style="width:150px">groupId</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px ">in:[1~7]</td>
    </tr>
    <tr>
        <td style="width:50px">Sting</td>
        <td style="width:150px">title</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px">max:50</td>
    </tr>
    <tr>
        <td style="width:50px">text</td>
        <td style="width:150px">content</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr>
</table>

### JSON Response
#### Success
```
200 OK

{
  "result": true
}

```

#### Error
400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```

## 2.<a name="alter">修改公告</a>
<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">PUT</td>
        <td style="width:400px">/api/v1/bulletin/in/alter</td>
    </tr>
</table>
### Input Parameter

<table>
    <tr>
        <td style="width:50px">Type</td>
        <td style="width:150px">Name</td>
        <td style="width:50px">Require</td>
        <td style="width:100px">Remark</td>
    </tr>
    <tr>
        <td style="width:50px">Integer</td>
        <td style="width:150px">id</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px "></td>
    </tr>
    <tr>
        <td style="width:50px">Sting</td>
        <td style="width:150px">title</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px">max:50</td>
    </tr>
    <tr>
        <td style="width:50px">text</td>
        <td style="width:150px">content</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr>
</table>
### JSON Response
#### Success
200 OK

```
{
  "result": true
}
```


#### Error
400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```

## 3.<a name="delete">刪除公告</a>
<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">Delete</td>
        <td style="width:400px">/api/v1/bulletin/in/delete</td>
    </tr>
</table>

### Input Parameter

<table>
    <tr>
        <td style="width:50px">Type</td>
        <td style="width:150px">Name</td>
        <td style="width:50px">Require</td>
        <td style="width:100px">Remark</td>
    </tr>
    <tr>
        <td style="width:50px">Integer</td>
        <td style="width:150px">id</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr>
</table>

### JSON Response
#### Success
200 OK

```
{
  "result": true
}
```


#### Error
400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```

## 4.<a name="comment">公告留言</a>
<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">POST</td>
        <td style="width:400px">/api/v1/bulletin/in/comment</td>
    </tr>
</table>

### Input Parameter

<table>
    <tr>
        <td style="width:50px">Type</td>
        <td style="width:150px">Name</td>
        <td style="width:50px">Require</td>
        <td style="width:100px">Remark</td>
    </tr>
    <tr>
        <td style="width:50px">Integer</td>
        <td style="width:150px">bulletinId</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr>
    <tr>
        <td style="width:50px">Integer</td>
        <td style="width:150px">authorId</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr><tr>
        <td style="width:50px">String</td>
        <td style="width:150px">comment</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px">留言 max:50</td>
    </tr>
</table>

### JSON Response
#### Success
200 OK

```
{
  "result": true
}
```


#### Error
400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```

## 5.<a name="deleteComment">刪除留言</a>
<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">DELETE</td>
        <td style="width:400px">/api/v1/bulletin/in/deleteComment</td>
    </tr>
</table>
### Input Parameter

<table>
    <tr>
        <td style="width:50px">Type</td>
        <td style="width:150px">Name</td>
        <td style="width:50px">Require</td>
        <td style="width:100px">Remark</td>
    </tr>
    <tr>
        <td style="width:50px">Integer</td>
        <td style="width:150px">id</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px">該留言的id</td>
    </tr>
    
</table>
### JSON Response
200 OK

```
{
  "result": true
}
```

#### Error
400 Bad Request
```
{
  "error": {
    "code": 400002,
    "message": "validation.required"
  }
}
```

