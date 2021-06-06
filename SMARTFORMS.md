# Important questions on SMARTFORMS

### What is SMARTFORMS?
SMARTFORMS is a tool provided by SAP to create business documents such as sales order, invoice documents etc.

### Difference between SMARTFORMS and SAP SCRIPT
SMARTFORMS | SCRIPT
---- | ----
SMARTFORMS are client independent. | SAP Scripts is client dependent.
SMARTFORMS can be standalone.  | SAP Script is not standalone. It requires driver program to run.
Integrated form builder to design the layout. | NA
Can be created without main window. | NA
A new function module is generated upon activating the SMARTFORM. | NA

### I have a smartform which works fine in development server. After trasnsporting it to Production, there is no Function module generated for this smartform. Due to that  my program dumps in Production? How to solve this?
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

### How can you make the Smartforms to choose a printer name by default?
In the CALL FUNCTION of the Smartform Function Module, use the output options parameter to set the printer name.
The output options is of the type SSFCOMPOP which contains the field TDDEST. Set the TDDEST field to your default printer name. 
```abap
DATA outparams TYPE SSFCOMPOP.
outparams-tddest = 'LOCL'. "put printer name here
" Pass this parameter to function module of SMARTFORMS
```

### Where can I provide the input parameters to the smartform?
The input parameters for the smartform can be defined in Global Settings->Form Interface.

### Which transaction code is used to configure the Adobe Forms / Smart forms / SAP Script to the output type?
Ans: NACE transaction.

### How to insert symbols in SMARTFORMS?
Open the TEXT ELEMENT node. 
Click on Insert->Characters->SAP Symbols

