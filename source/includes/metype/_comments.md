# Comments

Metype provides a commenting system for your users to engage with your content.

## Terminology - Comments
* `Page`: It is the web page where you want to insert your commenting widget. This acts as a unique identifier for the commenting widget.
* `Comment Realm`: An instance of a commenting widget is a comment realm. There could be multiple comment realms in a page.
* `User`: A person who can login and use the commenting widget.
* `Author`: A person who is logged in and has commented.
* `Moderator`: A person who moderates comments on a property.
* `Admin`: A person who manages the property settings. As of now all moderators are admins.
* `Spam`: A comment can be automatically or manually marked as spam on metype. This would mean that the mdoerator does not want to see the comment appear again on his property.
* `Trash`: A comment can be trashed by a moderator. This means the comment can be visible again on his property.
* `Auto Moderation`: A moderation methodology in which comment can be automatically spammed by metype system.
* `Pre Moderation`: A moderation methodology in which the comment flows into a pending queue.
* `Profanity`: Dirty language used in comments.

## Installation - Comments
### Prerequisites
* Sign up for an account @ www.metype.com.
* You will find all your accounts @ www.metype.com/admin if you are signed in.
* You can find account specific information in the `Embed Metype` Tab.
* Please whitelist your website url in `Allow Multiple Domains` under `Settings` Tab of the admin panel if you are embedding the widget on a website other than the website url provided during account creation. If this is not done you will get an error called `This domain is not whitelisted` on the browser console when you are trying to embed the script. Visually you ll see the `metype` logo appearing and the widget not rendering on the browser.


### Javascript
```javascript
<!-- Initialization Script -->
<script type='text/javascript'>
  window.talktype = window.talktype || function(f) {
    if (talktype.loaded)
      f();
    else
      (talktype.q = talktype.q || []).push(arguments);
  };
</script>
<!-- Javascript to render the widgets -->
<script src='https://www.metype.com/quintype-metype/assets/metype.js'></script> -->
```
* Setup the initialization script in the `<head>` section in case of a website.
If you have already done this to integrate other widgets please ignore this step.
Please find the script on the right in the Scripts tab.


```javascript
<!-- Commenting Widget embed code. Html Element with the necessary attributes.
The color and font are configurable according to your liking -->
<div id='metype-container'
     class='iframe-container'
     data-metype-account-id='XXXXX' <!-- Add your account ID here -->
     data-metype-host='https://www.metype.com/'
     data-metype-primary-color='#0987d5' <!-- Majority color of the widget can be customised -->
     data-metype-bg-color='#ffffff' <!-- Background color of the widget can be customised -->
     data-metype-font-color='#4a4a4a' <!-- Font color of the widget can be customised -->
     data-metype-comment-widget-id="comment-widget-x1"> <!-- Unique Id if you want to embed multiple comment widgets in the same page -->
</div>
<script type='text/javascript'>
  var metypeContainer = document.getElementById("metype-container"),
    page_url = metypeContainer.getAttribute("data-metype-page-url");

  //You can change the page url incase of infinite scroll to render different widgets.
  metypeContainer.setAttribute('data-metype-page-url', page_url || window.location.href);

  // The rest of the commands are for metype to render the widget as an iframe
  metypeContainer.setAttribute('data-metype-window-height', window.innerHeight);
  metypeContainer.setAttribute('data-metype-screen-width', window.screen.width);
  talktype(function() {
    talktype.commentWidgetIframe(metypeContainer);
  });
</script>
```
* Setup the embed code for the commenting widget at the position you need to embed.
Please find the script on the right in the Scripts tab.


## Comments Count API

* The total comments count can be fetched for a page or multiple pages using the api call on the shell.
The page ids should be comma seperated and base64URI encoded(first uri encode followed by base64 encoding the uri encoded url). A maximum of 10 page urls can be passed.

```shell--request
GET https://www.metype.com/api/v1/accounts/:account_id/pages?page_ids=base_64_uri_enc_string1,base_64_uri_enc_string2
```
```shell--response
[
    {
        "url": "http://www.example.com/1",
        "comments_count": 1
    },
    {
        "url": "http://www.example.com/2",
        "comments_count": 1
    }
]
```
