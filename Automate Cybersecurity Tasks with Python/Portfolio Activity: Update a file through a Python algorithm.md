
# File Update Algorithm in Python  
Algorithm for Managing Allow-List IPs in a Healthcare Environment

## 📌 Project Description
This project demonstrates my ability to use Python to automate file updates in a cybersecurity context.  
The scenario simulates a healthcare environment where only specific employees—identified by their IP addresses—are allowed to access a restricted subnet.  
I developed a Python algorithm that reads an allow-list file, compares it with a removal list, deletes unauthorized IPs, and rewrites the updated list back to the file.  
This project highlights my skills in file handling, list operations, loops, and conditional logic in Python.

---

## 📌 Python Code

```python
# Step 1: فتح ملف قائمة السماح
import_file = "allow_list.txt"

with open(import_file, "r") as file:
    ip_addresses = file.read()

# Step 2: تحويل السلسلة إلى قائمة
ip_addresses = ip_addresses.split()

# قائمة الإزالة
remove_list = ["192.168.1.10", "10.0.0.5", "172.16.0.22"]

# Step 3: التكرار عبر قائمة الإزالة
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
        # لا توجد نسخ مكررة، لذلك remove() آمنة هنا

# Step 4: إعادة تحويل القائمة إلى سلسلة
updated_ips = "\n".join(ip_addresses)

# Step 5: تحديث الملف بالقائمة المنقحة
with open(import_file, "w") as file:
    file.write(updated_ips)
```
