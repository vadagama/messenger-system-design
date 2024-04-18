# APIs specification

- [APIs specification](#apis-specification)
    - [POST /register](#post-register)
    - [POST /login](#post-login)
    - [GET /users/{user\_id}](#get-usersuser_id)
    - [POST /messages](#post-messages)
    - [GET /chat/{chat\_id}/messages](#get-chatchat_idmessages)
    - [GET /messages/{message\_id}](#get-messagesmessage_id)
    - [POST /groups](#post-groups)
    - [GET /groups/{group\_id}/messages](#get-groupsgroup_idmessages)
    - [POST /channels](#post-channels)
    - [GET /channels/{channel\_id}/messages](#get-channelschannel_idmessages)


### POST /register
*Method to register a user*
``` javascript
Request: {
    "email": string,
    "login": string, 
    "password": string,
    "name": string
}
```

### POST /login
*Method to login*
``` javascript
Request: {
    "login": string,
    "password": string
}
```
### GET /users/{user_id}
*Method to get a user*
``` javascript
Response: {
    "id": string,
    "email": string,
    "login": string,
    "name": string
    "messages": [
        "readed": [{message_ids}],
        "unreaded": [{message_ids}
        "writed": [{message_ids}]
    "metadata": {
        "friends": [{user_ids}],
        "groups": [{group_ids}],
        "channels": [{channel_ids}]
    }

}
```


### POST /messages 
*Method to send a message*
``` javascript
Request :{
    "chat_id": string,
    "sender_id": string,
    "reciever_id": string,
    "message": string,
    "attachments": [
        {
            "type": string,
            "url": string
        }
    ]
}
```

###  GET /chat/{chat_id}/messages 
*Method to get messages*
``` javascript
Response: {
    [{message_ids}]
}
```

### GET /messages/{message_id}
*Method to get a singlemessage*
``` javascript
Response: {
    "id": string,
    "sender_id": string,
    "reciever_id": string,
    "message": string,
    "attachments": [
        {
            "type": string,
            "url": string
        }
    ]
}
```

### POST /groups
*Method to create a group*
``` javascript
Request: {
    "id": string,
    "name": string,
    "users": [{user_ids}]
}
```

### GET /groups/{group_id}/messages
*Method to get messages from a group*
``` javascript
Response: {
    "id": string,
    "sender_id": string,
    "reciever_id": string,
    "message": string,
    "attachments": [
        {
            "type": string,
            "url": string
        }
    ]
}
```

### POST /channels
*Method to create a channel*
``` javascript
Request: {
    "name": string,
    "users": [{user_ids}]
}
```

### GET /channels/{channel_id}/messages
*Method to get messages from a channel*
``` javascript
Response: {
    "id": string,
    "sender_id": string,
    "reciever_id": string,
    "message": string,
    "attachments": [
        {
            "type": string,
            "url": string
        }
    ]
}
```