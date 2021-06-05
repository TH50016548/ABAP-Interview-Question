# ABAP-Interview-Question

## Questions on SAP SCRIP!

### 1.  What is the T Code for SAP Script forms?
SE71 is the T Code for SAP Script forms.

### 2.	What is PROTECT & ENDPROTECT?
PROTECT & ENDPROTECT is a command used to protect a paragraph against a page break.

### 3.	What are the different types of SAP Script symbols?
4 different types of SAP Script symbols are as follows.
* System symbols
*	Standard symbols
*	Program symbols
*	Text symbols

![symbols](/images/type_of_symbols.png)

[More about symbols and formatting in SAP SCRIPT](https://www.samplecodeabap.com/sapscript-symbols-and-formatting-options/)

### 4.	What are the different window types in SAP Script?
*	MAIN – Main window
*	VAR – Variable window
*	CONST – Constant window

![photo](/images/script_window_types.png)

### 5.	How many MAIN windows are allowed in SAP script?
99 main windows are allowed in SAP script.

### 6.	How do you control printer functions from SAP script?
By using PRINT-CONTROL command.

### 7.	How can we omit a leading sign and a leading zero in SAP Script?
Leading sign can be omitted by using ‘S’ with the Sap Script symbol i.e. &symbol(S)&. Leading zero can be omitted by using ‘Z’ with the Sap Script symbol i.e. &symbol(Z)&.

### 8.	How to debug a SAP Script?
To switch on the debugger for SAP Script use the menu path Utilities->Debugger or use the program RSTXDBUG.

### 9.	What are the different function modules used in SAP Script?
*	START_FORM
*	OPEN_FORM
*	WRITE_FORM
*	CLOSE_FORM
*	END_FORM
 
### 10.	How to call a subroutine in SAP Script?
Use PERFORM to call a subroutine.
Syntax for PERFORM statement is as follows
```abap
PERFORM <subroutine> IN PROGRAM <program>
USING &INVAR1&
USING &INVAR2&
CHANGING &OUTVAR1&
CHANGING &OUTVAR2&
ENDPERFORM
```

Syntax for FORM statement in the program is as follows.
```abap
FORM <subroutine> TABLES IN_TAB STRUCTURE ITCSY
OUT_TAB STRUCTURE ITCSY.
...
ENDFORM.
```
### 11. What Is The Table Name That Will Contain All The Script Form Names And Print Program Names?
TNAPR

### 12. Can You Create A Script With Out A Main Window?
No

### 13. How To Create Standard Text In Sapscripts?
SO10

### 14. How To Download/upload Image Sapscripts From & To Your Pc?
SE78 or RSTXLDMC

### 15. How Can You Copy Forms From One Client To Other?
SE71, Utilities -> Copy from client

### 16. How do you Create Boxes In Sap Script?
BOX XPOS ‘1’ CM YPOS ‘1’ CM WIDTH ‘10’ CM HEIGHT ‘10’ CM FRAME 10 TW

### 17. How To Insert Symbols In Smart Form?
Select the Text node.
Go to menu Include->Characters->SAP Symbols.
![symbols 1](/images/sap_symbols_1.png)
![symbols 2](/images/sap_symbols_2.png)

### 18. How Do Print You Number Pages In Sap Script Layout Outputs?
&page&
&next_Page&

### 19. Where Do We Define Tab Space For Data In Sapscript?
When defining the paragraph for the text element we can define the TABS there. 
There is parameter called TABS to be defined in paragraph definition.
![tab space](/images/tabs_space.png)

### 20. What is the difference between a window and a page window?
Window | Page Window
---- | ----
All the windows are created in this particular section. We can give window name and its description. | In page window, we map the already created windows on the pages as well as we can give margins and height width for the windows.
