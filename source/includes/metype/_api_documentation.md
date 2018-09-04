# API Documentation

## Accounts



### Create an account under an organization

```shell--request
curl -X POST \
  https://www.metype.com/api/v1/organizations/<organization_id>/accounts \
  -H 'Content-Type: application/json' \
  -d '{
	"authentication_token": <authentication_token>,
	"account_name": <account_name>,
	"account_email": <account_email>,
	"website_url": <website_url>
}'
```

```shell--response

{
  "id": 10,
  "config": null,
  "itsman_url": null,
  "name": "foo_1",
  "domains": [
      "http://localhost:3000"
  ],
  "profane_words": [],
  "profanity_configuration": {},
  "comments_limit": 4,
  "logo": null,
  "configurations": [
      {
          "id": 3,
          "name": "enable_image_uploads",
          "display_name": "Images/GIFs in comments"
      }
  ],
  "comment_reaction_sets": [],
  "page_reaction_sets": {
      "id": 10,
      "account_id": 10,
      "reaction_set": [
          {
              "id": 23,
              "account_id": 10,
              "reaction_id": 3,
              "shortcode": ":smiley:",
              "label": "Happy"
          },
          {
              "id": 24,
              "account_id": 10,
              "reaction_id": 4,
              "shortcode": ":cry:",
              "label": "Sad"
          },
          {
              "id": 25,
              "account_id": 10,
              "reaction_id": 5,
              "shortcode": ":sunglasses:",
              "label": "Cool"
          }
      ],
      "created_at": "2018-09-04T06:51:08.812Z",
      "updated_at": "2018-09-04T06:51:08.812Z"
  },
  "total_comments_count": 0,
  "is_paid_account": false
}
```

This endpoint creates an account under an organization

### HTTP Request

`POST https://www.metype.com/api/v1/organizations/:organization_id/accounts`

### Body Parameters
| Parameter | Required | Description |
|-----------|----------|-------------|
|authentication_token| Yes | Authentication token genereated by the metype team to access APIs |
|account_name| Yes | Name of the account |
|account_email| Yes | Email related to the account |
|website_url| Yes | URL of the website where metype will be used |

### Response codes
| Response code | Description |
|---------------|-------------|
|201|Account is created|
|401|When you pass a wrong organization credentials i.e., orgnization_id or auth_token|
|400|When required paramaters are not sent with API|
