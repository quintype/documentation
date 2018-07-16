# Token Authorization
Metype supports token based authorization to access the APIs

## Supported social login providers:
* Google
* Facebook

## Fetching metype Token
* Fetch access token for the respective social login provider using the followin API.
* Supported provider values:
  * `facebook`
  * `google_auth2` for google
* If the request succeeds API responds with 200 and the token is passed back as part of headers with header value `X-Metype-Token`

```shell
curl -I GET \
  'http://localhost:3000/users/auth/:provider/callback?access_token=XXXXXXXXXXXXX'
```

## Using Metype Token
* Once a token is produced using the above API. It can be used to access data as a user.
* Any metype API can be accessed as user by passing the `token` as valye and `X-Metype-Token` as key in headers.
* A current user API as an example is illustrated here.

```shell
curl -X GET \
  http://localhost:3000/api/v1/current_user \
  -H 'X-Metype-Token: x_xxxxxxxxxxxxxxxxx'
```

