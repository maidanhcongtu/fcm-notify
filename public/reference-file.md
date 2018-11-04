Msg format: https://firebase.googleblog.com/2018/05/web-notifications-api-support-now.html
Msg format: https://firebase.google.com/docs/cloud-messaging/auth-server
Service_Worker_API: https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API


=== json format message full
POST https://fcm.googleapis.com/v1/projects/myproject-b5ae1/messages:send

Content-Type: application/json
Authorization: Bearer [accessTokenLogin]

{
  "message": {
    "webpush": {
      "notification": {
        "title": "Fish Photos 🐟",
        "body": "Thanks for signing up for Fish Photos! You now will receive fun daily photos of fish!",
        "icon": "https://cdn-images-1.medium.com/max/1600/1*HaAps8GidfAKdee7OrjZ2w.png",
        "image": "https://i0.wp.com/androidbash.com/wp-content/uploads/2016/08/FCM.png?resize=750%2C422",
        "data": {
          "notificationType": "fishPhoto",
          "photoId": "123456"
        },
        "click_action": "https://example.com/fish_photos",
        "actions": [
          {
            "title": "Like",
            "action": "like",
            "icon": "https://cdn4.iconfinder.com/data/icons/like-18/32/459-01-512.png"
          },
          {
            "title": "Unlike",
            "action": "unlike",
            "icon": "https://cdn4.iconfinder.com/data/icons/like-18/32/460-01-512.png"
          }
        ]
      }
    },
    "topic": "movie"
  }
}


=== json format message simple
POST https://fcm.googleapis.com/v1/projects/myproject-b5ae1/messages:send

Content-Type: application/json
Authorization: Bearer [accessTokenLogin]

{
  "message":{
    //"token" : "bk3RNwTe3H0:CI2k_HHwgIpoDKCIZvvDMExUdFQ3P1...",
    // or
    "topic" : "<Your topic>",
    "notification" : {
      "body" : "This is an FCM notification message!",
      "title" : "FCM Message",
      }
   }
}

======== Register topic
POST https://iid.googleapis.com/iid/v1/<REGISTRATION_TOKEN>/rel/topics/<TOPIC_NAME>
Authorization: key=<Your server key>
Content-Type: application/json

e.g.
https://iid.googleapis.com/iid/v1/nKctODamlM4:CKrh_PC8kIb7O...clJONHoA/rel/topics/movies
Content-Type:application/json
Authorization:key=AIzaSyZ-1u...0GBYzPu7Udno5aA


