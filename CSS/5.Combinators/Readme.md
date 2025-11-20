# CSS Combinators --- Advanced Guide

CSS Combinators elementlar orasidagi **munosabat**ni ifodalaydi va
selektorlarning kuchini oshirishda muhim rol o'ynaydi. W3Schools'dagi
ma'lumot yetarli, ammo bu hujjat **professional darajada
chuqurlashtirilgan, real misollar, edge-case**lar bilan to'ldirilgan.

------------------------------------------------------------------------

# 📌 1. Descendant Combinator ( `A B` )

**A B** → A ichidagi **istalgan chuqurlikdagi** B elementlarga ta'sir
qiladi.

### Misol:

``` css
.card p {
  color: #333;
}
```

### Advanced:

-   Juda keng qamrovli, shuning uchun **performansga eng ko'p zarba
    beradi**.
-   Shaxsiylashtirish uchun *too generic* bo'lishi mumkin.
-   Large DOM'larda *accidental styling*ga olib kelishi mumkin.

### Must Avoid:

``` css
.container * {
  margin: 0;
}
```

Bu layoutni buzadi va troubleshootingni qiyinlashtiradi.

------------------------------------------------------------------------

# 📌 2. Child Combinator ( `A > B` )

**A \> B** → faqat **bevosita farzand** elementlar.

### Misol:

``` css
ul > li {
  list-style-type: none;
}
```

### Advanced:

-   Descendant selektoriga nisbatan *ancha tez ishlaydi*.
-   UI komponentlar tuzilmasida ishonchli natija beradi.
-   **Shadow DOM** bilan ishlaganda ham barqaror.

------------------------------------------------------------------------

# 📌 3. Adjacent Sibling Combinator ( `A + B` )

**A + B** → A dan keyin **darhol** keladigan B element.

### Misol:

``` css
input + label {
  color: blue;
}
```

### Advanced:

-   Form validation UI yaratishda kuchli vosita.
-   Bir xil type bo'lmagan elementlarda ham ishlaydi.
-   CSS animation trigger qilishda ishlatiladi:

``` css
.checkbox:checked + .toggle {
  transform: translateX(20px);
}
```

------------------------------------------------------------------------

# 📌 4. General Sibling Combinator ( `A ~ B` )

**A \~ B** → A'dan keyin keladigan **barcha ukalar** (faqat o'sha parent
ostida).

### Misol:

``` css
h2 ~ p {
  opacity: .6;
}
```

### Advanced:

-   Large forms, steps, timelines'da juda effektiv.
-   Event-driven UI'da CSS-only logika yaratish mumkin:

``` css
input:checked ~ .panel {
  display: block;
}
```

------------------------------------------------------------------------

# 🔥 SPECIAL ADVANCED SECTION

## 5. :is() bilan Combinatorlar

``` css
.card :is(h1, h2, h3) + p {
  margin-top: 0;
}
```

## 6. :has() bilan Combinatorlar (CSS Parent Selector!)

``` css
.card:has(img) {
  border-color: gold;
}
```

## 7. Multiple Combinator Chaining

``` css
.nav > ul li + li > a:hover {
  color: red;
}
```

------------------------------------------------------------------------

# ⚙️ Performance Ranking (Fast → Slow)

1.  `A > B` (child)
2.  `A + B` (adjacent)
3.  `A ~ B` (general sibling)
4.  `A B` (descendant -- eng sekin!)

------------------------------------------------------------------------

# ✔️ Best Practices

-   Component-based arhitekturaga mos bo'lsin.
-   Descendant selektorlarini minimal ishlat.
-   `:has()` bilan DOM manipulation'siz interaktiv UI yarat.

------------------------------------------------------------------------

# 📚 Xulosa

CSS Combinators --- oddiy ko'rinishiga qaramay, ular orqali: - kuchli
selektorlar yaratish - performansni saqlash - tartibli architecture
qurish - JavaScript'siz interaktiv UI lar qilish

mumkin.

Full advanced documentation yuqorida to'liq keltirilgan.
