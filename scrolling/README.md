scrolling
=========

### waypoints

*[http://imakewebthings.com/jquery-waypoints/](http://imakewebthings.com/jquery-waypoints/)*

- determines your location on page relative to content

##### implementing example

    // listen to the waypoint event
    $('body').delegate('.waypoint', 'waypoint.reached', function(event, direction) {
      var $active = $(this);

      if (direction === "up") {
        // think ahead
        $active = $active.prev();
      }
      if (!$active.length) $active = $active.end();

      // set the element to active
      $('.section-active').removeClass('section-active');
      $active.addClass('section-active');

      // set the coresponding links active
      $('.link-active').removeClass('link-active');
      $('a[href=#'+$active.attr('id')+']').addClass('link-active');
    });

    // set waypoints
    $('.waypoint').waypoint({ offset: '30' });
