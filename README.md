# Bradley's Whiteboard
Notes, gists, fiddling.

## AvareX Contributions
**Production**: [Chart regions diagram](https://github.com/b-spatz/avarex-regions), [NEXRAD/layer opacity](https://github.com/apps4av/avarex/pull/53), [TFRs (Internet](https://github.com/apps4av/avarex/pull/61), bug fixes.  
**Personal**: &nbsp; &nbsp; [Stratux automagic PFD/AHRS roll-reversal](https://github.com/apps4av/avarex/pull/59), [full NOTAMs+LTAs (Internet)](https://github.com/apps4av/avarex/pull/93), [METARs tab non-Kxxx](https://github.com/apps4av/avarex/pull/94), Dynon HDX WiFi/GDL90 support, Android SD card support.  
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
2025-03-13 PR   Rej  NOTAMs: put longpress POI at top of listing by using ICAO vs. lat/long radius search from FAA/DINS
2025-04-13 Bug       Report map delays on 0.54 with Dynon HDX GDL90 provider; like issue #81; reported again 2025-09-25 0.64
2025-06-11 Bug       Report/confirm 0.53-0.55 no METAR/TAF, TFRs on longpres; asfter re-install troubleshooting and resolution
2025-09-18 Bug       Confirm mising FAA TAF source data; contact FAA, resolved next day.  See forum posting.
2025-09-26 Bug       Suggest internet-connectivity state via gpsInternal is weak vs. any GDL90 reception, etc.  See emails
2025-10-06           Plead not to waste time on AI integration, especially at expense of working NOTAMs, METARs, Internet errs, etc.
2025-11-29 Bug       Confirm/reproduce chart cycle 2512 gap between Raleigh/Richmond; not sure if fixed in 2513 or just 2513 
2025-12-04 PR   Rej  Restore NOTAMs after 3+ months inop (spinner asalink); report new API/integration missing NOTAMs
2025-12-07           Validate 0.68-bspatz with working NOTAMs, Dynon HDX ownship workaround; test Dynon non-GDL90 broadcasts (OK!)
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

<a target="_blank" href="http://www.apps4av.org/regions/">http://www.apps4av.org/regions/</a>  
https://avare.bubble.org/2413/  
&nbsp; &nbsp; https://avare.bubble.org/version.php, Avare (legacy): {[TFRs](https://avare.bubble.org/TFRs.zip),[conus](https://avare.bubble.org/conus.zip),[weather](https://avare.bubble.org/weather.zip)}.zip  
https://github.com/cyoung/stratux/blob/master/notes/app-vendor-integration.md  

## Insights
* ZK: "I am experimenting if I can make something without configs" (2025-01-04)
* ZK: "I have not flown for 3 months" (2025-03-11)
* ZK: "I do not need help"  "I do what I want to do" (2025-03-13)

## AvareX Obstacles
Corrected longitude distance by latitude: https://dartpad.dev/?id=f064399bd9fe84367189636b94f4d957  
Time-based, with lattitude correction:    https://dartpad.dev/?id=b241a96b3f07e3033278b81dc9d0eef9
