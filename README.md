# Python Interface Package for Nanonis 

Official python package for the Nanonis TRAMEA Controller software.

## Usage

This package allows users of the Nanonis TRAMEA Controller software to use and control
said software through python commands.

## How to use

### Importing

import nanonis_tramea

### Initializing Connection through the socket module

import socket

connection = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

connection.connect((IP_ADRESS_HERE, PORT_HERE))

nanonisInstance = nanonis_spm.Nanonis(connection)

NOTE : THE PORT HAS TO BE AN INTEGER AND THE IP ADRESS A STRING

### Enabling Debug Console Output

The function "returnDebugInfo()" takes an integer as an argument. 
This integer should be either 1 = on, or 0 = off. This option is off by default.

Enable by running:
nanonisInstance.returnDebugInfo(1)

### Examples

There is a collection of examples installed with the package.

The description of all the available functions can be found in the TCP Protocol Document, and hovering on the function depending on the used IDE.

IMPORTANT:
The TCP Interface requires every argument to be of certain size (see documentation).
This is why the Numpy dependency is required, since it enables the specification
of variable sizes. 

## Change Log

### 1.0.3
Added the function Util.VersionGet to get the software version, the MCVA5 preamplifier functions, and the V5e Generic PI Controller functions.
### 1.0.4
Fixed the indentation of two Script functions (Script.Open and Script.LUTOpen) which triggered an error when trying to use the class.
Changed the behavior of the returnDebugInfo function so that nothing is printed out if there is no error.
### 1.0.5
Fixed some missing variable names in the function declaration of some MCVA and MProbe functions.
Fixed missing input arguments for Motor_FreqAmpGet and Motor_PosGet functions.
Added all functions for the Function Generators 1Ch and 2Chs.
Fixed the SpectrumAnlzr_DataGet function.
Removed a check in the ParseError function which set a different error string offset for functions returning exactly 8 bytes.
Changed the data types of the returning arguments for the BiasSpectr_ChsGet and ZSpectr_ChsGet functions.






