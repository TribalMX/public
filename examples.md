## Example Flow


### Registration
- A user "hologramgirl" registers with NightBot

`POST videogami.tv/api/v2/users?twitch=hologramgirl`

Example returned user object:
```
{
  "id": "56a5f12936cd3bc61fbb51c0",
  "local": {
    "displayName": "hologramgirl",
    "username": "hologramgirl",
    "profileImage": "https://static-cdn.jtvnw.net/jtv_user_pictures/hologramgirl-profile_image-f7171f4efdb8a345-300x300.jpeg",
    "profileColor": "#4FA6B7"
  },
  "stream": "56a5f12936cd3bc61fbb51c0",
  "twitch": {
    "id": "41799436",
    "username": "hologramgirl",
    "displayName": "Hologramgirl",
    "profileImage": "https://static-cdn.jtvnw.net/jtv_user_pictures/hologramgirl-profile_image-f7171f4efdb8a345-300x300.jpeg",
    "bio": "PC gaming on the daily.  Twitter @hologram_girl"
  }
}
```

### Clip Creation

- create a clip (and get the full object back)

`POST videogami.tv/api/v2/clips?user=hologramgirl&title=test%20clip2`

Example returned clip object:
```
{
  "__v": 0,
  "broadcast": "56a5f15ccb0b5e6902dd30de",
  "type": "clip",
  "vgobj": {
    "tracker": true,
    "screenshots": {
      "big": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.big.jpg",
      "medium": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.medium.jpg",
      "small": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.small.jpg"
    },
    "screenshot": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.medium.jpg",
    "gifs": {
      "fast": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.fast.gif",
      "normal": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.normal.gif"
    },
    "formats": {
      "mov": null,
      "smp4": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.small.mp4",
      "mp4": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.mp4",
      "flv": "https://www.vgtv.media/56a5f15e41402e28490caa32.290743398.40.original.mp4"
    },
    "live": true,
    "ready": false,
    "parent": {
      "end": 290743438,
      "start": 290743398,
      "stream": "56a5f12936cd3bc61fbb51c0",
      "pID": "56a5f15e41402e28490caa32"
    },
    "created": "2016-01-25T10:16:31.823Z",
    "tags": [],
    "description": "",
    "title": "test clip2",
    "user": "vdgami1",
    "_id": "56a5f5ff41402e28490caa35"
  },
  "author": {
    "id": "56a5f12936cd3bc61fbb51c0",
    "local": {
      "displayName": "hologramgirl",
      "username": "hologramgirl",
      "profileImage": "https://static-cdn.jtvnw.net/jtv_user_pictures/hologramgirl-profile_image-f7171f4efdb8a345-300x300.jpeg",
      "profileColor": "#4FA6B7"
    },
    "stream": "56a5f12936cd3bc61fbb51c0",
    "twitch": {
      "id": "41799436",
      "username": "hologramgirl",
      "displayName": "Hologramgirl",
      "profileImage": "https://static-cdn.jtvnw.net/jtv_user_pictures/hologramgirl-profile_image-f7171f4efdb8a345-300x300.jpeg",
      "bio": "PC gaming on the daily.  Twitter @hologram_girl"
    }
  },
  "_id": "56a5f5ff9d75764326684783",
  "slug": "test-clip2",
  "status": "public",
  "counts": {
    "plays": 0,
    "views": 0
  },
  "sid": "4yx7BJJtx",
  "url": "/h/4yx7BJJtx/test-clip2"
}
```

### Alternative Clipping Routes

-  You could also create clips through the other two routes
    - videogami.tv/api/c/hologramgirl
    - videogami.tv/api/clink/hologramgirl

### Link to a Clip
- link: `clip.links.full`
- short link: `clip.links.short`

### Displaying a Clip
All screenshots (`clip.vgobj.screenshot`) should be ready within seconds.

You should use our embedded clip player, as it will play the right clip 
formats to make sure clips are available as fast as possible, and also handles
displaying splash images, and relavent info about the clip. It also displays
loading messages if the clip is taking a while, and takes care of other 
intricacies.

Example: [http://videogami.tv/e/EJX4411Ke](http://videogami.tv/e/EJX4411Ke)

You can access the url of the embed clip player using `clip.links.embed`.

### Get User's Clips

- get all of hologramgirl's clips to display later

`GET http://videogami.tv/api/v2/users/hologramgirl/clips`

```
{
  "_total": 5,
  "clips": [...]
}
```
