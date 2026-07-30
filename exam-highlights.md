## 🎯 สรุปจุดเน้นยอดฮิตที่มักออกสอบประจำ (Exam Highlights & Key Formulas)

### 📌 1. ตารางเปรียบเทียบโครงสร้างข้อมูลเชิงเส้น (Linear Comparison)
| โครงสร้างข้อมูล | หลักการทำงาน | จุดเด่น | ปัญหา/ข้อจำกัด |
| :--- | :--- | :--- | :--- |
| **Array** | Random Access ($O(1)$) | เข้าถึงข้อมูลได้เร็วมากผ่าน Index | ขนาดคงที่ (Static), เสียเวลาเลื่อนข้อมูลเมื่อ Insert/Delete |
| **Stack** | **LIFO** (Last-In First-Out) | จัดการลำดับการทำงานย้อนกลับ, Recursion, Infix/Postfix | เกิด Overflow ถ้าจอง Array ไว้เต็ม |
| **Queue** | **FIFO** (First-In First-Out) | จัดการแถวคอยตามลำดับก่อนหลัง | คิวเชิงเส้นเกิด False Overflow ต้องแก้ด้วย Circular Queue |
| **Linked List** | Dynamic Allocation | ขนาดปรับเปลี่ยนได้ยืดหยุ่น แทรก/ลบง่าย $O(1)$ | สุ่มเข้าถึงไม่ได้ ต้องใช้ Sequential Search ($O(n)$) |

---

### 📌 2. รวบรวมสูตรคำนวณตำแหน่งในหน่วยความจำของ Array
* **1 มิติ**: $	ext{Loc}(A[i]) = B + C 	imes (i - L)$
* **2 มิติ Row Major**: $	ext{Loc}(A[i, j]) = B + C 	imes [(i - L_1) 	imes N + (j - L_2)]$
* **2 มิติ Column Major**: $	ext{Loc}(A[i, j]) = B + C 	imes [(j - L_2) 	imes M + (i - L_1)]$
* **3 มิติ Row Major**: $	ext{Loc}(A[i, j, k]) = B + C 	imes [(i - L_1) \cdot M \cdot N + (j - L_2) \cdot N + (k - L_3)]$
* **3 มิติ Column Major**: $	ext{Loc}(A[i, j, k]) = B + C 	imes [(i - L_1) \cdot M \cdot N + (k - L_3) \cdot M + (j - L_2)]$

---

### 📌 3. ลำดับพอยน์เตอร์การแทรก/ลบโหนดใน Linked List (ระวังโดนหลอก!)
* **แทรกโหนดใหม่หลังโหนด P ใน Singly Linked List**:
  * ✅ *ทำถูกต้อง*: `Next(Newnode) = Next(P)` ก่อน แล้วค่อย `Next(P) = Newnode`
  * ❌ *ทำผิด*: ถ้าสั่ง `Next(P) = Newnode` ก่อน สายชี้โหนดถัดไปจะหลุดหายทันที!
* **ลบโหนด P ใน Doubly Linked List**:
  * `Next(Prev(P)) = Next(P)`
  * `Prev(Next(P)) = Prev(P)`