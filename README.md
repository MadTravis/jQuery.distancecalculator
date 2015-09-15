# jQuery Distance Calculator Plugin 1.0.0

This plugin makes it easy to calculate distance between 2 or more addresses with the help of Google Maps API. Good thing is, you can also add as many addresses  as You want to calculate the distance of a whole route. The distance values you get are in Miles. You can also change it to get as Kilometers. This plugin acts as a helper code for Google Map’s Direction Services API so that you don’t have to struggle understanding the API code.


**Step-1 :** Include required JS files in your <head> tag. Do not include jQuery if you already have included. Also please note that Google Maps API is also included.

    <script src="//code.jquery.com/jquery-1.11.3.min.js"></script>
    <script src="//code.jquery.com/jquery-migrate-1.2.1.min.js"></script>

    <script src="https://maps.googleapis.com/maps/api/js?sensor=false" type="text/javascript"></script>
    <script src="jquery.distancecalculator.js"></script>


**Step-2:** Create a result container if You want to display the distance value.

    <div id="result"></div>

or
**Step-2:** Create a input textbox element if You want to store the distance value in it.

    <input type="textbox" id="result" value="" />


**Step-3:** Add a Button on which we will write a "click" event and in that event we will get the total distance value.

    <button type="button" id="calculate">Calculate</button>


**Step-4:** Apply the Plugin code to the element You created. Put this code before closing `</head>` tag or before closing `</body>` tag depending on where You have included Your javascripts on your website.

    <script type="text/javascript">
    $(document).ready(function() {
        $("#calculate").click(function(event) {
            event.preventDefault();
            $("#result").distancecalculator({
                start_address: "Amalsad",
                end_address: "Surat",
                waypoints: ['Navsari, Gujarat, India',
                            'Sachin, Gujarat, India',
                            'Bhestan, Gujarat, India'],
                units: "mile",
                travel_mode: "DRIVING",
            });
        });
    });
    </script>

Here "#result" is the container element where the distance needs to be displayed or the textbox element in which the distance value needs to be stored.

**Below are the list of options supported by this plugin :**

 1. **start_address** - the address from where the journey starts
 2. **end_address** - the address to where the journey ends
 3. **waypoints** - the addresses which comes in the journey between
    *start_address* and *end_address*
 4. **units** - the units in which you want the distance value. Supported
    units : *mile* (default), *kilometer*
 5. **travel_mode** - in which travel mode the journey is going to be. This
    is based on the travel modes provided by Google Maps Api. Supported
    travel modes : *DRIVING* (default), *BICYCLING*, *TRANSIT*, *WALKING*
 6. **result_container_type** - this defines whether you  want to store the
    result into a "div" container or into the textbox as value.
    Supported container types : *container* (default), *textbox*

