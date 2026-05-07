# Define variables
```cobol
DATA DIVISION.
WORKING-STORAGE SECTION.
01 var-group
   05 example_num     PIC s9(9).
   05 example_float   PIC s9(9)V99.
   05 example_text    PIC A(20).
```

Values inside brackets indicate the length of the variable.
```cobol
   05 small_number PIC 9(5).
   05 large_number PIC 9(20).
```
In the above example, `small_number` will have 5 digits, whereas `large_number` will have 20 digits.
## Integers
```cobol
   05 unsigned_int    PIC 9(10)
   05 signed_int      PIC s9(10)
```

## String
```cobol
   05 some_text       PIC A(20)
```