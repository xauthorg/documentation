---
title: "Get User Subscriptions"
sidebar_position: 6
---

# Get User Subscriptions
The `/users/@me/subscriptions` endpoint retrieves the list of a user's subscriptions. This endpoint uses a `GET` request.

URL: `<ID>.xauth.ru/users/@me/subscriptions`<br/>
Method: `GET`<br/>

## Headers: 
1. `Content-Type: application/json`
2. `Authorization`
3. `Cookie`


## Response
If the operation is successful, the endpoint responds with a `200 OK` status code and a JSON object in the body that includes an array of the user's subscriptions. Each subscription object includes the following fields:

- `id`: The unique identifier of the subscription.
- `user_id`: The unique identifier of the user to whom the subscription belongs.
- `plan`: The name of the plan to which the user is subscribed.
- `start_date`: The date and time when the subscription started.
- `end_date`: The date and time when the subscription ends.
- `status`: The status of the subscription (for example, "active" or "expired").
- `created_at`: The date and time when the subscription was created.
- `updated_at`: The date and time when the subscription was last updated.


Example:
```json
[
    {
        "id": "uuid",
        "user_id": "uuid of user",
        "plan": "basic",
        "start_date": "datestring",
        "end_date": "datestring",
        "status": "active",
        "created_at": "datestring",
        "updated_at": "datestring"
    },
    {
        "id": "uuid",
        "user_id": "uuid of user",
        "plan": "premium",
        "start_date": "datestring",
        "end_date": "datestring",
        "status": "expired",
        "created_at": "datestring",
        "updated_at": "datestring"
    }
]
```