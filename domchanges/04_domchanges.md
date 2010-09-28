!SLIDE
# DOM Change Event

!SLIDE bullets
# The Problem

* Generic way to alter changes to the page
* Live events are just one part of the solution

!SLIDE
# Example

    @@@ javascript
    $(document).ready(function() {
      $('.important').text(function(i, old) {
        return old.toUpperCase() + "!!!";
      });
    });

    $('#warn-me').click(function(e) {
      $('.important', this).html("Don't do this");
    });

!SLIDE bullets
# Issues

* No DOM Events for this
* Custom Event systems are not enough
* No bubbles

!SLIDE
# Draft of a solution

    @@@ javascript
    $(document).ready(function() {
      $('a[rel=remote]').live('click', App.ajaxHandler);

      $(document).domchange();
    });

    $(".widget").domchange(function(e) {
      // do stuff if '.widget' is updated
    });

    $.fn.domchange = function(callback) {
      if ($.isFunction(callback)) {
        // register handler for $(this)
      } else {
        // check what changed, if it has
        // something that we listen for
        // and call its handler
      }
    }

    // override $.fn.html() or call from ajax.success

!SLIDE
# `jquery.domchange.js`
## coming soon

!SLIDE bullets
# Thank you! Questions?

* [Sprockets](http://getsprockets.org/)
* [Global Ajax Event Handlers](http://api.jquery.com/category/ajax/global-ajax-event-handlers/)
* [BlockUI plugin](http://jquery.malsup.com/block/)
* Me: [László Bácsi](http://github.com/lackac)
* [http://github.com/lackac/showoff-jquery-tricks/](http://github.com/lackac/showoff-jquery-tricks/)
