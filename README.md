```
var API = window.Kano.apiClient({
  worldUrl:"http://ksworldapi-dev.us-west-1.elasticbeanstalk.com",
  resolve:true,
  log:true,
})
```

```
API.login({
  params: {
    username: "nectarsoft",
    password: "Chupand0nectar",
  },
  populate:{
    id: "user.id",
    ui: {
      followers: {
        list: "user.followers"
      },
      following: {
        list: "user.following"
      },
    }
  },
}).then(user => {
  console.log(user)  
}).catch(err => {
  console.error(err)
})
setTimeout( _ => {API.logout()}, 5000)
setTimeout( _ => {
  API.login({
    params: {
      username: "nectarsoft",
      password: "Chupand0nectar",
    },
    populate:{
      id: "user.id",
    },
  }).then(user => {
    console.log(user)
  }).catch(err => {
    console.error(err)
  })
}, 10000)
```
