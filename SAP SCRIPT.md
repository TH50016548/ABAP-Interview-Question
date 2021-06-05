# ABAP-Interview-Question

## 1.  What is the T Code for SAP Script forms?
SE71 is the T Code for SAP Script forms.

## 2.	What is PROTECT & ENDPROTECT?
PROTECT & ENDPROTECT is a command used to protect a paragraph against a page break.

## 3.	What are the different types of SAP Script symbols?
4 different types of SAP Script symbols are as follows.
* System symbols
*	Standard symbols
*	Program symbols
*	Text symbols

## 4.	What are the different window types in SAP Script?
*	MAIN – Main window
*	VAR – Variable window
*	CONST – Constant window

## 5.	How many MAIN windows are allowed in SAP script?
99 main windows are allowed in SAP script.

## 6.	How do you control printer functions from SAP script?
By using PRINT-CONTROL command.

## 7.	How can we omit a leading sign and a leading zero in SAP Script?
Leading sign can be omitted by using ‘S’ with the Sap Script symbol i.e. &symbol(S)&. Leading zero can be omitted by using ‘Z’ with the Sap Script symbol i.e. &symbol(Z)&.

## 8.	How to debug a SAP Script?
To switch on the debugger for SAP Script use the menu path Utilities->Debugger or use the program RSTXDBUG.

## 9.	What are the different function modules used in SAP Script?
*	START_FORM
*	OPEN_FORM
*	WRITE_FORM
*	CLOSE_FORM
*	END_FORM
 
## 10.	How to call a subroutine in SAP Script?
Use PERFORM to call a subroutine.
Syntax for PERFORM statement is as follows
> PERFORM <subroutine> IN PROGRAM <program>
> USING &INVAR1&
> USING &INVAR2&
> CHANGING &OUTVAR1&
> CHANGING &OUTVAR2&
> ENDPERFORM

Syntax for FORM statement in the program is as follows.
> FORM <subroutine> TABLES IN_TAB STRUCTURE ITCSY
> OUT_TAB STRUCTURE ITCSY.
> ...
> ENDFORM.
