Here is a clean and complete list of **commonly used C language header files**, grouped by category for easy learning.

---

# ✅ **Standard C Header Files (C89/C90 + C99 + C11)**

## **1. Input / Output**

| Header      | Purpose                                            |
| ----------- | -------------------------------------------------- |
| `<stdio.h>` | Standard input/output (printf, scanf, fopen, etc.) |

---

## **2. Standard Library**

| Header            | Purpose                                                        |
| ----------------- | -------------------------------------------------------------- |
| `<stdlib.h>`      | Memory allocation, conversions, random numbers, exit functions |
| `<stddef.h>`      | Common macros: NULL, size_t, ptrdiff_t                         |
| `<stdbool.h>`     | Boolean type `bool` (C99)                                      |
| `<stdint.h>`      | Fixed-width integer types like int32_t (C99)                   |
| `<inttypes.h>`    | Format macros for `stdint` (C99)                               |
| `<stdnoreturn.h>` | `noreturn` function specifier (C11)                            |

---

## **3. Strings & Characters**

| Header       | Purpose                                              |
| ------------ | ---------------------------------------------------- |
| `<string.h>` | String operations (strlen, strcpy, strcmp)           |
| `<ctype.h>`  | Character functions: isalpha(), isdigit(), toupper() |
| `<wchar.h>`  | Wide character handling                              |
| `<wctype.h>` | Wide character classification (C99)                  |

---

## **4. Math**

| Header        | Purpose                                |
| ------------- | -------------------------------------- |
| `<math.h>`    | Mathematics functions (sin, cos, sqrt) |
| `<complex.h>` | Complex numbers (C99)                  |
| `<fenv.h>`    | Floating-point environment (C99)       |
| `<tgmath.h>`  | Type-generic math macros (C99)         |

---

## **5. Time & Date**

| Header     | Purpose                              |
| ---------- | ------------------------------------ |
| `<time.h>` | Date & time (clock, time, struct tm) |

---

## **6. Diagnostics & Error Handling**

| Header       | Purpose                    |
| ------------ | -------------------------- |
| `<assert.h>` | assert() macro             |
| `<errno.h>`  | Error macros & error codes |

---

## **7. Localization**

| Header       | Purpose                  |
| ------------ | ------------------------ |
| `<locale.h>` | Locale-specific settings |

---

## **8. Signal Handling**

| Header       | Purpose                                 |
| ------------ | --------------------------------------- |
| `<signal.h>` | Signal handling (SIGINT, SIGKILL, etc.) |

---

## **9. Variable Arguments**

| Header       | Purpose                               |
| ------------ | ------------------------------------- |
| `<stdarg.h>` | Variable argument functions (va_list) |

---

## **10. Multithreading (C11)**

| Header          | Purpose                 |
| --------------- | ----------------------- |
| `<threads.h>`   | Threads & mutex (C11)   |
| `<stdatomic.h>` | Atomic operations (C11) |

---

# ✅ **Additional (Non-standard / Compiler Specific)**

| Header          | Used in                                    |
| --------------- | ------------------------------------------ |
| `<conio.h>`     | getch(), clrscr() — Turbo C / Windows only |
| `<process.h>`   | process & thread functions (Windows)       |
| `<unistd.h>`    | POSIX system calls (Linux/Unix)            |
| `<sys/types.h>` | System-defined types (POSIX)               |
| `<sys/stat.h>`  | File info/stat (POSIX)                     |
| `<fcntl.h>`     | File control (POSIX)                       |
| `<pthread.h>`   | POSIX threads                              |

---

# ⭐ If you want, I can also send:

✅ List of headers **with example programs**
✅ List of headers **for Turbo C**, **Linux**, or **Windows**
✅ Printable **PDF table** of all header files

Just tell me!
