# Admin API Reference Guide

1. [創建公告](#CreateBulletin)
2. [修改公告](#alter)
3. [刪除公告](#delete)
4. [Update Role User](#UpdateRoleUser)
5. [Delete User](#DeleteUser)

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
        <td style="width:50px">Integer'</td>
        <td style="width:150px">authorId</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr><tr>
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

### JSON Response
#### Success
200 OK

```
{
  "result": true
}
```


#### Error
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
```
status code:200
{
  "Users": [
    {
    	"id": *id*,
		"uid": *uid*,
		"email": *email*,
		"name": *name*,
		"role": *role*,
		"created_at": *createTime*,
		"updated_at": *updateTime*
    }
  ]
}
```

#### Error
```
status code:403
{
  "message": "The email does not exist"
}
- or -
status code:403
{
  "message": "Permission denied"
}
```

## 4.<a name="UpdateRoleUser">Update Role User</a>
<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">POST</td>
        <td style="width:400px">/api/v1/admin/role</td>
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
        <td style="width:50px">String</td>
        <td style="width:150px">email</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px"></td>
    </tr>
    <tr>
        <td style="width:50px">String</td>
        <td style="width:150px">role</td>
        <td style="width:50px">✔︎</td>
        <td style="width:100px">admin or user</td>
    </tr>
</table>

### JSON Response
#### Success
```
status code:200
{
  "Users": [
    {
    	"id": *id*,
		"uid": *uid*,
		"email": *email*,
		"name": *name*,
		"role": *role*,
		"created_at": *createTime*,
		"updated_at": *updateTime*
    }
  ]
}
```

#### Error
```
status code:403
{
  "message": "The email does not exist"
}
- or -
status code:403
{
  "message": "Permission denied"
}
```

## 5.<a name="DeleteUser">Delete User</a>
<table>
    <tr>
        <td style="width:50px">Method</td>
        <td style="width:400px">URI</td>
    </tr>
    <tr>
        <td style="width:50px">DELETE</td>
        <td style="width:400px">/api/v1/admin/delete/{email}</td>
    </tr>
</table>

### JSON Response
#### Success
```
status code:200
{
  "message": "The user has been deleted"
}
```

#### Error
```
status code:403
{
  "message": "The email does not exist"
}
- or -
status code:403
{
  "message": "Permission denied"
}
- or -
status code:403
{
  "message": "The delete user operation failed"
}
```

