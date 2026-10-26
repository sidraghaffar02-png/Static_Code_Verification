# Table 2: Code Review Report

| Line Number | Defect Type | Why It Is a Problem | Proposed Fix | Severity |
|---|---|---|---|---|
| **32–33** | Initialization | The monsters array is not initialized. | Initialize array elements to `nullptr`. | **Medium** |
| **41–43** | Array Bounds | Adding monsters without checking capacity can overflow the array. | Check `monsterCount < MAX_MONSTERS` before insertion. | **Critical** |
| **49** | Control Flow | `=` assigns a value instead of comparing IDs, causing incorrect search results. | Replace `=` with `==`. | **Critical** |
| **56–58** | Pointer Handling | If no monster is found, accessing `m->health` can crash the program. | Check whether `m == nullptr` before accessing it. | **Critical** |
| **57–58** | Arithmetic | Unsigned damage can cause incorrect comparisons and calculations. | Use signed integers and validate damage. | **High** |
| **66** | Loop / Array Bounds | `i <= monsterCount` can access an invalid array element. | Change the condition to `i < monsterCount`. | **Critical** |
| **72–75** | Pointer / Reference | Returning a reference to a local string creates a dangling reference. | Return `std::string` by value. | **Critical** |
| **79–81** | Initialization | `sum` contains an indeterminate value before addition. | Initialize it with `double sum = 0.0;`. | **High** |
| **85–88** | Pointer Handling | The code accesses `m->name` after deleting `m`. | Print the name before deleting the monster and check for `nullptr`. | **Critical** |
| **94–95** | Arithmetic | Integer division may discard the fractional part. | Convert an operand to `double` before division. | **Medium** |
| **98–103** | Control Flow | The function does not return a value for scores of 100 or below. | Add a return statement for the remaining cases. | **High** |
| **106, 109** | Input Handling | The fixed-size character array can overflow with a long input. | Use `std::string` and appropriate input handling. | **High** |
| **113** | Memory Management | Memory allocated with `new[]` is released with `delete` instead of `delete[]`. | Use `delete[] name` or replace the allocation with `std::string`. | **High** |
| **125** | Memory Management | The dynamically allocated bonus monster is never deleted. | Delete it when no longer needed or use a smart pointer. | **Medium** |
| **118–123** | Array Bounds | Six monsters are added to an array with a capacity of five. | Increase the capacity or limit the number of monsters. | **Critical** |
| **138** | Memory Management | Copying `Game` copies raw pointers, potentially causing double deletion. | Implement safe copy semantics or use appropriate smart-pointer ownership. | **Critical** |

