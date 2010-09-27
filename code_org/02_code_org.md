!SLIDE
# Code Organization

!SLIDE
# jquery-1.4.js 6240 lines

!SLIDE
# There's gotta be a way to manage this!

!SLIDE
# Our take on it

    + public/
      + javascripts/
        - application.js
        - app.base.js
        - app.some_page.js
        - app.some_other_page.js
        - app.cool_widget.js
        - app.custom_control.js
        - jquery-1.4.js
        - jquery-ui-1.8.js
        - jquery.blockui.js
        - jquery.delay.js
        - ...

!SLIDE
# Use Sprockets or something

!SLIDE
# application.js with sprockets

    @@@ javascript
    //= require <jquery-1.4>
    //= require <jquery-ui-1.8>

    //= require <app.base>
    //= require <app.some_page>
    //= require <app.some_other_page>
