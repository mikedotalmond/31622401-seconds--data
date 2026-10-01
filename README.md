# 31622401-seconds--data

This data is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).


----

This repository contains 366 JSON files, one for every day of 2016, with data to represent every second of the year.

See [mikedotalmond.dev/projects/31622401-seconds](http://mikedotalmond.dev/projects/31622401-seconds) for more information on the project.


### Data format

Each day of data consists of a `status` and `delete` array with 86400 (60 x 60 x 24) entries each. Errors and server downtime are recorded as `-1` in the outputs, otherwise the values within the arrays should be positive integers.

Days start at 00:00:00 UTC and end with 23:59:59 UTC (no timezone offsets)

```json
{
  "error":"",
  "time: "",
  "status": [...],
  "delete": [...]
}
```

```haxe
typedef BufferData = {
 
 /** A message, or null if data contains no errors */
 @:optional var error:String;
 
 /** A number representing the milliseconds elapsed between 1 January 1970 00:00:00 UTC and the given date */
 var time:String;
 
 /** Array of integer values, one per second for the day. Represents number of status events recorded per-second */
 var status:Array<Int>;
 
 /** Array of integer values, one per second for the day. Represents number of delete events recorded per-second */
 var delete:Array<Int>;
}
```
