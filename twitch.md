## Twitch Clipping API


It is unnecessary to manually 'register' a Twitch user as account creation is taken care of automatically whenever a Twitch channel is clipped.


### Twitch Bot Clipping (Plain Text)

GET `/api/clink/twitch/:twitch_username`

- This route will return a plain text link to the newly created clip. (ex. `clps.co/EkzeRLltl`)
- If the Twitch user is unintialized on Videogami we will return a message similar to `Initializing clipping for riotgames.` Clipping will then be enabled shortly (usually within a minute).
- If the Twitch user is offline we will return a `Stream Offline` message
- You can add a title to the clip using the `title` param (ex. `/api/clink/twitch/riotgames?title=Awesome%20Clip`)
