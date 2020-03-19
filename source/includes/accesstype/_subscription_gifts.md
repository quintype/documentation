# Subscription Gifts

## POST Preview a Subscription for gifting
```shell--request
curl -H "X-SUBAUTH: <auth-token>" -H "Content-Type: application/json" -X POST https://www.accesstype.com/api/v1/subscribers/<provider>/<identity>/subscriptions/preview.json -d '{
  "recipient_subscriber": {
    "recipient_identity_provider": "email",
    "recipient_identity": "friend@example.com"
  },
   "subscription": {
        "notes": "enter your notes",
        "subscription_type": "standard",
        "subscription_plan_id": 2118,
        "coupon_code": "UAT",
        "payment": {
            "payment_type": "razorpay",
            "amount_cents": 14400,
            "amount_currency": "INR",
            "payment_token": "pay_BWpQWQcLLK3L37"
        },
        "metadata": {
            "mobile_number": "7639817688"
        }
    },
    "alternate_provider": "email",
    "alternate_identity": "hey@quintype.com",
    "attempt_token": "WnwxA2AVrE3xqcDUqrSb3sNm"
}'
```

```shell--response
{
    "subscription": {
        "id": null,
        "subscriber_id": 2454,
        "subscription_plan_id": 10,
        "created_at": null,
        "updated_at": null,
        "assets": [],
        "start_timestamp": "2020-03-18T11:29:12.926Z",
        "end_timestamp": "2020-03-25T11:29:12.926Z",
        "deleted_at": null,
        "payment_id": null,
        "metadata": {
            "mobile_number": "7639817688"
        },
        "external_id": null,
        "trial_period_length": null,
        "trial_period_unit": null,
        "campaign_id": null,
        "plan_amount_cents": 1000,
        "plan_amount_currency": "INR",
        "duration_unit": "weeks",
        "duration_length": 1,
        "plan_name": "plan inr",
        "plan_description": "plan inr",
        "group_name": "TEST",
        "group_description": "test",
        "subscription_type": "standard",
        "plan_occurrence": "One Time",
        "subscription_attempt_id": 2781,
        "renewal_reminder_sent_date": null,
        "dynamic_assets": {},
        "coupon_discount_id": null,
        "notes": null,
        "account_id": null,
        "subscription_group_id": 5,
        "preferred_identity": {
            "provider": "email",
            "value": "friend@example.com"
        },
        "active": true,
        "payment_amount": "10.00",
        "payment_amount_cents": 1000,
        "payment_amount_currency": "INR",
        "payment_type": "paypal",
        "payment_token": null,
        "renewable": true,
        "status": "active",
        "expired": false,
        "coupon_code": null,
        "recurring": false,
        "cancelled_at": null,
        "next_payment_due_date": null,
        "cancelled": false,
        "in_grace_period": false,
        "invoices": [],
        "subscriber_name": null,
        "discount_detail": {},
        "referrer": null,
        "gifter": null,
        "created_by": null,
        "subscriber": {
            "id": 2454,
            "name": null,
            "created_at": "2020-03-18T11:29:12.741Z",
            "updated_at": "2020-03-18T11:29:12.741Z",
            "metadata": null,
            "cumulative_end_timestamps": {
                "standard_subscriptions_cumulative_end_timestamp": null,
                "campaign_subscriptions_cumulative_end_timestamp": null
            },
            "subscriber_identities": [
                {
                    "provider": "email",
                    "value": "friend@example.com"
                }
            ]
        },
        "expires_in_days": 7,
        "in_trial_period": false
    },
    "attempt_token": "EVcXP57CjzE6t2yumRHQ44gf",
    "external_reference_id": null,
    "custom_message": null
}
```
It returns a preview for a Subscription, without creating a new subscription.
For a successful subscription, it also returns an `attempt_token`.

Please note that **recipient subscriber should not be same as the gifter**.

## POST Create a Subscription for gifting

