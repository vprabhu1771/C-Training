Here’s how you can **convert `__DATE__` and `__TIME__` macros** into a proper **ISO 8601 format (`YYYY-MM-DD HH:MM:SS`)**:

---

### 🚀 **Code: Convert `__DATE__` and `__TIME__` to `YYYY-MM-DD HH:MM:SS`**

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
    int day, year, hour, min, sec;

    // Parse __DATE__ (format: "MMM DD YYYY")
    sscanf(__DATE__, "%3s %d %d", month, &day, &year);
    
    // Parse __TIME__ (format: "HH:MM:SS")
    sscanf(__TIME__, "%d:%d:%d", &hour, &min, &sec);

    int monthNum = getMonthNumber(month);
    
    if (monthNum == 0) {
        printf("Invalid month detected!\n");
        return 1;
    }

    // Print formatted date-time in "YYYY-MM-DD HH:MM:SS" format
    printf("Compilation Timestamp: %04d-%02d-%02d %02d:%02d:%02d\n", 
            year, monthNum, day, hour, min, sec);

    return 0;
}
```

---

### 📝 **Explanation:**
1. **Extracts and parses `__DATE__` (MMM DD YYYY)**  
   - Uses `sscanf(__DATE__, "%3s %d %d", month, &day, &year);`  
   - Converts the month abbreviation (`"Feb"`) to its numeric value (`2`).  
2. **Extracts and parses `__TIME__` (HH:MM:SS)**  
   - Uses `sscanf(__TIME__, "%d:%d:%d", &hour, &min, &sec);`.  
3. **Formats the output in `YYYY-MM-DD HH:MM:SS`**  
   - Ensures proper zero-padding for single-digit values.  

---

### 🖥️ **Sample Output (if compiled on Feb 22, 2025, at 14:30:45):**  
```
Compilation Timestamp: 2025-02-22 14:30:45
```

---

🔔 **Why is this useful?**  
✅ Standardized **ISO 8601** format  
✅ Can be logged for debugging or version tracking  
✅ Useful for comparing timestamps programmatically  

---

💡 **Need to store it in a string instead of printing it?** Let me know! 😊
