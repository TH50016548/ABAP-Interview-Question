### 1. How many phases are there in real time implementation?
  5 phases
  * Project Preparation
  * Business Blue Print
  * Realization
  * Testing (UTP)
  * Go-Live & Support

### 2. How do you write technical specs?
  Based on the requirements mentioned in the FS(Function Specification Document) we prepare the TS(Technical Spefication Document).
  TS may include 
    Selection Screen Parameters,
    Point of change or creation (Report name, Enhancement Name etc...)
    Flow of Logic
 
### 3.What is Cross Applications? 
  Cross application is a communication methodology which is used
  To transfer data from SAP to SAP or SAP to NON-SAP.

  Communication done by following components...
  1->RFC (REMOTE FUNCTION CALL)
  2->IDOC (INTERMEDIATE DOCUMENT)
  3->ALE (APPLICATION LINK ENABLING)
  4->BAPI (BUSINESS APPLICATION PROGRAMMING INTERFACE)
  etc..

### 4. How data is stored in a cluster table?
  Each field of cluster table behaves as tables which contains the no. of entries.

### 5. What are client dependent objects in ABAP/SAP?
  SAP Script layout, text element, and some DDIC objects
  
### 6. On which event we can validate the input fields in module programs?
  In PAI (Write field statement on field you want to validate, if you want to validate group of fields put in chain and End chain statement).

### 7. In selection screen I have three fields, plant mat no and material group. If I input plant how do I get the material number and material group based on plant dynamically?
  ```abap
  AT SELECTION-SCREEN ON VALUE-REQUEST FOR MATERIAL.
  CALL FUNCTION 'F4IF_INT_TABLE_VALUE_REQUEST'.     "to get material and material group for the plant
  ```

### 8. How do you get output from IDOC?
  Data in IDOC is stored in segments, the output from IDOC is obtained by reading the data stored in its respective segments.
  
### 9. When top of the page event is triggered?
  After executing first write statement in start-of-selection event.
  
### 10. Can we create field without data element and how?
  In SE11 one option is available above the fields strip. Data element/direct type.

### 11. Which transaction code can I used to analyze the performance of ABAP program.
  TCode AL21