```shell--request
curl -H "X-SUBAUTH: <auth-token>" -H "Content-Type: application/json" -X POST https://www.accesstype.com/api/v1/subscribers/<provider>/<identity>/subscriptions.json -d '{
  "recipient_subscriber": {
    "recipient_identity_provider": "email",
    "recipient_identity": "friend@example.com"
  },
   "subscription": {
        "notes": "enter your notes",
        "subscription_type": "standard",
        "subscription_plan_id": 2118,
        "coupon_code": "UAT",
        "payment": {
            "payment_type": "razorpay",
            "amount_cents": 14400,
            "amount_currency": "INR",
            "payment_token": "pay_BWpQWQcLLK3L37"
        },
        "metadata": {
            "mobile_number": "7639817688"
        }
    },
    "alternate_provider": "email",
    "alternate_identity": "hey@quintype.com",
    "attempt_token": "WnwxA2AVrE3xqcDUqrSb3sNm"
}'
```
```shell--response
{
  "subscription": {
    "id": 104273,
    "subscriber_id": 101788,
    "subscription_plan_id": 19781,
    "created_at": "2020-01-20T09:09:15.988Z",
    "updated_at": "2020-01-20T09:09:15.988Z",
    "assets": [],
    "start_timestamp": "2020-01-20T09:09:15.943Z",
    "end_timestamp": "2020-01-27T09:09:15.943Z",
    "deleted_at": null,
    "payment_id": 104440,
    "metadata": {
      "mobile_number": "8892665215"
    },
    "external_id": null,
    "trial_period_length": null,
    "trial_period_unit": null,
    "campaign_id": null,
    "plan_amount_cents": 0,
    "plan_amount_currency": "INR",
    "duration_unit": "weeks",
    "duration_length": 1,
    "plan_name": "Gold - 3 months",
    "plan_description": "Price 0",
    "group_name": "Gold",
    "group_description": "Gold plan",
    "subscription_type": "standard",
    "plan_occurrence": "One Time",
    "subscription_attempt_id": 184597,
    "renewal_reminder_sent_date": null,
    "dynamic_assets": {},
    "coupon_discount_id": null,
    "notes": null,
    "subscription_group_id": 8686,
    "preferred_identity": {
      "provider": "email",
      "value": "friend@example.com"
    },
    "active": true,
    "payment_amount": "0.00",
    "payment_amount_cents": 0,
    "payment_amount_currency": "INR",
    "payment_type": "sponsored",
    "payment_token": null,
    "renewable": false,
    "status": "active",
    "expired": false,
    "coupon_code": null,
    "recurring": false,
    "cancelled_at": null,
    "next_payment_due_date": null,
    "cancelled": false,
    "in_grace_period": false,
    "invoices": [
      {
        "id": 71623,
        "sequenced_invoice_number": "Kihn28241",
        "base_price": "0",
        "amount_cents": 0,
        "amount_currency": "INR",
        "created_at": "2020-01-20T09:09:16.117Z",
        "amount_after_discount_before_tax": "0",
        "discount_details": {},
        "invoice_taxes": {
          "Milagros": {
            "percentage": "9.0",
            "amount": "0",
            "currency": "INR"
          },
          "Xiao": {
            "percentage": "9.0",
            "amount": "0",
            "currency": "INR"
          },
          "Dwight": {
            "percentage": "9.0",
            "amount": "0",
            "currency": "INR"
          },
          "Ardath": {
            "percentage": "9.0",
            "amount": "0",
            "currency": "INR"
          }
        },
        "round_off": "0",
        "external_payment_id": null,
        "downloadable": false
      }
    ],
    "subscriber_name": null,
    "discount_detail": {},
    "referrer": null,
    "gifter": {
      "id": 101663,
      "name": "Gifter",
      "email": "gifter@example.com"
    },
    "created_by": null,
    "subscriber": {
      "id": 101788,
      "name": null,
      "created_at": "2020-01-20T09:09:14.557Z",
      "updated_at": "2020-01-20T09:09:14.557Z",
      "metadata": null,
      "cumulative_end_timestamps": {
        "standard_subscriptions_cumulative_end_timestamp": "2020-01-27T09:09:15.943Z",
        "campaign_subscriptions_cumulative_end_timestamp": "2020-01-27T09:09:15.943Z"
      },
      "subscriber_identities": [
        {
          "provider": "email",
          "value": "friend@example.com"
        }
      ]
    },
    "expires_in_days": 7,
    "in_trial_period": false
  }
}
```

This API can be used to create a subscription and gift it to a `recipient_subscriber`.
`recipient_subscriber` details are required.
It returns a Subscription Object in response

## LIST Subscriptions gifted by a user

```shell--request
$ curl -H "X-SUBAUTH: <auth-token>" https://www.accesstype.com/api/v1/subscribers/<provider>/<identity>/subscription_gifts.json

```
```shell--response
{
 "subscriptions":[
  {
     "id":713,
     "subscriber_id":453,
     "subscription_plan_id":16,
     "created_at":"2017-10-30T10:55:42.201Z",
     "updated_at":"2017-10-30T10:55:42.201Z",
     "assets":[

     ],
     "start_timestamp":"2017-10-30T10:55:42.176Z",
     "end_timestamp":"2017-11-13T10:55:42.176Z",
     "deleted_at":null,
     "payment_id":668,
     "metadata":{
        "Name":"Sample User",
        "Address":"Sample add",
        "Phone Number":"1111111111"
     },
     "external_id":null,
     "trial_period_length":null,
     "trial_period_unit":null,
     "coupon_code":null,
     "subscription_group_id":21,
     "preferred_identity":{
        "provider":"email",
        "value":"sample@gmail.com"
     },
     "group_name":"Sub Group 1",
     "plan_name":"Sub Plan 1",
     "duration_length":2,
     "duration_unit":"weeks",
     "subscription_type":"individual",
     "active":true,
     "payment_amount":"0.00",
     "payment_type":"manual",
     "renewable": true
    }
  ]
}
```
