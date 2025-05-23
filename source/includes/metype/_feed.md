# Activity Feed

Metype provides a feed to represent audience activity on your site.

## Terminology - Feed
* `Page`: It is the web page where you want to insert your commenting widget.
* `User`: A person who can login and use the feed widget.
* `Author`: A person who is logged in and has commented.

## Installation - Feed
### Prerequisites
* Sign up for an account @ [www.metype.com](https://www.metype.com).
* You will find all your accounts @ [www.metype.com/admin](https://www.metype.com/admin) if you are signed in.
* You can find account specific information in the `Embed Metype` Tab.


### Javascript
* Setup the initialization script in the `<head>` section in case of a website.
If you have already done this to integrate other widgets please ignore this step.
Please find the script in the shell on the right in the shell.

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

* Setup the embed code for the feed widget at the position you need to embed.
Please find the script with detailed comments on the right in the shell.

```javascript
<!-- Feed Widget embed code. Html Element with the necessary attributes.
The color and font are configurable according to your liking -->
<div id='feed-metype-container'
     class='feed-iframe-container'
     data-metype-account-id='XXXXX'
     data-metype-host='https://www.metype.com/' <!-- Add your account ID here -->
     data-metype-publisher='John Doe' <!-- Add the name that needs to appear on the feed here -->
     data-metype-primary-color='#0987d5' <!-- Majority color of the widget can be customised -->
     data-metype-secondary-color='#ffffff'> <!-- Background color of the widget can be customised -->
  <!-- This is a clickthru button on the right side of the web page. A click of this will open the feed. -->
  <div id='metype-clickthru' class='metype-clickthru' onClick="talktype.toggleButton()"></div>

  <!-- This is to close the feed -->
  <div class="metype-feed-slide-icon" id="metype-feed-slide-icon" onclick="talktype.slideButton()"></div>
</div>

<script type='text/javascript'>
  // This is required to render the iframe.
  talktype(function() {
    talktype.feedWidgetIframe(document.getElementById('feed-metype-container'));
  });
</script>
```
