# Bradley's Whiteboard
Notes, gists, fiddling.

## AvareX Contributions
```
Date       Type Prod Description
2024-09-12 Map  Y    Map of new chart/data "regions" per ZK bboxes; from Suzanne C forum issue; ZK adds to Download i button
                     Share leaflet code that produces map PNGs with ZK
2025-01-07 Bug  Y    Find CSUP extra/old pages bug (X235): report Aeronav, fixed AvareX 1/14
2025-01-11 POC       Obstacles "radius": Dart to correct AvareX delta-longitude due to latitude
2025-01-11 POC       Obstacles "radius": Dart to use time-based "radius" using speed and latitude
2025-01-12           Create Github, Gist accounts
2025-01-13           Install Flutter/Android_Studio tooling for Windows platform, target=Android/Windows
2025-01-13           First compile/run of AvareX
2025-01-13 Bug  Y    First code bug: dev/bootstrap main.db crash; ZK fix next day
2025-01-16 POC  N    Develop/email NOTAM mod to limit to just airport long-ressed... (radius=2nm instead of 20)
2025-01-16 PR   Y    Develop/submit NEXRAD opacity fix (0.5); PR accepted next day; ZK changes to 0.8 later that day
2025-01-18 Bug  Y    Report db locked bug, Zk regression from main.db bug on 13th; ZK fixes
2025-01-31           Report distance ring labels positioned "behind you" if track-up southbound-ish; no response
2025-02-22 PR   ?    Nexrad opacity slider; ZK denies PR but integrates idea: opacity sliders for every layer
2025-02-27 PR        Stratux automagic reverse PFD/AHRS roll orientation
2025-02-27 Bug  Y    Report missing break in gdl90/message_factory.dart (between uplink/ownship); ZK fixes
2025-02-28 PR   Y    TFR (Internet) quick fix due to FAA tfr3 breaking things; transition to XML-based API
2025-03-05 Map       Place chart/data region map code (Leaflet) here on Github
2025-03-13 PR        NOTAMs: put longpress POI at top of listing by using ICAO vs. lat/long radius search from FAA/DINS
```
Column `Prod` means whether this contribution made it into production (was accepted).
  
## To-Do
* [done] Flutter/Android_Studio tooling, oh my
    * [done] Compile/run from source
* [done] Collect PR offers from ZK emails

## Requests
* 2024-12-09
   * [POC complete] Nexrad opacity, configurable
      * ZK: "Only overlays support transparency, tiles don't. Mesonet is tiles while GDL90 nexrad is an overlay. If you can find a solution let me know. It's clearly stated in flutter map documentation"
      * 1-line change using Flutter Opacity() widget
   * [POC complete] NOTAMs (long-press): reduce clutter: put long-press location at top, or reduce list to just long-press
      * ZK: "There are technical issues. How FAA provides data. I have not heard anyone else complain about it so not working on it soon"
      * [POC complete] reduce radius from 20 nm to 2: effectively confine list of airport of long-press
         * confirmed: using geo radius search via HTTP post on https://www.notams.faa.gov/dinsQueryWeb/
      * [POC complete] make configurable via optional user.db setting (so no config UI needed from devs)
   * [POC Complete] Obstacles
      * ZK: "Send a PR. I will consider change"
      * [partial] document criteria: 15 sec updates, withon 200 feet altitude, 0.1 degrees lat/log (6nm at equator) [now 0.4?]
      * [POC complete; dart Gist] correct search area longitude for increasing latitude
      * [POC complete; dart Gist] use time to obstacle (speed-based) to set distance, correct search area longitude for increasing latitude
   * GeoJSON (user-provided): support _color property of feature to set color. exclude _* vars from labels
      * ZK: "if you create an issue on GitHub I will get to it"

http://www.apps4av.org/regions/  
https://avare.bubble.org/2413/  

## Insights
* ZK: "I am experimenting if I can make something without configs"

## AvareX Obstacles
Corrected longitude distance by latitude: https://dartpad.dev/?id=f064399bd9fe84367189636b94f4d957  
Time-based, with lattitude correction:    https://dartpad.dev/?id=b241a96b3f07e3033278b81dc9d0eef9
