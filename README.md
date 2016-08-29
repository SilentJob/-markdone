# -markdone
測試markdone



## H2

> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.

  <br />  
  <br />  
  <br />  
  
階層式區塊用兩個大於符號(>>)：
> 新北市
>>板橋區
>>中和區

> 桃園縣
>>大溪鎮
>>龜山鄉

*   Red
*   Green
*   Blue
或
+   Red
+   Green
+   Blue
或
-   Red
-   Green
-   Blue
-   
**粗體**

*斜體*

~~刪除線~~

| Left-Aligned  | Center Aligned  | Right Aligned |
| :------------ |:---------------:| -----:|
| col 3 is      | some wordy text | $1600 |
| col 2 is      | centered        |   $12 |
| zebra stripes | are neat        |    $1 |
| test | 測試        |    $3333 |


```php
  echo "測試";
```

##Update User Profile

Update the profile for a specific user account.

PUT /account/{userId}/profile

##Headers

AuthSessionId - Identifier for current session
AuthSessionSecret - Secret for current session

##Parameters

userId - Identifier for current user

##Body

username - Username to update to
email - E-mail address to update to

##Response

userId - Identifier for the user

##Errors

ErrorCode1 - Caused by missing identifier
ErrorCode2 - Username was not given
ErrorCode3 - Server exploded
Example Request

` GET /account/1692/profile `

```
{
    username: "NewUsername",
    email: "Email@Email.com"
}
```
`Example Response`

`200 OK`

`{
    userId: 1692
}`
