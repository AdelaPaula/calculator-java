1. LOC 
Calculator.java
Total linii: 177
Comentarii: 5
Linii goale: ~47
LOC efectiv: ~125
Start.java
Total linii: 24
Comentarii: 0
Linii goale: ~5
LOC efectiv: ~19
Proiect total
Metrică	Valoare
Total linii	201
LOC efectiv	144

2. Complexitate ciclomatică
Metodă	Complexitate
evaluateExpression()	11
Calculate()	12
3. Complexitate cognitivă
Metodă	Complexitate
evaluateExpression()	9
Calculate()	11

Concluziile sunt urmatoarele:

# Assignment 1 – Software Metrics and Static Analysis

## Metrics

### LOC

| File              | LOC |
| ----------------- | --- |
| Calculator.java   | 125 |
| Start.java        | 19  |
| Total Project LOC | 144 |

### Cyclomatic Complexity

| Method               | Cyclomatic Complexity |
| -------------------- | --------------------- |
| evaluateExpression() | 11                    |
| Calculate()          | 12                    |

### Cognitive Complexity

| Method               | Cognitive Complexity |
| -------------------- | -------------------- |
| evaluateExpression() | 9                    |
| Calculate()          | 11                   |

---

## Informal Code Review and Static Analysis Report

Calculator.java – line 17 – Method `ToString()` does not follow Java naming conventions. It should be named `toString()`.

Calculator.java – line 6 – Static variable `finalResult` introduces global mutable state and makes the class non-thread-safe.

Calculator.java – line 29 – No validation for empty input string. Calling `expression.charAt(0)` may throw `StringIndexOutOfBoundsException`.

Calculator.java – line 35 – The regular expression used in `split()` does not properly support unary operators inside expressions.

Calculator.java – line 39 – Iteration stops at `expression.length() - 1`, potentially ignoring invalid trailing operators.

Calculator.java – line 58 – Generic `Exception` is caught instead of the more specific `NumberFormatException`.

Calculator.java – line 25 – Method `evaluateExpression()` performs parsing, validation and calculation, violating the Single Responsibility Principle.

Calculator.java – line 68 – Method `Calculate()` is overly complex and contains duplicated code blocks.

Calculator.java – line 68 – Method name `Calculate()` does not follow Java naming conventions. It should be `calculate()`.

Calculator.java – line 68 – Recursive implementation may cause stack overflow for very large expressions.

Calculator.java – lines 81–167 – Significant code duplication exists for handling arithmetic operators.

Calculator.java – line 91 – Division by zero is not explicitly validated.

Calculator.java – line 169 – Method may terminate without reporting an error when unsupported operators are present.

Start.java – line 11 – A new `Scanner` object is created on every loop iteration, causing unnecessary object allocation.

Start.java – line 7 – Variable name `Expression` violates Java naming conventions; local variables should start with lowercase letters.

Start.java – line 8 – Boolean variable `active` could be replaced with a clearer loop structure.

Project-wide – Missing unit tests and JavaDoc documentation.

---

## Concluzie

Proiectul este relativ mic și ușor de înțeles, dar au fost identificate mai multe erori de cod:

* global mutable state (`finalResult`);
* duplicated code in arithmetic evaluation;
* recursive implementation of calculations;
* insufficient input validation;
* violations of Java naming conventions;
* lack of unit tests and documentation.

Refactorizarea logicii de calcul și îmbunătățirea validării ar îmbunătăți semnificativ mentenabilitatea și fiabilitatea.
