# iso\_8601\_erl

## Introduction

This project was started because I needed the ISO Week Number for a given date and I wanted it in Erlang.
Since the calendar module in the stdlib-1.17.1 application of Erlang/OTP R14B did not provide this functionality, I decided to write it myself.

## Rules

The following rules are used:

* Week 01 is the week with the year's first Thursday in it.
* Weeks start with Monday.
* Monday is assigned the number 1.
* Weeks ranges from 01 to 52 or 53 within a year.

## Implementation

The module iso_8601.erl currently contains functions for computing the week number only. The [standard covers][iso8601covers] far more than this. This module can be extended later, for now I needed only this.

The implementation is based on the calendar module of the stdlib application of Erlang/OTP.

The implementation was tested successfully with eunit using the tests file.

## Examples

<pre>
2010, 11, 19 -> "2010-W46-5"
2004, 12, 31 -> "2004-W53-5"
2000, 01, 01 -> "1999-W52-6"
</pre>

Where the format "YYYY-Www-D" is used.

## References

* [ISO Week Date Calendar][calendar] is a nice calendar.
* [ISO Week Date on Wikipedia][iwdwiki] contains some explanation.

[iso8601covers]: http://www.iso.org/iso/date_and_time_format#what-iso-8601-covers "What ISO 8601 covers"
[iwdwiki]: http://en.wikipedia.org/wiki/ISO_week_date "ISO Week Date on Wikipedia"
[calendar]: http://www.personal.ecu.edu/mccartyr/isowdcal.html "ISO Week Date Calendar"
