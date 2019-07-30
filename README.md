# maya-color-tdskeys
Simple MEL scripts to quickly color the timeslider key ticks in maya. 
<br><br>

You can use these MEL scripts in different ways:
 - Load all the mel scripts as a shlef button.
 - or Just Load the single customColorKey.mel file to the shelf which provides a color picker to assign color each time.
 - or you can use by assigning seperate Hotkey for these MEL scripts.
 
**Quick Demo: Add as a Shelf Button Demo**
<br>
<br>
<img src="/resource/guide-1.gif">
<br>
Use this scrpt to change Key tick color to Blue
```
// Blue TDS Key
setKeyframe;
float $currentTime = `currentTime -q`;
displayRGBColor "timeSliderTickDrawSpecial" 0 0 255;   
selectKey -clear;
selectKey -add -k -t $currentTime;
keyframe -tds on;
```
Use this scrpt to change Key tick color to Green
```
// Green TDS Key
setKeyframe;
float $currentTime = `currentTime -q`;
displayRGBColor "timeSliderTickDrawSpecial" 0 255 0;   
selectKey -clear;
selectKey -add -k -t $currentTime;
keyframe -tds on;
```
Use this scrpt to change Key tick color to Red
```
// Red TDS Key
setKeyframe;
float $currentTime = `currentTime -q`;
displayRGBColor "timeSliderTickDrawSpecial" 255 0 0;   
selectKey -clear;
selectKey -add -k -t $currentTime;
keyframe -tds on;
```
or you can use this script to add custom color to the timeslider tdskey ticks.<br><br>
**Quick Demo: Custom Key Color Picker**
<br>
<br>
<img src="/resource/guide-2.gif">
```
setKeyframe;

float $TStime = `currentTime -q`;

colorEditor;
if (`colorEditor -query -result`) {
   float $rgb[];
   $rgb = `colorEditor -query -rgb`;
   displayRGBColor "timeSliderTickDrawSpecial" $rgb[0] $rgb[1] $rgb[2];
} else {
   print ("Operation Stopped\n");
}
   
selectKey -clear;
selectKey -add -k -t $TStime;

keyframe -tds on;
```
