# Arduino To Unity tutorial for Mac
For our research and design class Jonathan Kievits and I got to play around with the arduino. Here is a very simple way to get Parallax 2-AXIS Input to Unity.

Do you have a Windows computer instead of a Mac??? check out <a href="https://github.com/JonathanKievits/Arduino">Jonathan Kievits'</a> github page!!

we recommend using <a href="www.codebender.cc">Codebender</a> for the arduino code!
use <a href="https://youtu.be/Sfwl0_sm6Yo">this</a> to connect the controller like we did.

On codebender put this code:
<pre>
<code>
void setup()
{
 Serial.begin(38400);
}
void loop()
{
 float values[] = {analogRead(0),analogRead(1)};
 Serial.flush();
 Serial.print(map(values[0],0,1023,0,359));
 Serial.print(",");
 Serial.print(map(values[1],0,1023,0,359));
 Serial.println();
 delay(40);
}
</code>
</pre>

then open the <a href="https://github.com/danivdwerf/Arduino-Unity_tut/blob/master/Assets/Test_Script.cs">unity code</a>

the /dev/tty.usbmodem1421 may be different for your mac device, so check your path on codebender

put this script on a cube and use the controller to move it

this should get you started!
