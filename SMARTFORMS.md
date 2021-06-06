# Important questions on SMARTFORMS

### 1. What is SMARTFORMS?
SMARTFORMS is a tool provided by SAP to create business documents such as sales order, invoice documents etc.

### 2. Difference between SMARTFORMS and SAP SCRIPT
SMARTFORMS | SCRIPT
---- | ----
SMARTFORMS are client independent. | SAP Scripts is client dependent.
SMARTFORMS can be standalone.  | SAP Script is not standalone. It requires driver program to run.
Integrated form builder to design the layout. | NA
Can be created without main window. | NA
A function module is generated upon activating the SMARTFORM. | NA
SMARTFORMS supports single page format | SAP SCRIPT supports multiple page formats.
SMARTFORMS supports various colors | SAP SCRIPT supports only Black and White.

### 3. I have a smartform which works fine in development server. After trasnsporting it to Production, there is no Function module generated for this smartform. Due to that  my program dumps in Production? How to solve this?
The Smartform that is created in the Development may not have the same name in the Production server. So it is always advised to use the Function Module SSF_FUNCTION_MODULE_NAME to get the Function Module name by passing the Smartform name.
```abap
DATA: fm_name TYPE rs38l_fnam.

  CALL FUNCTION 'SSF_FUNCTION_MODULE_NAME'
  EXPORTING
  formname = 'ZSMARTFORM'
  IMPORTING
  fm_name = fm_name
  EXCEPTIONS
  no_form = 1
  no_function_module = 2.

  CALL FUNCTION fm_name
  EXCEPTIONS
  formatting_error = 1
  internal_error = 2
  send_error = 3.

ENDIF.
```

### 4. How can you make the Smartforms to choose a printer name by default?
In the CALL FUNCTION of the Smartform Function Module, use the output options parameter to set the printer name.
The output options is of the type SSFCOMPOP which contains the field TDDEST. Set the TDDEST field to your default printer name. 
```abap
DATA outparams TYPE SSFCOMPOP.
outparams-tddest = 'LOCL'. "put printer name here
" Pass this parameter to function module of SMARTFORMS
```

### 5. Where can I provide the input parameters to the smartform?
The input parameters for the smartform can be defined in Global Settings->Form Interface.

### 6. Which transaction code is used to configure the Adobe Forms / Smart forms / SAP Script to the output type?
NACE transaction.

### 7. How to insert symbols in SMARTFORMS?
Open the TEXT ELEMENT node. 
Click on Insert->Characters->SAP Symbols

### 8. I have defined my own Program Lines, where I have used a global variable G_TEXT. I get an error G_TEXT is not defined?
Whenever using the global variables in the Program Lines, enter the variable name in Input Parameters if you are going to use(read) the variable. If you are going to both read/write the variable value enter the same in Output Parameters.

### 9. I have created a table node for display. Where can I check the condition which must satisfy to display the table?
The conditions can be defined in the Conditions tab. In smartforms all the nodes have a condition tab where you can specify the condition to be satisfied to access the node.

### 10. How can I define Page Protect in Smartforms?
To define Page Protect for a node go to the Output options and check the Page Protection checkbox.

### 11. How do you convert a Smartform Output to PDF output?
The following two function modules and their importing/exporting parameters:

CONVERT_OTF
CONVERT_OTF_2_PDF

In the Driver program, import the parameter 'job_output_info' from the Smartform FM and utilize that info in 'OTF' parameter of the two aforementioned function modules.

### 12. How can you see the Smartform Print Preview output as list output?
Type SLIS in the command prompt and hit enter

### 13. How do you achieve Bar Code printing in Smartforms?
Step1: Use SE73 i.e. SAP-Script Font Maintenance and create a Bar code say Zbarcode.
Step 2: For Smartform, create a character format C1 and use the recently created Barcode Zbarcode.

### 14. How do you add a Watermark Or a Background Image for Smartforms ?
* Upload an image or watermark using SE78 transaction.
* Go to the properties of a page in Smartform, Click on Background Image tab.
* Specify the source of the image you need here and it can be used as background image / Watermark in Smartforms.
[Background image in smartforms](/images/smartforms_background_image.png)

### 15. How will you print on both sided of a Smartform?
At the Page level in Smartforms, you can find something called as Print Mode.
Set the Print mode to duplex to print on both sides of the Smartform.
[Both side print in smartforms](/images/smartfomrs_printdouble.png)

### 16. How can you  provide a background color to the table?
Specify the color and shading for the table lines. 
[Table color and Shade in SMARTFORMS](/images/smartforms_table_shade.png)

### 17. How do you achieve Page Protection in Smartform ?
* Click on text node or table node.
* Goto __Output Options__ tab and select [x] __Page Protection__.
[Page Protection](/images/smartforms_pageprotect.png)

### 18. Can you move a Smartform from one SAP system to another without using transports ?
Ans: Yes, this can be achieved using the Upload/Download feature for Smartforms.

### 19. Can you have a Smartform without a main window?
Ans: Yes, you can create a Smartform without a Main Window.

### 20. How do you find the name of the Function Module for a Smartform?
* Open a smartform.
* Click on __Environment --> Function Module Name__ in the Menue.

### 21. Types of windows in SMARTFORMS?
There are four types of windows in smartforms.
* Main Window - To print the dynamic output, which doesn't have fixed length. The output automatically flows to the next page if there is no space on current page. There can be only one main window in smartforms.
* Secondary Window- To print the output which has fixed size and length.
* Final Window - A special type of window which is called after all the other windows are processed.
* Copies Window - A copy window can be placed multiple times on multiple pages.

### 22. What are default standard exceptions in smartforms?
* FORMAT ERROR
* INTERNAL ERROR
* SEND ERROR 
* USER CANCELED

[exceptions in smartforms](/images/smartforms_exceptions.png)

 
