# maya-color-tdskeys
Simple MEL scripts to quickly color the timeslider key ticks in maya. 

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
