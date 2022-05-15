# global-logger
Simple logging utility with log levels - run in global scope.

# motivation
There are quite a few logging packages around - this one tries to be a very simple variant, which doesn't require to be wired throughout the application but uses a FGV instead. It introduces several logging levels to allow for easy control of the depth of logged information.

# usage
All you need is initialize your logger at the start of your application. Then log by specific level wherever in your application. Close the logger afterwards.

![global-logger-example](img/global-logger-example1.png)
This snippet will produce the following in the `application_directory/logs/[year]/[month]/[day]/Demo_log.tsv`:
```
15:21:40.630 23.10.2018 INFO  For loop cycle: 0 Global_logger.lvlib:Example.vi

15:21:40.630 23.10.2018 WARN  Something might go wrong..  Global_logger.lvlib:Example.vi

15:21:40.630 23.10.2018 FATAL ..Ups ! Global_logger.lvlib:Example.vi

```

Additionally you can create multiple named loggers and assign each of them with one to many output destinations (files or UI controls). See Examples.

# features
- Globally accessible logger
- Six logging levels
- Configurable level meaning:
  - Standard: Ignores messages with log level which is less important that the logger's level.
  - Positive: Ignores messages with log level with greater importance that the logger's level.
  - Exact: Ignores messages with all levels except for the exact logger's level.
- Error wire check & error logging
- Configurable record fields:
  - timestamp
  - log level
  - logger name
  - message
  - source VI
  - source app
- Output to file
  - csv, tsv formats
  - year/month/day folder structure
  - configurable file size
  - configurable maximum logs age
- Output to UI controls
  - String, Listbox, Multicolumn Listbox, Table controls
- Option to write to multiple named loggers
  - Multiple outputs (file, UI) per logger each with it's own setup
- Configurable record ordering: new records to top / bottom
- Timestamp formatting


# next
Contibutions welcome!
## ideas for future versions
- more intelligent/efficient Writer.vi - currently each record = 1 write operation
