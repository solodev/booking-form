# booking-form
Scheduling is an important part of the online ecosystem. Not only does it play a huge role in almost every web and mobile application we use, scheduling is what makes the web most useful. Without the context of time, quality content is hard to decipher. Additionally, scheduling is a large part of sales and provides convenience to your website visitors and customers who can schedule appointments, phone calls, demos, tours, and more on your website with a date picker.

Some websites take scheduling to an entirely different level like Expedia.com where scheduling is everything. You'd like a flight that leaves at this day and time and comes back at this day and time, etc. For whatever the use, jQuery UI's date picker makes it easy to add any scheduling functionality to your website. In this article, [Solodev](https://www.solodev.com/) will walk you through building a booking (hotels, flights, rental cars, etc.) form for your website using [jQuery UI](https://jqueryui.com/).

## Tutorial

For detailed instructions, view Solodev's [How to Create a Booking Form with jQuery UI](https://www.solodev.com/blog/web-design/how-to-create-a-booking-form-with-jquery-ui.stml) article.

## Demo

Try out a working example on [JSFiddle](https://jsfiddle.net/solodev/y6mfba1s/).

## HTML

The booking form contains the following basic HTML markup.

```
<div>
<!-- Static navbar -->
<nav class="navbar navbar-default">
   <div class="container-fluid">
      <div class="navbar-header">
         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
         <span class="sr-only">Toggle navigation</span>
         <span>Book Now!</span>
         </button>
         <a class="navbar-brand" href="/">
         <img src="https://www.solodev.com/assets/email/logo.png" alt="Logo Solodev">
         </a>
      </div>
      <div id="navbar" class="navbar-collapse collapse">
         <form class="form book-now-form" role="form" id="widget_booking_form" name="widget_booking_form" >
            <input id="campaign" type="hidden" value="visitflagler_topNavWidget" name="campaign"> <input id="clone_id" type="hidden" value="278" name="clone_id">
            <div class="form-group">
               <label for="lodging">Book Your Stay</label> 
               <select class="form-control" id="lodgingID" name="lodgingID" placeholder="All Lodging">
                  <option value="103" selected="selected">
                     All Options
                  </option>
                  <option value="50">
                     Flights
                  </option>
                  <option value="9">
                     Hotels
                  </option>
                  <option value="21">
                     Cars
                  </option>
                  <option value="5">
                     Cruises
                  </option>
                  <option value="7">
                     Vacation Rentals
                  </option>
                  <option value="7">
                     Bundle Deals
                  </option>
               </select>
            </div>
            <!--check in element-->
            <div class="form-group">
               <label for="check-in">Check In</label> <!-- <input type="textfield" class="form-control" id="check-in" placeholder="12.20.2014"> -->
               <input type="text"  class="form-control" id="start-date" name="start-date" placeholder="mm/dd/yyyy">
            </div>
            <!--check out element-->
            <div class="form-group">
               <label for="check-out">Check Out</label> <!-- <input type="textfield" class="form-control" id="check-out" placeholder="12.27.2014"> -->
               <input type="text" class="form-control" id="end-date" name="end-date" placeholder="mm/dd/yyyy" >
            </div>
            <!--submit-->
            <div class="form-group">
               <button name="Submit" href="#" class="btn btn-sm btn-warning">Search</button>
            </div>
         </form>
      </div>
      <!--/.nav-collapse -->
   </div>
   <!--/.container-fluid -->
</nav>
<section class="ct_icon_box_section">
   <div class="container">
      <div class="ct-section_header ct-section_header--type2">
         <h2>
            Booking Form
         </h2>
         <div class="ct-section_header-description">
            Allow your users to book directly on your website with an intutive booking form using jQuery UI.
         </div>
         <div class="clearfix">
            &nbsp;
         </div>
         <div class="ct-section_header-separator">
            &nbsp;
         </div>
      </div>
     <div class="row">
         <div class="col-md-4 col-sm-6">
            <div class="ct-icon_box media">
               <div class="media-left">
                  <i class="fa fa-plane" aria-hidden="true"></i>
               </div>
               <div class="media-body">
                  <h3 class="media-heading">
                     Flights
                  </h3>
                  <div class="ct-icon_box-content">
                     Get the lowest rates on air fare!
                  </div>
               </div>
            </div>
         </div>
         <div class="col-md-4 col-sm-6">
            <div class="ct-icon_box media">
               <div class="media-left">
                  <i class="fa fa-building" aria-hidden="true"></i>
               </div>
               <div class="media-body">
                  <h3 class="media-heading">
                     Hotels
                  </h3>
                  <div class="ct-icon_box-content">
                     Find the best hotels for the best price!
                  </div>
               </div>
            </div>
         </div>
         <div class="col-md-4 col-sm-6">
            <div class="ct-icon_box media">
               <div class="media-left">
                  <i class="fa fa-car" aria-hidden="true"></i>
               </div>
               <div class="media-body">
                  <h3 class="media-heading">
                     Cars
                  </h3>
                  <div class="ct-icon_box-content">
                     Choose any car on the planet to get you there!
                  </div>
               </div>
            </div>
         </div>
         <div class="col-md-4 col-sm-6">
            <div class="ct-icon_box media">
               <div class="media-left">
                  <i class="fa fa-ship" aria-hidden="true"></i>
               </div>
               <div class="media-body">
                  <h3 class="media-heading">
                     Cruises
                  </h3>
                  <div class="ct-icon_box-content">
                     Let the finest cruise lines get you to your destination!
                  </div>
               </div>
            </div>
         </div>
         <div class="col-md-4 col-sm-6">
            <div class="ct-icon_box media">
               <div class="media-left">
                  <i class="fa fa-line-chart"></i>
               </div>
               <div class="media-body">
                  <h3 class="media-heading">
                     Vacation Rentals
                  </h3>
                  <div class="ct-icon_box-content">
                    Book your own destination with vacation rentals.
                  </div>
               </div>
            </div>
         </div>
         <div class="col-md-4 col-sm-6">
            <div class="ct-icon_box media">
               <div class="media-left">
                  <i class="fa fa-users" aria-hidden="true"></i>
               </div>
               <div class="media-body">
                  <h3 class="media-heading">
                     Bundle Deals
                  </h3>
                  <div class="ct-icon_box-content">
                     Create your own vacation bundle and find big savings!
                  </div>
               </div>
            </div>
         </div>
      </div>
   </div>
</section>
```

## CSS

All required CSS is included in the file booking-form.css

## JavaScript

The booking form uses the following JavaScript.

```
$( document ).ready(function() {
$( function() {
  var dateToday = new Date();
  var dates = $("#start-date, #end-date").datepicker({
    defaultDate: "+2d",
    changeMonth: true,
    numberOfMonths: 1,
    minDate: dateToday,
    onSelect: function(selectedDate) {
        var option = this.id == "start-date" ? "minDate" : "maxDate",
        instance = $(this).data("datepicker"),
        date = $.datepicker.parseDate(instance.settings.dateFormat || $.datepicker._defaults.dateFormat, selectedDate, instance.settings);
        dates.not(this).datepicker("option", option, date);
    }
  });
});
});

```
## External Includes

This tutorial contains the following third party resources.
```
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" rel="stylesheet">
<script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
<link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">
<link href="https://code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css" rel="stylesheet">
<script src="booking-form.js"></script>
<link href="booking-form.css" rel="stylesheet">
```
