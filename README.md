# manage-users
A generic HTTP REST API to manage users.

# Operations

1. User
    - Create one
    - Create multiple
    - Fetch one
    - List multiple
    - Delete one
    - Delete multiple
    - Update one
2. User Settings
    - Get settings
    - Update settings

# API Definition

| Route                 | Methods  | Description                |
|-----------------------|----------|----------------------------|
| `/user`               | `POST`   | Create one or more users   |
| `/user`               | `GET`    | List all users             |
| `/user/{id}`          | `GET`    | Get a user                 |
| `/user/{id}`          | `PUT`    | Update a user              |
| `/user`               | `DELETE` | Delete multiple users      |
| `/user/{id}`          | `DELETE` | Delete one user            |
| `/user/{id}/settings` | `GET`    | Get the user's settings    |
| `/user/{id}/settings` | `PUT`    | Update the user's settings |

# Data Definition

## User

```json
{
  "resource": "/user",
  "status": "success",
  "pagination": {
    "current": "/users?request=123&page=2",
    "next": "/users?request=123&page=3",
    "prev": "/users?request=123&page=1",
    "first": "/users?request=123&page=1",
    "last": "/users?request=123&page=4"
  },
  "data": [
    {
      "id": "abc-123-defg-23412-asdaa",
      "status": "active",
      "name": {
        "first": "Tom",
        "last": "Hanks"
      },
      "email": "tom.hanks@example.com",
      "mobile": "919985999859",
      "created_date": "2019-04-02T23:43:21Z",
      "last_updated": "2019-04-02T23:43:21Z"
    }
  ]
}
```

## User settings

```json
{
  "resource": "/user/abc-123-defg-23412-asdaa/settings",
  "status": "success",
  "data": {
    "id": "abc-123-defg-23412-asdaa",
    "language": "en_UK",
    "communication_channels": [
      {
        "mode": "sms",
        "priority": 1
      },
      {
        "mode": "email",
        "priority": 2
      },
      {
        "mode": "phone",
        "priority": 0
      },
      {
        "mode": "fax",
        "priority": 0
      }
    ],
    "notifications_subscribed": [
      "marketing", "offers", "service_updates"
    ],
    "last_updated": "2019-04-02T23:43:21Z"
  }
}
```
