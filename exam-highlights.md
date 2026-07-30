# 🎯 สรุปสูตรและจุดเน้นสำหรับเตรียมสอบ (Exam Highlights)[cite: 1, 2, 3, 4, 5]

## 📌 1. ตารางเปรียบเทียบโครงสร้างข้อมูลเชิงเส้น[cite: 1, 2, 3, 4, 5]
| โครงสร้างข้อมูล | หลักการทำงาน | จุดเด่น | ปัญหา/ข้อจำกัด |
| :--- | :--- | :--- | :--- |
| **Array** | Random Access ($O(1)$)[cite: 2] | เข้าถึงข้อมูลได้เร็วมากผ่าน Index[cite: 2] | ขนาดคงที่ (Static), เลื่อนข้อมูลช้าเมื่อ Insert/Delete[cite: 1, 2] |
| **Stack** | **LIFO** (Last-In First-Out)[cite: 3] | จัดการลำดับย้อนกลับ, Recursion, Infix/Postfix[cite: 3] | เกิด Overflow ถ้า Array เต็ม[cite: 3] |
| **Queue** | **FIFO** (First-In First-Out)[cite: 4] | จัดการแถวคอยตามลำดับก่อนหลัง[cite: 4] | คิวเชิงเส้นเกิด False Overflow ต้องแก้ด้วย Circular Queue[cite: 4] |
| **Linked List** | Dynamic Allocation[cite: 1, 5] | ปรับขนาดได้ยืดหยุ่น แทรก/ลบง่าย $O(1)$[cite: 5] | สุ่มเข้าถึงไม่ได้ ต้องค้นหาตามลำดับ ($O(n)$)[cite: 1, 5] |

---

## 📌 2. รวบรวมสูตรคำนวณตำแหน่ง Array ในหน่วยความจำ[cite: 2]
* **1 มิติ**: $\text{Loc}(A[i]) = B + C(i - L)$[cite: 2]
* **2 มิติ Row Major**: $\text{Loc}(A[i, j]) = B + C[(i - L_1)N + (j - L_2)]$[cite: 2]
* **2 มิติ Column Major**: $\text{Loc}(A[i, j]) = B + C[(j - L_2)M + (i - L_1)]$[cite: 2]
* **3 มิติ Row Major**: $\text{Loc}(A[i, j, k]) = B + C[(i - L_1)MN + (j - L_2)N + (k - L_3)]$[cite: 2]
* **3 มิติ Column Major**: $\text{Loc}(A[i, j, k]) = B + C[(i - L_1)MN + (k - L_3)M + (j - L_2)]$[cite: 2]

---

## 📌 3. ข้อระวังในข้อสอบปฏิบัติการ Linked List[cite: 5]
* **แทรกโหนดใหม่หลังโหนด P ใน Singly Linked List**:
  * ✅ *ต้องทำ*: `Next(Newnode) = Next(P)` ก่อน แล้วค่อยสั่ง `Next(P) = Newnode`[cite: 5]
  * ❌ *ถ้าสลับกัน*: สายชี้โหนดถัดไปจะหลุดหายทันที![cite: 5]
* **ลบโหนด P ใน Doubly Linked List**:
  * `Next(Prev(P)) = Next(P)`[cite: 5]
  * `Prev(Next(P)) = Prev(P)`[cite: 5]