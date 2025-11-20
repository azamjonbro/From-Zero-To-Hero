# CSS va Box Model haqida to'liq tushuncha

Ushbu README sizga **CSS** va **CSS Box Model** tushunchalarini to‘liq, sodda va amaliy tarzda tushuntirib beradi.

---

## CSS nima?

**CSS (Cascading Style Sheets)** — bu HTML elementlariga **dizayn, uslub, rang, joylashuv** berish uchun ishlatiladigan uslublar tili.

HTML = tuzilma
CSS = ko'rinish (dizayn)

### CSS yordamida qilinadi:

* Ranglar berish
* Shrftlar o‘lchamini o‘zgartirish
* Elementlarni markazlashtirish
* Margin / padding qo‘shish
* Border yaratish
* Layout: flex, grid
* Animatsiya yaratish

---

## CSS qanday ulanishi mumkin?

### **1️⃣ Inline CSS**

```html
<p style="color:red;">Salom</p>
```

### **2️⃣ Internal CSS**

```html
<style>
  p {
    color: red;
  }
</style>
```

### **3️⃣ External CSS (tavsiya etiladi)**

**style.css:**

```css
p {
  color: red;
}
```

**HTML:**

```html
<link rel="stylesheet" href="style.css">
```

---

## 📦 CSS Box Model nima?

Har bir HTML elementi aslida **kvadrat (quti)** ko‘rinishida bo‘ladi va 4 qismdan iborat:

```
+---------------------------+
|        margin             |
|  +---------------------+  |
|  |       border        |  |
|  |  +---------------+  |  |
|  |  |    padding     | |  |
|  |  | +-----------+ | |  |
|  |  | |  content  | | |  |
|  |  | +-----------+ | |  |
|  |  +---------------+  |  |
|  +---------------------+  |
+---------------------------+
```

### **1) Content**

Matn yoki rasm joylashadigan asosiy maydon.

### **2) Padding**

Content atrofidagi ichki bo‘sh joy.

```css
padding: 20px;
```

### **3) Border**

Elementning chegarasi.

```css
border: 2px solid black;
```

### **4) Margin**

Element tashqi tomondagi bo‘sh joy.

```css
margin: 20px;
```

---

## Box Model hisoblanishi

```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 5px solid red;
  margin: 30px;
}
```

**Real kenglik hisoblanishi:**

```
width + padding + border
200 + 20 + 20 + 5 + 5 = 250px
```

---

## `box-sizing` xulqi

### **content-box (default)**

`width` faqat contentga tegishli.

### **border-box (tavsiya etiladi)**

`width` ichiga padding va border ham kiradi.

```css
* {
  box-sizing: border-box;
}
```

Natija: element o‘lchami **aniq** bo‘ladi.

---

## Qisqa eslab qolish jadvali

| Qism        | Vazifa           |
| ----------- | ---------------- |
| **Content** | Matn / rasm joyi |
| **Padding** | Ichki bo‘sh joy  |
| **Border**  | Chegara          |
| **Margin**  | Tashqi bo‘sh joy |

---

## ✔ Amaliy misol

```css
div {
  width: 300px;
  padding: 20px;
  border: 10px solid black;
  margin: 20px;
}
```

**Haqiqiy width:**
`300 + 40 + 20 = 360px`