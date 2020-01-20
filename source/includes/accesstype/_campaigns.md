# Campaigns

## LIST all Campaigns

```shell--request
$ curl -H "X-SUBAUTH: <your-auth-token>" https://www.accesstype.com/api/v1/campaigns.json
```
```shell--response
{
	"subscription_groups": [{
		"id": 9,
		"account_id": 2,
		"name": "Campaign",
		"description": "Campaign",
		"subscription_type": "campaign",
		"public": true,
		"created_at": "2019-12-12T09:26:05.418Z",
		"updated_at": "2020-01-03T05:33:05.130Z",
		"deleted_at": null,
		"preferred_identity_provider": "email",
		"metadata_fields": [],
		"currency": "INR",
		"target_amount": 1070200,
		"target_amount_validation_enabled": true,
		"assets": [],
		"display_assets": [],
		"subscription_plans": [{
				"id": 76,
				"subscription_group_id": 9,
				"duration_length": 1,
				"price_cents": 100000,
				"price_currency": "INR",
				"created_at": "2019-12-23T10:44:45.659Z",
				"updated_at": "2019-12-23T10:44:45.659Z",
				"duration_unit": "years",
				"description": "qwerty",
				"title": "Plan 2",
				"max_trial_period_length": null,
				"max_trial_period_unit": null,
				"recurring": false,
				"metadata": {},
				"deleted_at": null,
				"enabled": true,
				"trial_period_enabled": false,
				"supported_payment_providers": [],
				"assets": [],
				"display_assets": []
			},
			{
				"id": 49,
				"subscription_group_id": 9,
				"duration_length": 1,
				"price_cents": 5000,
				"price_currency": "INR",
				"created_at": "2019-12-12T09:33:39.024Z",
				"updated_at": "2019-12-12T09:33:39.024Z",
				"duration_unit": "weeks",
				"description": "Camp Door",
				"title": "Camp Door",
				"max_trial_period_length": null,
				"max_trial_period_unit": null,
				"recurring": false,
				"metadata": {},
				"deleted_at": null,
				"enabled": true,
				"trial_period_enabled": false,
				"supported_payment_providers": [],
				"assets": [{
					"title": "Asset Site",
					"metadata": {},
					"type": "site"
				}],
				"display_assets": [{
					"title": "Asset Site",
					"metadata": {},
					"type": "site"
				}]
			}
		]
	}]
}
```

This API will list out all campaign subscriptions that are set up for the account.
