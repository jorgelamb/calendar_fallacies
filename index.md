# Your calendrical fallacy is thinking...

## Days are 86,400 seconds long

False. Even if you live in a place that doesn't have [Daylight Saving Time](https://en.wikipedia.org/wiki/Daylight_saving_time), you are still subject to rogue [leap seconds](https://en.wikipedia.org/wiki/Leap_second) that get inserted into our calendars every now and then. If you care about being precise, you care about leap seconds. And if you're writing software for others to use, chances are at least one of your users will be affected by DST at some point.

## Days are 24 hours long

False. Many places around the world observe Daylight Saving Time, which means that people living in these locations will sometimes experience 23 hour days (when they "leap forward") and 25 hour days (when they "leap back").

## An hour will never occur twice in a single day

False. On days when we "leap back" for the Daylight Saving Time shift, one hour occurs *twice*. For example, in the United States, the hour that occurs twice is the 2 AM hour. This means that on these "fall back" days, correctly-implemented clocks will go from 1:58 ... 1:59 ... 2:00 ... 2:01 ... ... 2:59 ... 2:00 ... 2:01 ...

This leads to some interesting questions: If a user has set an alarm to wake up at 2 AM on that day, what happens? Does the alarm go off the hour after the 1 AM hour? Or does it go off during the hour before 3 AM? Or does it go off twice? Or do you just give up and not make the alarm go off at all and make your users miss their dead-of-night appointment?

## Every day has a midnight

False. Brazil performs its DST "leap forward" transition at midnight, which means that 11:59 PM is followed by 1:00 AM.

## Days start at midnight (or as close to it as possible)

Mostly true. For the sake of simplifying calculations and establishing conventions, the day-to-day rollover happens at midnight. However, the Hebrew calendar traditionally starts its days at sunset.

## Everyone uses the Gregorian calendar

False. Many places in Africa use one of the various Coptic calendars. Israel uses the Hebrew calendar. The Islamic calendar is used all through the Middle East and other predominantly muslim countries. Thailand uses the Buddhist calendar. Japan uses the Japanese Imperial calendar for official state business.

## Months always have 30 or 31 days in them

False. February. Duh.

## OK... Months always have at least 28 days in them

False. The month [*Pi Kogi Enavot*](https://en.wikipedia.org/wiki/Intercalary_month_%28Egypt%29) in the Coptic calendar only has 5 or 6 days in it (depending on the year).

## Month lengths follow regular cycles

False. Traditional Islamic calendars base their months on local observations of the moon. So if it's really really cloudy and the moon isn't visible, then the previous month just keeps going... and going...

## The current year is {2017}

False. It's the year 5777 in the Hebrew calendar.

## All the important years are four digits longs

False. It's the year Heisei 29 in the Japanese calendar.

## In a range of days, a day will not be missing in the middle of it

False. In 1582, the transition from the Julian to Gregorian calendars meant that there was about a week and a half that was missing for various locations around Europe.

Additionally, in 2011, Samoa decided to jump "ahead" a full day in order to move to the west side of the International Date Line (previously they were on the east). This resulted in December 30, 2011 being skipped on their calendars. So for Samoans, December 29, 2011 was followed by December 30, 2011.

## In a range of months, a month will not be missing in the middle of it

False. The Hebrew calendar uses leap months, which occur during the middle of the year.

## A year is twelve months

False. Calendars like the Hebrew and Coptic calendars deal with years that are 13 months long.

## A year is 365 (or 366) days

## Leap years occur every four years

False. The year 2000 was not a leap year.

## Leap years occur every four years except when the year is evenly divisible by 100

False. The Hebrew calendar, which is based almost entirely off the lunar cycle, inserts leap years 7 times in a 19 year period.

## The current year only changes at "New Years"

False. The current year of the Japanese Imperial calendar is based on the reign of the current emperor. When the emperor dies, the next day is reset to the year 1 (of a new era).

For example, the Emperor Shōwa (Akhito) passed away on January 7, Shōwa 64 (January 7, 1989). His son, Hirohito, ascended to the throne the next day, which was the date January 8, Heisei 1.

## Nobody uses the Julian calendar anymore

False. The Julian calendar is still used by Eastern Orthodox churches, and the Julian day is used in certain kinds of astronomical calculations.

## Timezones always are on the hour mark
## OK... Timezones are always on the *half* hour mark
## *Fine*... Timezones are always on the *quarter* hour mark
## No location will ever change what time zone it's in

## It is normal that the Sept-, Oct-, Nov-, and Dec- months are numbered 9, 10, 11, and 12

False. This is very weird.

## "Calendrical" isn't a real word.

[False](https://www.merriam-webster.com/dictionary/calendrical).

## This is all really complicated.

True!

## I never want to write code that handles all of this.

True! You should always use the Date and Time Services provided by the [ICU Project](http://userguide.icu-project.org/datetime). If you're an iOS/macOS developer, then you should always stick to `NSCalendar` and its cohorts, which are all built on top of the ICU libraries.
