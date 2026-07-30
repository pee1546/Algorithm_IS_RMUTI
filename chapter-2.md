# บทที่ 2: โครงสร้างข้อมูลแบบอาร์เรย์ (Array Data Structure)[cite: 2]

## 2.1 คุณลักษณะของอาร์เรย์[cite: 2]
1. **Homogeneous Data Type**: สมาชิกทุกตัวต้องเป็นประเภทข้อมูลเดียวกัน[cite: 2]
2. **Contiguous Memory**: จัดเก็บในหน่วยความจำเรียงติดต่อกัน[cite: 2]
3. **Static Structure**: มีขนาดแน่นอน จองพื้นที่ล่วงหน้า[cite: 2]
4. **Random Access**: เข้าถึงสมาชิกทุกตัวได้โดยตรงผ่าน Index ด้วยเวลา $O(1)$[cite: 2]

---

## 2.2 อาร์เรย์ 1 มิติ (One-Dimensional Array)[cite: 2]
* **จำนวนช่องทั้งหมด**: 
  $$\text{Elements} = U - L + 1$$
[cite: 2]
* **ขนาดความจุ (Bytes)**: 
  $$\text{Capacity} = (U - L + 1) \times \text{Size}$$
[cite: 2]
* **สูตรคำนวณแอดเดรส $A[i]$ ในหน่วยความจำ**:
  $$\text{Loc}(A[i]) = B + C \times (i - L)$$
[cite: 2]
  *(เมื่อ $B$ = Base Address, $C$ = ขนาดข้อมูลต่อช่อง [Bytes], $i$ = Index ที่ต้องการ, $L$ = Lower Bound)*[cite: 2]

> 💡 **ตัวอย่าง**:
> กำหนดอาร์เรย์ $A[1:5]$ มี $B = 2000$, $C = 1$ Byte จงหาแอดเดรสของ $A[3]$[cite: 2]
> $$\text{Loc}(A[3]) = 2000 + 1 \times (3 - 1) = 2002$$[cite: 2]

---

## 2.3 อาร์เรย์ 2 มิติ (Two-Dimensional Array)[cite: 2]
* **รูปแบบ**: $A[L_1:U_1, L_2:U_2]$ หรือ $A[M, N]$ ($M$ = แถว, $N$ = คอลัมน์)[cite: 2]
  * จำนวนแถว ($M$) $= U_1 - L_1 + 1$[cite: 2]
  * จำนวนคอลัมน์ ($N$) $= U_2 - L_2 + 1$[cite: 2]
  * จำนวนช่องรวม $= M \times N$[cite: 2]
* **การจัดเก็บในหน่วยความจำ**:
  1. **Row Major Order (เรียงตามแถวเป็นหลัก)**:
     $$\text{Loc}(A[i, j]) = B + C \times \left[(i - L_1) \times N + (j - L_2)\right]$$
[cite: 2]
  2. **Column Major Order (เรียงตามคอลัมน์เป็นหลัก)**:
     $$\text{Loc}(A[i, j]) = B + C \times \left[(j - L_2) \times M + (i - L_1)\right]$$
[cite: 2]

> 💡 **ตัวอย่าง**:
> กำหนด $A[1:5, 1:10]$ ($M=5, N=10$), $B = 1050$, $C = 4$ Bytes จงหาแอดเดรส $A[3, 5]$[cite: 2]
> * **Row Major**: $1050 + 4 \times [(3-1) \times 10 + (5-1)] = 1050 + 4 \times 24 = 1146$[cite: 2]
> * **Column Major**: $1050 + 4 \times [(5-1) \times 5 + (3-1)] = 1050 + 4 \times 22 = 1138$[cite: 2]

---

## 2.4 อาร์เรย์ 3 มิติ (Three-Dimensional Array)[cite: 2]
* **รูปแบบ**: $A[L_1:U_1, L_2:U_2, L_3:U_3]$ หรือ $A[L, M, N]$ ($L$ = ชั้น/Pages, $M$ = แถว/Rows, $N$ = คอลัมน์/Cols)[cite: 2]
* **สูตรหาแอดเดรสตำแหน่ง $A[i, j, k]$**:
  1. **Row Major Order**:
     $$\text{Loc}(A[i, j, k]) = B + C \times \left[(i - L_1) \cdot M \cdot N + (j - L_2) \cdot N + (k - L_3)\right]$$
[cite: 2]
  2. **Column Major Order**:
     $$\text{Loc}(A[i, j, k]) = B + C \times \left[(i - L_1) \cdot M \cdot N + (k - L_3) \cdot M + (j - L_2)\right]$$
[cite: 2]