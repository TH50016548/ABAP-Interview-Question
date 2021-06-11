# Questions on SAP ABAP Reports

Author: Nikhil Mishra

### 1. What is a report?
  Report is a program used to fetch data from the database tables and display it on the screen. It has 2 screens selection screen(optional) and list or output screen.

### 2. When the TOP-OF-PAGE event does get triggered?
  TOP-OF-PAGE event will be triggered when the first ULINE, WRITE or SKIP statement occurs in a program.

### 3. What is the difference between SKIP and RESERVE?
  SKIP provides empty space between lines, while RESERVE executes a page break on the current page if the number of lines between current line and the page footer is less than the number specified in RESERVE statement.

What is the difference between SKIP and NEW-LINE?

SKIP generates a blank line, while the NEW-LINE causes the control to move to next line.

What is hotspot?

Hotspot is an area on the list where the mouse pointer turns into an upright hand symbol. A single click on the hotspot does the same thing as a double-click.

What does HIDE statement do?

The HIDE statement hides the contents of the line along with the line numbers in a system defined HIDE area. This is used in interactive reporting.

What are the events in classical reports?

INITIALIZATION
AT SELECTION-SCREEN
START-OF-SELECTION
END-OF-SELECTION
TOP-OF-PAGE
END-OF-PAGE
How many detail lists can be created in interactive reporting?

20

What is the name of the system variable that holds the contents of the selected line in interactive reporting?

SY-LISEL

Can we set page headers to details lists?

Yes. Use TOP-OF-PAGE DURING LINE-SELECTION event.
