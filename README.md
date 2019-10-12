# QtSerialMonitor
Universal serial monitor with data plotting capabilities, based on [Qt](https://www.qt.io/). Designed with all sorts of [Arduino](https://www.arduino.cc/) projects in mind, as a handy tool for debugging and experimentation :) 

![mainwindow](/docs/_screenshots/mainwindow.png)

**Features:**

- In/out serial data terminal with command history,
- UDP network protocol support,
- Advanced data plotter with multiple graphs support and basic data filtering - uses [QCustomPlot](https://www.qcustomplot.com/),
- Printer support, ability to save graph as image,
- Read/write ".txt" data logs,
- many more...
---
<a href="https://github.com/mich-w/QtSerialMonitor/releases/download/1.1/QtSerialMonitor_1.1_win_x64.zip" download>Download QtSerialMonitor_v1.1_win_x64</a> 
-
---

***Notes:***

* The app uses a custom-written parser, which searches the incoming message for plottable data in form of label-value set. At the moment, all labels and values **must be separated with a whitespace** in order to be recognized. Its possible to use separators like "=" and "," - parser will be replace them with whitespace before processing. If no label is found, a generic name will be used i.e. "Graph 0".*

        Examples of supported formats:

        - "Roll = 1.23 Pitch = 45.6"
        - "Voltage: 1.23 (tabulator) Output: 4.56"
        - "1.23 4.56" (Graph 0 and Graph 1)
 
* Application uses QtSettings functionality and stores a simple .ini file on the hard drive in which it keeps its settings. Under Windows, the file should be located in *C:\ProgramData\QtSerialMonitor*. The settings are saved each time the app closes.
