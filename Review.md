# Defect Analysis

| Category | Result | Defect |
|---|---|---|
| **Initialization** | Issue | `sum` is uninitialized in `averageAttack()` (line 79). |
| **Pointers** | Issue | Null pointer access (line 58), dangling reference (line 75), use-after-delete (line 88), and shallow copying of pointers (line 138). |
| **Arrays** | Issue | Array capacity is 5, but 6 monsters are added (lines 118–123). |
| **Loops** | Issue | Incorrect loop condition `i <= monsterCount` in `totalMonsterHealth()` (line 66). |
| **Arithmetic** | Issue | Incorrect unsigned damage handling (lines 57–58) and integer division in `calculateDamage()` (line 95). |
| **Control Flow** | Issue | Assignment instead of comparison in `findMonster()` (line 49) and missing return in `playerRank()` (lines 98–103). |
| **Function Calls** | Issue | `attackMonster()` and `getMonsterLabel()` do not safely handle invalid monster IDs (lines 56–58 and 72–75). |
