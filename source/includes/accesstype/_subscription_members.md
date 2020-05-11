# Subscription Members
A subscription of type `group_access` supports multiple subscribers.

### Terminology
- <b>Primary Subcriber:</b> The subscriber who buys the subscription.
- <b>Subscription Members:</b> The members (identified as subscriber in AT) who have not bought subscription but are given access via it.
- <b>User limit:</b> The maximum number of members that can be added in a subscription. It is equal to the `user_limit` set in subscription_plan of said subscription.


## GET list of members

``` shell--request
  $ curl -H 'X-SUBAUTH: <api-auth-key>'\
  -X GET 'https://accesstype.com/api/v1/subscribers/<primary_subscriber_identity_provider>/<primary_subscriber_identity>/subscriptions/<subscription_id>/members'
```

```shell--response
{
  "members": [
    {
      "id": 1087,
      "name": 'foo',
      "created_at": "2019-08-14T09:43:57.557Z",
      "updated_at": "2019-08-14T09:43:57.557Z",
      "metadata": null,
      "cumulative_end_timestamps": {
        "standard_subscriptions_cumulative_end_timestamp": null,
        "campaign_subscriptions_cumulative_end_timestamp": null
      },
      "subscriber_identities": [
        {
          "provider": "email",
          "value": "foo@example.com"
        },
        {
          "provider": "quintype",
          "value": "123"
        }
      ]
    }
  ]
}
```

Used to get the list of subscription members for a particular subscription.

### Arguments
<dl>
  <dt><b>primary_subscriber_identity_provider</b> <small>required</small></dt>
  <dd> The identity provider for primary subscriber.(e.g. email) </dd>
  <dt><b>primary_subscriber_identity</b> <small>required</small></dt>
  <dd> The identity for primary subscriber.(e.g. the actual email address) </dd>
  <dt><b>subscription_id</b> <small>required</small></dt>
  <dd> The id of subscription for which you want to get list of members.</dd>
</dl>


## POST members to subscription

``` shell--request
  $ curl -H 'X-SUBAUTH: <api-auth-key>'\
  -X POST 'https://accesstype.com/api/v1/subscribers/<primary_subscriber_identity_provider>/<primary_subscriber_identity>/subscriptions/<subscription_id>/members -d {
	"member" : {
		"provider": "email",
		"identity": "jon@gmail.com",
		"name": "jon doe"
  }}'
```
```shell--response
{
  "members":
    {
      "id": 1087,
      "name": 'foo',
      "created_at": "2019-08-14T09:43:57.557Z",
      "updated_at": "2019-08-14T09:43:57.557Z",
      "metadata": null,
      "cumulative_end_timestamps": {
        "standard_subscriptions_cumulative_end_timestamp": null,
        "campaign_subscriptions_cumulative_end_timestamp": null
      },
      "subscriber_identities": [
        {
          "provider": "email",
          "value": "foo@example.com"
        },
        {
          "provider": "quintype",
          "value": "123"
        }
      ]
    }
}
```
Used to add a member to a particular subscription.

### Arguments
<dl>
  <dt><b>primary_subscriber_identity_provider</b> <small>required</small></dt>
  <dd> The identity provider for primary subscriber.(e.g. email) </dd>
  <dt><b>primary_subscriber_identity</b> <small>required</small></dt>
  <dd> The identity for primary subscriber.(e.g. the actual email address) </dd>
  <dt><b>subscription_id</b> <small>required</small></dt>
  <dd> The id of subscription for which you want to get list of members.</dd>
</dl>

### Request Body
It is an object with following fields:
<dl>
  <dt><b>provider</b> <small>required</small></dt>
  <dd> The identity provider for member to be added.(e.g. email) </dd>
  <dt><b>identity</b> <small>required</small></dt>
  <dd> The identity for member to be added.(e.g. the actual email address) </dd>
  <dt><b>name</b> <small>optional</small></dt>
  <dd> The name of member to be added.</dd>
</dl>


## DELETE members

``` shell--request
  $ curl -H 'X-SUBAUTH: <api-auth-key>'\
  -X DELETE 'https://accesstype.com/api/v1/subscribers/<primary_subscriber_identity_provider>/<primary_subscriber_identity>/subscriptions/<subscription_id>/members?ids[]=id1&ids[]=id2'
```

```shell--response
{}
```

Used to delete members from a particular subscription.

### Arguments
<dl>
  <dt><b>primary_subscriber_identity_provider</b> <small>required</small></dt>
  <dd> The identity provider for primary subscriber.(e.g. email) </dd>
  <dt><b>primary_subscriber_identity</b> <small>required</small></dt>
  <dd> The identity for primary subscriber.(e.g. the actual email address) </dd>
  <dt><b>subscription_id</b> <small>required</small></dt>
  <dd> The id of subscription for which you want to get list of members.</dd>
  <dt><b>ids</b> <small>required</small></dt>
  <dd> The array of member ids to be deleted.</dd>
</dl>
