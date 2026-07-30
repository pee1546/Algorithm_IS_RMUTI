# บทที่ 5: โครงสร้างข้อมูลแบบลิงค์ลิสต์ (Linked List Data Structure)[cite: 5]

## 5.1 ความหมายและโครงสร้างโหนด (Node)[cite: 5]
* **ลิงค์ลิสต์**: โครงสร้างข้อมูลเชิงเส้นขนาดยืดหยุ่น (Dynamic Structure) ไม่จำเป็นต้องเก็บเรียงติดกันในหน่วยความจำ[cite: 5]
* **องค์ประกอบของ 1 โหนด**:
  $$\text{[ INFO / DATA } | \text{ LINK / NEXT / POINTER ]}$$[cite: 5]
  * `INFO`: เก็บข้อมูลจริง[cite: 5]
  * `LINK`: เก็บแอดเดรสชี้ไปยังโหนดถัดไป (โหนดสุดท้ายชี้ `NULL` หรือ `^`)[cite: 5]
* **Storage Pool & `AVAIL`**: กลุ่มโหนดว่างในหน่วยความจำ ชี้โดย Pointer ชื่อ `AVAIL`[cite: 5]

---

## 5.2 Singly Linked List (ลิงค์ลิสต์เดี่ยว)[cite: 5]
มีตัวชี้ทิศทางเดียว ชี้จากโหนดหน้าไปโหนดหลัง[cite: 5]

### อัลกอริทึมปฏิบัติการที่สำคัญ:
1. **การสร้างโหนดแรก**:
   `New(P)`, `Data(P) = X`, `Next(P) = NULL`, `Head = P`, `Tail = P`[cite: 5]
2. **การเพิ่มโหนดต่อท้าย (Append)**:
   `New(P)`, `Data(P) = X`, `Next(P) = NULL`, `Next(Tail) = P`, `Tail = P`[cite: 5]
3. **การเพิ่มโหนดก่อนหน้าโหนดแรก (Prepend)**:
   `New(P)`, `Data(P) = X`, `Next(P) = Head`, `Head = P`[cite: 5]
4. **การแทรกโหนดใหม่ไว้หลังโหนด P**:
   * `Next(Newnode) = Next(P)` *(ต้องทำขั้นตอนนี้ก่อนเสมอ)*[cite: 5]
   * `Next(P) = Newnode`[cite: 5]
5. **การลบโหนดแรก**:
   `Head = Next(Head)`[cite: 5]
6. **การลบโหนดตรงกลาง (ลบโหนดถัดจาก BeforeP)**:
   `Next(BeforeP) = Next(P)`[cite: 5]

---

## 5.3 Doubly Linked List (ลิงค์ลิสต์คู่)[cite: 5]
แต่ละโหนดมีพอยน์เตอร์ 2 ทิศทาง:
$$\text{[ LLINK / PREV } | \text{ DATA } | \text{ RLINK / NEXT ]}$$[cite: 5]

* **LLINK / PREV**: ชี้โหนดก่อนหน้า[cite: 5]
* **RLINK / NEXT**: ชี้โหนดถัดไป[cite: 5]

### อัลกอริทึมการแทรกและลบ:
* **แทรกโหนดใหม่หลังโหนด P**:
  1. `Prev(Next(P)) = Newnode`[cite: 5]
  2. `Next(Newnode) = Next(P)`[cite: 5]
  3. `Prev(Newnode) = P`[cite: 5]
  4. `Next(P) = Newnode`[cite: 5]
* **ลบโหนด P ตรงกลาง**:
  1. `Next(Prev(P)) = Next(P)`[cite: 5]
  2. `Prev(Next(P)) = Prev(P)`[cite: 5]

---

## 5.4 ลิงค์ลิสต์แบบวงกลม (Circular Linked List)[cite: 5]
* **Circular Singly Linked List**: `Next` ของโหนดสุดท้ายชี้กลับมาที่ `Head`[cite: 5]
* **Circular Doubly Linked List**: `RLINK` ของโหนดสุดท้ายชี้มาที่ `Head` และ `LLINK` ของโหนดแรกชี้ไปที่ `Tail`[cite: 5]