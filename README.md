Conf Manager
============

Conf Manager is a library to read/write configuration files.

#### How to use ####

1. Download both **cnfm.h** and **conf_manager.c** to your working directory.
2. Add ```#include "cnfm.h"``` to your program.
3. Call the functions you need from **conf_manager** library. see list of functions
4. Compile your program with the **conf_manager** library.
<br/>
   ```gcc -Wall -o example example.c conf_manager.c``` 
<br/>

#### Functions ####

> The following example codes are with in-correct syntaxes.

* get_prop
 
  This function returns the left portion of line after splitting it from the defined symbol.

* trim_string

  This allows you to remove spaces in both front and end. 
  
  example: 
  ```
  stringVariable_withoutspaces = trim_string(stringVariable_withspaces)
  ```
  
* conf_save

  To save the configuration values, you need to call this function. 
  Note: pre-opened file descriptor with read/write permissions should be passed as the first parameter. 
  
  example: 
   * old configuration
  ```
  application_name = my_first_app
  ```
   * new configuration you expect
  ```
  application_name = my_second_app
  ```
   * function 
  <br/>

  ```
  fileDescriptor = /*pre-opened file*/
  
  value = my_second_app 
 
  property = application_name

  conf_save(fileDescriptor, value, attribute)
  ```
  
* conf_read

  This returns the configuration value for a given attribute.
>  Note: pre-opened file descriptor with read/write permissions should be passed as the first parameter.
  
  example: 
  ```
  required_value = conf_read(fileDescriptor, attribute)
  ```
  
> See the declaration of all the main and sub functions in "cnfm.h" file. 

