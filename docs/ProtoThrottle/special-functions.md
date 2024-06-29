---
title: Special Functions
---
# ProtoThrottle User Manual ![](img/pt-logo.png){align=right style="height: 75px; margin-top:0px; margin-bottom: 0px"}

## Special Function: Brake Test

|     | Navigation |     |
|----:|:----------:|:----|
|None :material-arrow-right-drop-circle:<br><br>[Return to Main Screen](manual.md#main-screen) :material-checkbox-marked-circle:|<pre class="screen">LCD<br> SCREEN <br></pre>|:material-arrow-up-circle: None<br><br>:material-arrow-down-circle: Begin Brake Test Function|

**What is a brake test?** (Note: this is a simplified explanation of train air brakes)
After an engine couples up to a string of cars and the air hoses are connected, the engineer and conductor will usually
perform a brake test to ensure there are no air leaks, the pressure drop reaches the end of the train, and the air pressure
through the brake lines is adequate. Each car in the train has a reserve air tank that is pressurized to apply the brakes.
When the air pressure through the train line is approximately 90 psi, a value on each car closes off the reserve air tank
thus keeping the car free rolling. When the train line air pressure is ***reduced*** it causes the valve in each car to open
releasing the pressurized air from the reserve tank thus applying the brakes. This process is called a “failsafe” because
if the train loses it’s train line pressure the train will automatically brake. A brake test is performed when the engineer
reduces the train line pressure by approximately 20-26 psi thus applying the brakes and the conductor visually confirms
the brakes being applied. To simulate this test with the ProtoThrottle, follow the steps below (**note:** the time is user-variable):

1. Release the brake handle and watch the pressure build to it’s maximum of approximately ~89-91 psi (air is simulated increasing into the train line; compressor sound is playing).

2. Perform the brake test by moving the brake handle to the right. A 26 psi reduction will show on the gauge. (air is simulated reduced through the train line; air letoff sound plays).

1. Release the brake handle and let the pressure return to the maximum (compressor sound starts; once ~90 psi is reached the compressor will silence).

1. Press the “Return to Main Screen” key to return the throttle to normal operation and the train can now be moved.
