# Bradley's Whiteboard
Notes, gists, fiddling.  

## To-Do
* [done] Flutter/Android_Studio tooling, oh my
    * [done] Compile/run from source
* [done] Collect PR offers from ZK emails

## Requests
* 2024-12-09
   * Nexrad opacity, configurable
      * ZK: "Only overlays support transparency, tiles don't. Mesonet is tiles while GDL90 nexrad is an overlay. If you can find a solution let me know. It's clearly stated in flutter map documentation"
   * [POC complete] NOTAMs (long-press): reduce clutter: put long-press location at top, or reduce list to just long-press
      * [POC complete] reduce radius from 20nm to 2: effectively confine list of airport of long-press
      * make configurable via optional user.db setting (so no config UI needed from devs)
      * ZK: "There are technical issues. How FAA provides data. I have not heard anyone else complain about it so not working on it soon"
   * Obstacles
      * [partial] document criteria: 15 sec updates, withon 200 feet altitude, 0.1 degrees lat/log (6nm at equator) [now 0.4?]
      * [POC complete; dart Gists] correct search area longitude for increasing latitude
      * ZK: "Send a PR. I will consider change"
   * GeoJSON (user-provided): support _color property of feature to set color. exclude _* vars from labels
      * ZK: "if you create an issue on GitHub I will get to it"

http://www.apps4av.org/regions/  
https://avare.bubble.org/2413/  

## Insights
* ZK: "I am experimenting if I can make something without configs"

## AvareX Obstacles
Corrected longitude distance by latitude: https://dartpad.dev/?id=f064399bd9fe84367189636b94f4d957  
Time-based, with lattitude correction:    https://dartpad.dev/?id=b241a96b3f07e3033278b81dc9d0eef9
