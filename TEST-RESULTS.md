aplicația se închide dacă expresia este goală (StringIndexOutOfBoundsException);
nu există mesaj de eroare pentru împărțirea la zero;
nu suportă expresii precum 2*-3;
nu suportă paranteze (2+3)*4;
folosește float, ceea ce reduce precizia;
nu există validare pentru spații (2 + 3);
nu există validare pentru operatori consecutivi.



# TEST RESULTS

## Black Box Testing

| Test | Input | Expected | Actual | Status |
|------|-------|----------|--------|--------|
|T1|2+3|5|5|PASS|
|T2|2+3*4|14|14|PASS|
|T3|2/0|Infinity|Infinity|PASS|
|T4|""|ERROR|Application crashes|FAIL|
|T5|2*-3|-6|ERROR|FAIL|
|T6|(2+3)*4|20|ERROR|FAIL|
|T7|abc|ERROR|ERROR|PASS|
|T8|3.5+2.5|6|6|PASS|

## Observed Defects

1. Empty input causes application crash.
2. Negative numbers after an operator are not supported.
3. Parentheses are not supported.
4. No validation for spaces.
5. Division by zero is not handled explicitly.
6. Float precision may produce inaccurate results for large numbers.

## Unit Test

A JUnit test was implemented to verify the calculation functionality for multiplication.
