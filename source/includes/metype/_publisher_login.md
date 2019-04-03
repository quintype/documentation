# Publisher login

Metype lets publishers use their own authentication system to login user to metype. Metype uses shared key authentication method to implement this.

## Publisher login - Terminology
* `Shared key` - Shared key is used to generate JWT[https://jwt.io/].

## Publisher login - Prerequisites

* Sign up for an account @ www.metype.com.
* You will find all your accounts @ www.metype.com/admin if you are signed in.
* You will find the `shared key` in the `Embed Metype` Tab on your admin panel.

## Generating JWT

* Most of the languages have libraries to generate JWT.
* Expected user pay load:
  {
    'email': 'bathman@gotham.com',
    'name': 'batman',
    'avatar': 'https://gothamcity.com/batman-photo.jpg',
    'member-id': 123345,
  }
* `member-id` is the unqiue id to idenity member on your system.
* JWT generator should be used to generate token using `shared key` from metype, `payload` and `SHA-256` as the hashing algorithm.
