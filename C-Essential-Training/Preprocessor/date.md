Here’s how you can **parse the `__DATE__` macro** to convert it into a **`YYYY-MM-DD`** format:

---

### 🚀 **Code Example: Convert `__DATE__` to `YYYY-MM-DD`**

```c
#include <stdio.h>
#include <string.h>

int getMonthNumber(const char *month) {
    if (strcmp(month, "Jan") == 0) return 1;
    if (strcmp(month, "Feb") == 0) return 2;
    if (strcmp(month, "Mar") == 0) return 3;
    if (strcmp(month, "Apr") == 0) return 4;
    if (strcmp(month, "May") == 0) return 5;
    if (strcmp(month, "Jun") == 0) return 6;
    if (strcmp(month, "Jul") == 0) return 7;
    if (strcmp(month, "Aug") == 0) return 8;
    if (strcmp(month, "Sep") == 0) return 9;
    if (strcmp(month, "Oct") == 0) return 10;
    if (strcmp(month, "Nov") == 0) return 11;
    if (strcmp(month, "Dec") == 0) return 12;
    return 0; // Invalid month
}

int main() {
    char month[4];
    int day, year;

    // Parse the __DATE__ macro (format: "MMM DD YYYY")
    sscanf(__DATE__, "%3s %d %d", month, &day, &year);

    int monthNum = getMonthNumber(month);

    if (monthNum == 0) {
        printf("Invalid month detected!\n");
        return 1;
    }

    // Print the date in "YYYY-MM-DD" format
    printf("Formatted Date: %04d-%02d-%02d\n", year, monthNum, day);

    return 0;
}
```

---

### 📝 **Explanation:**
1. **`sscanf(__DATE__, "%3s %d %d", month, &day, &year);`**  
   - Extracts the three-letter month abbreviation, day, and year from `__DATE__`.  
2. **`getMonthNumber` function:**  
   - Converts the month abbreviation (e.g., `"Feb"`) to its numeric equivalent (`2`).  
3. **Formatted Output:**  
   - Uses `printf` with zero-padding to ensure `"YYYY-MM-DD"` format.

---

### 🖥️ **Sample Output (if compiled on Feb 22, 2025):**  
```
Formatted Date: 2025-02-22
```

🔔 **Edge Cases Handled:**  
- Space-padded days (e.g., `"Jan  5 2025"`) will still convert to `"2025-01-05"`.  
- Invalid month names return an error message.  

---

💡 **Need to include the compilation time with `__TIME__` as well?** I can help with that too! 😊
