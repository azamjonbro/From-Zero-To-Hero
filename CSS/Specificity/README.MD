# CSS Specificity --- To'liq Qo'llanma

**Specificity** --- brauzer bir elementga tegadigan bir nechta CSS
qoidasidan qaysi biri ustun bo'lishini aniqlaydigan reyting tizimi.

CSS specificity quyidagi formatda baholanadi:

    [a, b, c, d]

  ---------------------------------------------------------------------------
  Bo'lak               Ma'nosi                    Misol
  -------------------- -------------------------- ---------------------------
  **a**                Inline styles              `<div style="color:red">`

  **b**                ID selectorlar             `#header`

  **c**                Class, attribute,          `.btn`, `[type="text"]`,
                       pseudo-class               `:hover`

  **d**                Element, pseudo-element    `div`, `h1`, `::before`
  ---------------------------------------------------------------------------

------------------------------------------------------------------------

## Specificity Hisoblash

### 1. Inline style

    [1, 0, 0, 0]

### 2. ID selector

    #content → [0, 1, 0, 0]

### 3. Class / Attribute / Pseudo-class

    .title → [0, 0, 1, 0]
    [type="text"] → [0, 0, 1, 0]
    :hover → [0, 0, 1, 0]

### 4. Element / Pseudo-element

    p → [0, 0, 0, 1]
    ::after → [0, 0, 0, 1]

------------------------------------------------------------------------

## Specificity Qoidalari

### 1. Specificity baland bo'lsa --- o'sha qoida yutadi

``` css
p { color: red; }
.card p { color: blue; } /* yutadi */
```

### 2. ID --- class'dan kuchli

``` css
.title { color: red; }
#title { color: blue; } /* yutadi */
```

### 3. Inline --- hammasidan kuchli

``` html
<p style="color: green">text</p>
```

### 4. `!important` --- Specificityni oshirmaydi, lekin ustun bo'ladi

``` css
.text { color: red !important; }
#title { color: blue; }
```

------------------------------------------------------------------------

## Amaliy Misol

### Misol 1

``` css
#nav ul li a.link { color: red; }
```

Hisob:

    [0, 1, 1, 3]

### Misol 2

``` css
header nav ul li a:hover { color: blue; }
```

Hisob:

    [0, 0, 1, 5]

------------------------------------------------------------------------

## Xulosa

Specificity quyidagicha tartiblanadi:

1.  Inline
2.  ID
3.  Class / Attribute / Pseudo-class
4.  Element / Pseudo-element
5.  `!important` (barcha specificity qoidalaridan ustun)
------------------------------------------------------------------------

# CSS Selektorlari --- To'liq Qo'llanma
CSS selektorlari HTML elementlarini tanlash uchun ishlatiladi. Ular
turli xil turlarga ega bo'lib, har biri o'ziga xos vazifalarni bajaradi.
CSS’da elementlar o‘zaro munosabatiga asoslanib target qilinadi.
## 5.1. Descendant Selector (`A B`)

```css  
div p { color: blue; }
```
* **Meaning**: `div` ichidagi *har qanday chuqurlikdagi* `p`.
* Specificity: Ikki selektorning yig‘indisi.