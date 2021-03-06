# JavaScript Tracker for Pipes

This module includes the JavaScript tracker and the automatic
deployment package. 

## Architecture Overview

![architecture](https://github.com/pipes/pipesdata.com/blob/master/docs/images/pipes-js.png)

**The following 4 steps should be run to configure the tracker:**

1) The [pipes core module needs](https://github.com/pipes/pipes) to be deployed via Cloudformation
2) Run `make deploy` to deploy and build the JavaScript tracker
3) In the S3 bucket copy the content of the `tag.min.js` file
4) The content of the `tag.min.js` should be placed inside the `<header>` or
into Google Tag Manager `Custom Html`

**The following methods can be called to track your application:**

```js
// {...} means you can put anything you line inside the object - no fixed schema

// tracking of pageviews
pipes.page('name', {...})

// tracking of screens
pipes.screen('name', {...})

// tracking of events
pipes.track('name', {...})

// user identification
// should be called only once when the user logins, signups or registers
pipes.identity('userId', {...})

// tracking of link clicks 
pipes.trackLink(linkElement, 'name', {...})

//  tracking of form elements
pipes.trackForm(formElement, 'name', {...}) 

// deactivation of pipes
pipes.disable() 
```


