# algorithm-assignment2
## Boyer–Moore (Bad Character) Search – US 50 States

## Purpose
A menu-driven console application (Java/Windows) that performs substring searches on text (the names of the 50 US states concatenated with spaces) using **only the bad character rules** of Boyer–Moore.

## Execution Method
- Environment: JDK 17 or later (Windows)
- Compile: `javac Main.java`
- Run: `java Main`

## Operations (Menu)
1) Display the text  
   → Shows the 50-state text and character count  
2) Search  
   → Enter pattern (ignores case). Displays hit **0-based index** in an array  
3) Exit program  
   → Exit

## Algorithm
- Implements only the **bad character rule** from Boyer–Moore.
- Calculates **shift = max(1, j - last[bad])** from mismatch position j and the **last occurrence position of bad character bad** last[bad], then skips.
- Preprocessing: Create the pattern's last array (ASCII 0..255) in O(m).
- Time complexity: Average sublinear, worst case O(n·m).  
- Case normalized using `toLowerCase`; **index reported using original text's zero-based indexing**.

## Data
- Concatenate 50 state names into a single string using `String.join(“ ”, states)` (space-separated).

## Representative Tests
- Pattern: `new` → Output multiple starting positions in “New Hampshire / New Jersey / New Mexico / New York”.  
- Pattern: `car` → Outputs positions in “North **Car**olina, South **Car**olina”.  
- Pattern: `zzz` → No matches.

## Known Specifications
- Assumes ASCII. Treats the last occurrence of non-ASCII characters as -1.
- Empty string patterns are not accepted.


