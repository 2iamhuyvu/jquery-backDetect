# jquery-backDetect
---

jQuery backDetect is a jQuery plugin that is used to determine when a user clicks their browser's back button and fire a callback function before the browser actually jumps back a page. 

### Browser Support

| <img src="http://i.imgur.com/dJC1GUv.png" width="48px" height="48px" alt="Chrome logo"> | <img src="http://i.imgur.com/o1m5RcQ.png" width="48px" height="48px" alt="Firefox logo"> | <img src="http://i.imgur.com/8h3iz5H.png" width="48px" height="48px" alt="Internet Explorer logo"> | <img src="http://i.imgur.com/j3tgNKJ.png" width="48px" height="48px" alt="Safari logo"> |
|:---:|:---:|:---:|:---:|:---:|
| All ✔ | All ✔ | 9+ ✔ | All ✔ |

Note about IE: The 1x1.png is required for this plugin to work correctly in IE.  By default, this plugin looks for the 1x1.png in the same directory as the backDetect javascript file.  You can change the location of the 1x1.png by updating the frameDataSrc value:

``` html
	var backDetectValues = {
		frameLoaded: 0,
		...
		frameDataSrc: '1x1.png'
	};
```

### Basic Usage

``` html
<script src='backdetect.jquery.js'></script>
<script>
		$(window).load(function(){
			$('body').backDetect(function(){
				// Callback function
			});
		});
</script>
```

### Custom Options

You can set a delay intiate the back detect.  Very similar to setting the time in jquery animate:

``` html
<script src='backdetect.jquery.js'></script>
<script>
		$(window).load(function(){
			$('body').backDetect(function(){
				// Callback function
			});
		}, 1000); // <- 1 second delay
</script>
````

| Settings | Default Value | Description
| --- | --- | --- |
| delay | <pre>delay: 0</pre> |  The length of time it takes for the backDetect plugin to fire and monitor when a user hits the back button. 


### Licence 

                    __
            _,..,_ (, )
         .,'      `,./
       .' :`.----.': `,
      :   : ^    ^ :   ;
     :   :  6    6  :   ;
     :   :          :   ;
     :   :    __    :   ;
      :   `:'.--.`:'   ;
       `.  : o  o :  .'
   MIT  :   `----'   :  
        : .  :'`:  . :
        `.:.'    `.:.' 


