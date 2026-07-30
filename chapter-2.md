## บทที่ 2: โครงสร้างข้อมูลแบบอาร์เรย์ (Array Data Structure)

### 2.1 คุณลักษณะของอาร์เรย์
1. **Homogeneous Data Type**: สมาชิกทุกตัวต้องมีประเภทข้อมูลเดียวกัน
2. **Contiguous Memory**: จัดเก็บในหน่วยความจำเรียงติดต่อกัน
3. **Static Structure**: มีขนาดแน่นอน จองพื้นที่ล่วงหน้า
4. **Random Access**: เข้าถึงสมาชิกทุกตัวได้โดยตรงผ่าน Index/Subscript ด้วยเวลา $O(1)$

### 2.2 อาร์เรย์ 1 มิติ (One-Dimensional Array)
* **การคำนวณจำนวนช่อง (Total Elements)**:
  $$	ext{Elements} = U - L + 1$$
  *(เมื่อ $U$ คือ Upper Bound, $L$ คือ Lower Bound)*
* **การคำนวณขนาดความจุ (Capacity in Bytes)**:
  $$	ext{Capacity} = (U - L + 1) 	imes 	ext{Size}$$
* **สูตรคำนวณแอดเดรสตำแหน่ง $A[i]$ในหน่วยความจำ**:
  $$	ext{Loc}(A[i]) = B + C 	imes (i - L)$$
  * $B$ = Base Address (แอดเดรสเริ่มต้น)
  * $C$ = ขนาดของข้อมูลแต่ละช่อง (Bytes)
  * $i$ = Index ตำแหน่งที่ต้องการหา
  * $L$ = Lower Bound (ตำแหน่งแรกของอาร์เรย์)

> 💡 **ตัวอย่างคำนวณ 1 มิติ**:
> กำหนดให้อาร์เรย์ $A[1:5]$ มี Base Address ($B$) = 2000, ขนาดข้อมูลแต่ละช่อง ($C$) = 1 Byte
> จงหาแอดเดรสของ $A[3]$:
> $$	ext{Loc}(A[3]) = 2000 + 1 	imes (3 - 1) = 2000 + 2 = 2002$$

### 2.3 อาร์เรย์ 2 มิติ (Two-Dimensional Array)
* **รูปแบบ**: $A[L_1:U_1, L_2:U_2]$ หรือ $A[M, N]$ โดย $M$ = จำนวนแถว (Rows), $N$ = จำนวนคอลัมน์ (Columns)
  * $M = U_1 - L_1 + 1$
  * $N = U_2 - L_2 + 1$
* **จำนวนช่องทั้งหมด**: $M 	imes N = (U_1 - L_1 + 1) 	imes (U_2 - L_2 + 1)$
* **รูปแบบการจัดเก็บในหน่วยความจำ**:
  1. **เรียงตามแถวเป็นหลัก (Row Major Order)**: จัดเก็บทีละแถวเรียงกันไป
     $$	ext{Loc}(A[i, j]) = B + C 	imes \left[(i - L_1) 	imes N + (j - L_2)
ight]$$
  2. **เรียงตามคอลัมน์เป็นหลัก (Column Major Order)**: จัดเก็บทีละคอลัมน์เรียงกันไป
     $$	ext{Loc}(A[i, j]) = B + C 	imes \left[(j - L_2) 	imes M + (i - L_1)
ight]$$

> 💡 **ตัวอย่างคำนวณ 2 มิติ**:
> กำหนดอาร์เรย์ $A[1:5, 1:10]$ ($M=5, N=10$), $B = 1050$, $C = 4$ Bytes จงหาแอดเดรส $A[3, 5]$
> * **Row Major Order**:
>   $$	ext{Loc}(A[3, 5]) = 1050 + 4 	imes \left[(3-1) 	imes 10 + (5-1)
ight] = 1050 + 4 	imes (20 + 4) = 1050 + 96 = 1146$$
> * **Column Major Order**:
>   $$	ext{Loc}(A[3, 5]) = 1050 + 4 	imes \left[(5-1) 	imes 5 + (3-1)
ight] = 1050 + 4 	imes (20 + 2) = 1050 + 88 = 1138$$

### 2.4 อาร์เรย์ 3 มิติ (Three-Dimensional Array)
* **รูปแบบ**: $A[L_1:U_1, L_2:U_2, L_3:U_3]$ หรือ $A[L, M, N]$
  * $L$ = จำนวนชั้น/ความลึก (Pages) $= U_1 - L_1 + 1$
  * $M$ = จำนวนแถว (Rows) $= U_2 - L_2 + 1$
  * $N$ = จำนวนคอลัมน์ (Columns) $= U_3 - L_3 + 1$
* **จำนวนช่องทั้งหมด**: $L 	imes M 	imes N$
* **สูตรหาแอดเดรสตำแหน่ง $A[i, j, k]$**:
  1. **Row Major Order**:
     $$	ext{Loc}(A[i, j, k]) = B + C 	imes \left[(i - L_1) 	imes M 	imes N + (j - L_2) 	imes N + (k - L_3)
ight]$$
  2. **Column Major Order**:
     $$	ext{Loc}(A[i, j, k]) = B + C 	imes \left[(i - L_1) 	imes M 	imes N + (k - L_3) 	imes M + (j - L_2)
ight]$$

---