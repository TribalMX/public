
# Routes

## User Data

Endpoint | Description 
---- | --------------- 
GET /api/v2/users/:user | Get a user object |
GET /api/v2/users/:user/clips | Get a user's recent clips  
GET /api/v2/users/:user/broadcasts | Get a user's recent broadcasts 

- where `:user` in every case is their Videogami username or ID
- Example: http://videogami.tv/api/v2/users/riotgames
- Example: http://videogami.tv/api/v2/users/riotgames/clips
- Example: http://videogami.tv/api/v2/users/riotgames/broadcasts



## Create User

Endpoint | Description
---- | ---------------
POST /api/v2/users?twitch=:twitch_username | Create Videogami user using their Twitch username 

- where `:twitch_username` is their Twitch username
- Example: POST http://videogami.tv/api/v2/users?twitch=riotgames


## Create Clip

Endpoint | Description
---- | ---------------
POST videogami.tv/api/v2/clips?user=:user&title=:title| Create a Clip 

- where `:user` is their Videogami username
- where `:title` is the title of the clip
- Example: POST http://videogami.tv/api/v2/clips?twitch=riotgames&title=Awesome%20Play


## Alternative Clipping Routes

### Plain Text Link

| Endpoint | Description |
| ---- | --------------- |
| GET /api/clink/:user | returns link to clip page in plain text |

- This is what existing users are using with your custom api command

### Clipping Button

| Endpoint | Description |
| ---- | --------------- |
| GET /api/c/:user | http redirect to new clip page|

- This route can be used as anchor tag for clipping button, ex http://videogami.tv/api/c/riotgames



### Other Routes
| Endpoint | Description |
| ---- | --------------- |
GET 	/api/v2/users| Newest Users
GET 	/api/v2/clips| Latest Clips
GET 	/api/v2/clips/hot| Trending Clips
GET 	/api/v2/clips/:clip| Get a clip by ID
GET 	/api/v2/broadcasts| Latest broadcasts
GET 	/api/v2/broadcasts/live|  Live broadcasts
GET 	/api/v2/broadcasts/:broadcast| Get a broadcast by ID
