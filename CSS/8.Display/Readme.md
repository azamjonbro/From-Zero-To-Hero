# CSS `display` Advanced Guide

CSS `display` — bu HTML elementning sahifada qanday joylashishi, qanday blok modelda ishtirok etishi va boshqa elementlar bilan qanday aloqada bo‘lishini belgilaydigan eng asosiy layout xossasidir.

Ushbu `readme.md` sizga `display` xossasining **eng to‘liq**, **professional**, **advanced** tushuntirishini beradi.

---

# # 1. Asosiy `display` qiymatlari

## ## 1.1 `display: block`

**Block-level** elementlar:

* doim yangi qatordan boshlanadi
* width → 100% (default)
* height, padding, margin to‘liq ishlaydi

Misol elementlar: `div`, `p`, `h1`–`h6`, `section`

```css
div {
  display: block;
}
```

---

## ## 1.2 `display: inline`

**Inline elementlar:**

* yangi qatordan boshlanmaydi
* width/height ishlamaydi
* faqat content kattaligi bilan o‘lchanadi

Misollar: `span`, `a`, `em`

```css
span {
  display: inline;
}
```

---

## ## 1.3 `display: inline-block`

Block + inline xulqning aralash turi.

* qatordan chiqmaydi
* width/height ishlaydi

Buttonlar, badge-lar va UI elementlarda eng ko‘p ishlatiladi.

```css
button {
  display: inline-block;
}
```

---

## ## 1.4 `display: none`

Element:

* ko‘rinmaydi
* sahifada joy egallamaydi
* DOMda mavjud, lekin UIda yo‘q

`visibility: hidden`dan farqi → joy egallamaydi.

---

# # 2. Flexbox — zamonaviy layout modeli

## ## 2.1 `display: flex`

Elementni **flex container**ga aylantiradi.

* elementlar bir qatorda bo‘ladi
* joylashuv juda moslashuvchan
* responsive uchun eng qulay model

```css
.container {
  display: flex;
  gap: 20px;
}
```

### Flex asosiy xossalari:

* `flex-direction`
* `justify-content`
* `align-items`
* `flex-wrap`
* `flex-grow`
* `flex-shrink`

---

## ## 2.2 `display: inline-flex`

Flex, lekin elementning o‘zi inline bo‘lib qoladi.

```css
.wrapper {
  display: inline-flex;
}
```

---

# # 3. CSS Grid — eng kuchli layout modeli

## ## 3.1 `display: grid`

Ikki o‘lchamli (2D) layout: rows va columns.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}
```

### Grid asosiy xossalari:

* `grid-template-columns`
* `grid-template-rows`
* `grid-template-areas`
* `place-items`
* `place-content`

---

## ## 3.2 `display: inline-grid`

Grid struktura, lekin inline xulq.

---

# # 4. Kamroq ishlatiladigan, lekin muhim `display` qiymatlari

## ## 4.1 `display: list-item`

Element `<li>` kabi ishlaydi.

```css
div {
  display: list-item;
}
```

---

## ## 4.2 `display: table`, `display: table-cell`

HTML `<table>`siz table-style layout. Modern dizaynlarda kam ishlatiladi.

---

## ## 4.3 `display: contents` (Juda ADVANCED)

Element **yo‘qoladi**, faqat uning ichidagi bolalar DOMda qoladi.
UI komponent kutubxonalarida ko‘p ishlatiladi.

```css
.wrapper {
  display: contents;
}
```

---

## ## 4.4 `display: flow-root` (float muammosi uchun ideal)

Element **yangi block formatting context** yaratadi.
Bu floatli layoutlarda keraksiz oqim buzilishlarini tuzatadi.

```css
.card {
  display: flow-root;
}
```

---

# # 5. Qaysi layoutga qaysi display?

| Holat                   | Tavsiya display |
| ----------------------- | --------------- |
| Katta bloklar           | block           |
| Matn elementlari        | inline          |
| Button/icon             | inline-block    |
| 1D layout (row/column)  | flex            |
| 2D layout (rows + cols) | grid            |
| Elementni yashirish     | none            |
| Wrapperni yo‘qotish     | contents        |
| Floatni to‘g‘rilash     | flow-root       |

---

# # 6. Eng keng tarqalgan xatolar

### ❌ `display: inline` → width ishlamaydi

Bu tabiiy.

### ❌ `display: none` bilan animatsiya qilish

Animatsiya qilinmaydi (zerodan birdan o‘chadi/yoqiladi).

### ❌ Flex ichida `text-align` ishlamaydi

Flex itemlarni joylash uchun `justify-content` ishlatiladi.

### ❌ Inline-block elementlar orasida bo‘sh joy

HTML whitespace sabab.


