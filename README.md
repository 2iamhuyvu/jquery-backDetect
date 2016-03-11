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

                      MMMMMMM           MMMMMMH 
                HMMMMM:::::::.MMMMMMMMMM:::::.TMM
              MMMI:::::::::::::::::::MMH::::::::TM
            MMIi::::::::::::.:::::::::::::::::::::MMMM
           MT::::.::::::::::::::::::::::::::::::.::=T.IMMM
         MMMi:::::::::::::::::::::::::::::::::::::::::::MT)MM
     MMMI.:::::::::::::::::::::::::::::::::::::::::::.:::M= MM
   XMXi::::::::::::::::::::::.:::::::::::::::::::::::::::::::=MM
   MMi::::::::::::::::::::::::::::::::::::::::::::::::::.::..:=MMM
  MM:MMT:::::::::.:::::::::::::::::.:::::::::::::::::::::::::::MiMM
   MMM::::::::::::::::::.::::::::::::::::::::::::::.::::::::::.TM.MM
   MMi::::::::::::::.::::::::::::::::::::::::::::::::::::::.:::.:: M
   MM:::.::::::::::::::::::::::::::::::::.:.:::::::::::::::::::::: XM
 MM:MT::.::::::::::::::::::::::::::::::::::::::::::::::::::::::::::XM
IMM:::.::::::::::::::::::::::::::::::::::: :::::::::::::::::::::::.=M
 MM::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: :::M
 XMT:::::::::::::::::::::: ::::::::::::::::: : ::::::::::::::::::: iM
   MiMi:::::::::: :::::::::::::::::::::::::::::::: ::::::::::::::.:IM
     M::::::HH::::::::::::::::::::::::::::::::::::::::::::::::::::: M
     MT:::::iM::::::::Hi:iXH:::ii::XH:::::::::::::.::::::::::::::.:.M
      MX:::::iMX:i::::iMi:iMH::XH::Mi:::::::::::::::::::::::::::::: M
        Mii::::HMH:::::iMH::MH=:MM=TMi::::::::::::::::::::::::::::::MM
          MMMMMMMMMMMXTi:MMHi:HMMIMMMMii::::::::::::::::::::::::::::XM
           XXOXMMT:. ::T= :IMMMMMMM=iXMii:::::::::::::::::::::::::: MM
            MMMH:::.:::::::.::::.::::.:XMi::::::::::::::::::::::::::MM
           XMM::.:.:..::..:.:.::.:.::: ::XMi::::::::::::::::::::::::MX
          XMMT::::.:.::.::::.::.::::::::.::XH:::::::::::::::::::::: M
          HMX::...:..::..:.:.::::::..... :::XX::::::::::::::.:::::. M
          MM:::....:::::.::::::..:::::.:..:::HX::::::::::::::::::::=M
          MX::::::::::::::::::::::..::::.:..::X::::::::::::::::::::IM
         XMI..  .:.::....:..::::.:: ::...::.:.MH:::::::::::::::::.: M
         MM:. ::..::....::.::::::....:.:...:..MT::.   ::::::::: :..IM
         MM=:::::.::.:::::..::::.: .::..::..::Mi:::::::::::::::::: MM
         MMI:::...:  .::..::::::.:::::::.::::TM:::::::::::::::::::=MO
          MH.: .::::.::.. .:::::iLMXX=::::.:.Mi::::::: ::::::::::.MM
          MX:.:..:: .:.:.:.: :MMM:::..:::::.HM:::: :::::::::::::.MM
          MM:::...::....: ::IMT:::.:...:.::.MT::::::: ::::::::: MM
           M=::..::::..:::MM:i:..::.:...: ::M:::: ::: ::::::::::MI
           MH::: :.:.: MMMM=:::.:.:...:....iM::: ::::::  ::::::LM
          MMMMT.::. ::TM:::::..::::::::.::.IM::::HH:::::::::::.MO
           MM:LM::T:MT.:: .......:....:.:: TMMiXMT.MH:::.::::.:M=
            M:. :::MMi:::MMMM=::::::.::..::=MMMMMMXMH:::.:::::MM
           XMI: :..::=MX  :M::.......:...:::.MXTHM MH:::.: :.XM
           MM XMMI IM    M   ................:: :MIIM:::::::MMO
            MMXXMILM  .ML.= :.:::....:.:..::.:..:::MMT:::::TMM
              MXMLMMMT::.:...:........ ....::.:.=.MMMM:::::MM
              MHM=:: :.:::...::::.:...:.....:: =MMM==Mi::::M
              MM=:::.......:.:.::.:.::...:.: ::  . ::=M:: MM
             MMi:=XMMMi::::...:::::.::.:::::::::..: ::Mi:=MT
            MM=:I::  :iMH==:::::.::.:::::::::::::::.::MT:XMT
           MT=:=MMMMMMM=HM::::.::::::MMT=Mi::::::..:::MI=MM
          M ::::::.=I= .MX:..: ::::.::MX::::.:::.:.  .XMMM
         M:MMMMMMM=.::::  ::.::...:.MMIM::.:::.::..::::M
                 M=:: : ::::.==XMMM:XMMM=:::.::.:.::::.M
                 M=.IMMM )X   M  MMMMMM=:::..::..:::.::M
                 MM  X  MMM:MMMMMMMMM=:::.:.:.. .:.::::M
   MIT            MIMMMMMMMMMMMMMMI::::::::.:::.:...:.:M
                MMMMMMMMMMMMMX:.   .:..::....:...:::.:iM
               MMMMMMMMMMI::::::.:.::...:....:.....:.:=M
           MMMMMMMMMI:::::.:.. :.::.::..........:..:..:M
            M=:  :..::..::.........::.......::.:.....: M
             MMMi::::::.:.:==MMMMMMMMMT:.:.:::..:::..: OM
               MM=::..: OMMMM         MMMT:::....:.::: :M
                M=::::MM                MMI:::........:OM
                 MMMMM                   MMH:::..::MMMMMM
                                          MMMMMMMMMMMMMMM
                                          Hakuna Matata


