### TAGS
##### GET TAGS
`GET /api/tags` 
No authentication required, return all a List of Tags

---

### ARTICLES
##### GET Articles
`GET /api/articles`
No authentication required, return all a List of Articles

---

##### GET Articles by Slug
`GET /api/articles/:slug` 
No authentication required, return a single Article

Update: 
+ need to return `isFollowing` and `isFavorited` for the current user
+ check `favoritesCount`, currently its not properly => need to update
+ return `avatar` for the author


--- 

##### CREATE Article
`POST /api/articles`
Authentication required, returns the created Article

**BODY**
```json
{
    "title" : "If we quantify the alarm, we can get to the FTP pixel through the online SSL interface!",
    "description": "Omnis perspiciatis qui quia commodi sequi modi. Nostrum quam aut cupiditate est facere omnis possimus. Tenetur similique nemo illo soluta molestias facere quo. Ipsam totam facilis delectus nihil quidem",
    "body": "Body Quia quo iste et aperiam voluptas consectetur a omnis et.\\nDolores et earum consequuntur sunt et.\\nEa nulla ab voluptatem dicta vel",
    "tagList": [
        "reactjs",
        "angularjs",
        "dragons"
    ], // optional
}
```

---

##### UPDATE Article
`PATCH /api/articles/:slug`
Authentication required, returns the updated Article

**BODY**
```json
{
    "title" : "If we quantify the alarm, we can get to the FTP pixel through the online SSL interface!",
    "description": "Omnis perspiciatis qui quia commodi sequi modi. Nostrum quam aut cupiditate est facere omnis possimus. Tenetur similique nemo illo soluta molestias facere quo. Ipsam totam facilis delectus nihil quidem",
    "body": "Body Quia quo iste et aperiam voluptas consectetur a omnis et.\\nDolores et earum consequuntur sunt et.\\nEa nulla ab voluptatem dicta vel",
    "tagList": [
        "reactjs",
        "angularjs",
        "dragons"
    ], // optional
}
```
---

##### DELETE Article By Slug
`DELETE /api/articles/:slug`
Authentication required, returns empty response

---

##### FAVORITE Article
`POST /api/articles/:slug/favorite`
Authentication required, returns the Article

---

##### UNFAVORITE Article
`DELETE /api/articles/:slug/favorite`

---
### USERS
##### LOGIN
`POST /api/users/login`
Authentication required, returns a User

**BODY**
```json
{
    "email": "email@gmail.com",
    "password": "1234abcd"
}
```

---

##### REGISTER
`POST /api/users`
Authentication required, returns a User

**BODY**
```json
{
    "email" : "test10@gmail.com",
    "username": "test10",
    "password": "123123"
}
```

---

##### GET ME
`GET /api/users/me`
Authentication required, returns the current User

---

##### UPDATE ME
`PATCH /api/users/me`

---

##### GET PROFILE
`GET /api/profiles/:username`  
Authentication optional, returns a Profile

---

##### FOLLOW USER
`POST /api/profiles/:username/follow`
Authentication required, returns a Profile

---

##### UNFOLLOW USER
`DELETE /api/profiles/:username/follow`
Authentication required, returns a Profile

