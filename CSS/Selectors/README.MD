# CSS Selectors — Advanced, Deep-Dive Explanation (README)

CSS selektorlar — bu DOM ichidagi elementlarni **aniq va qatʼiy qoidalar bo‘yicha target qiladigan** mexanizm. Selektorlar orqali biz stil qoidalarini *qaysi elementga tatbiq etish* kerakligini belgilaymiz. Ushbu hujjat selektorlarni eng chuqur darajada, professional front-end darajasida tushuntiradi.

---

# 1. **Type Selector (Element Selector)**

Element nomi orqali tanlaydi.

```css
p { color: red; }
```

### Xususiyatlari:

* Specificity: **0-0-0-1**
* Barcha shu nomdagi elementlarga taʼsir qiladi.

### Afzalligi:

* Kode yozishda minimalizm va umumiy stylar uchun qulay.

### Kamchiligi:

* Juda global taʼsirga ega.
* Katta loyihalarda tartibsizlikka olib keladi.

---

# 2. **Class Selector**

Nuqta (`.`) bilan belgilanadi.

```css
.card { padding: 20px; }
```

### Specificity: **0-0-1-0**

### Afzalliklari:

* Eng ko‘p ishlatiladigan selektor turi.
* Bir nechta class bir elementda bo‘lishi mumkin.
* Modular CSS: BEM, OOCSS, SMACSS metodologiyalariga mos.

### Kamchiligi:

* Haddan tashqari ko‘p classlar loyihani chalkashtirishi mumkin.

---

# 3. **ID Selector**

`#` bilan boshlanadi.

```css
#header { background: black; }
```

### Specificity: **0-1-0-0** (classdan kuchli)

### Afzalliklari:

* DOMdagi **unikal** elementni target qilish uchun ishlatiladi.

### Kamchiligi:

* Odatda tavsiya etilmaydi, chunki specificity juda kuchli bo‘lib, override qilish qiyin.
* Reusability yo‘q.

---

# 4. **Universal Selector `*`**

```css
* { box-sizing: border-box; }
```

### Specificity: **0-0-0-0**

### Afzalliklari:

* Reset qilishda juda foydali.

### Kamchiligi:

* Performance masalasi: Katta DOM strukturalarda sekinlashishga olib kelishi mumkin.

---

# 5. **Combinators (Kombinatorlar)**

CSS’da elementlar o‘zaro munosabatiga asoslanib target qilinadi.

## 5.1. Descendant Selector (`A B`)

```css
div p { color: blue; }
```

* **Meaning**: `div` ichidagi *har qanday chuqurlikdagi* `p`.
* Specificity: Ikki selektorning yig‘indisi.

### Afzalligi:

* Structural targeting.

### Kamchiligi:

* Juda keng qamrovli.

---

## 5.2. Child Selector (`A > B`)

```css
ul > li { margin: 10px; }
```

* To‘g‘ridan-to‘g‘ri bola elementlar.
* Descendant selector’dan aniqroq.

---

## 5.3. Adjacent Sibling (`A + B`)

```css
h1 + p { font-style: italic; }
```

* `h1` dan keyingi **birinchi** `p`.

---

## 5.4. General Sibling (`A ~ B`)

```css
h1 ~ p { color: red; }
```

* `h1` dan keyingi **barcha** `p`lar.

---

# 6. **Attribute Selectors**

## 6.1. `[attr]`

Element atributga ega bo‘lsa tanlaydi.

```css
input[disabled] { opacity: 0.5; }
```

## 6.2. `[attr="value"]`

Atribut **aniq** qiymatga teng.

## 6.3. `[attr^="val"]` — boshlanishi

## 6.4. `[attr$="val"]` — tugashi

## 6.5. `[attr*="val"]` — ichida qatnashgan

### Afzalliklari:

* HTML forma, SEO teglar, linklar bilan ishlashda juda kuchli.

---

# 7. **Pseudo-Classes**

Elementning *holati* yoki *pozitsiyasi*ga qarab target qiladi.

## 7.1. Interaction Pseudo-classes

* `:hover`
* `:active`
* `:focus`

## 7.2. Position Pseudo-classes

* `:first-child`
* `:last-child`
* `:nth-child(n)`
* `:nth-of-type(n)`
* `:only-child`

### Specificity: **0-0-1-0** (class bilan bir xil)

### Afzalliklari:

* Dynamik UI uchun eng muhim selektorlar.

### Kamchiligi:

* Loyihada noto‘g‘ri ishlatilsa, murakkablikni oshiradi.

---

# 8. **Pseudo-Elements**

Elementning virtual qismlarini target qiladi.

* `::before`
* `::after`
* `::first-letter`
* `::first-line`
* `::selection`

```css
p::before {
  content: "→ ";
  color: gray;
}
```

### Specificity: **0-0-1-0**

### Afzalliklari:

* Dekorativ elementlar qo‘shishda HTMLni iflos qilmaydi.

---

# 9. **Specificity (Selektor ustuvorligi)**

CSS qoidalari konfliktga kirganda eng yuqori specificity g‘olib bo‘ladi.

### Specificity tartibi:

1. Inline style → **1-0-0-0**
2. ID → **0-1-0-0**
3. Class, pseudo-class, attribute → **0-0-1-0**
4. Element → **0-0-0-1**
5. Universal → **0-0-0-0**

---

# 10. **Advanced Selector Patterns**

## 10.1. **BEM Naming + Class Selectors**

Professionallar uchun tavsiya etiladi:

```
.block__element--modifier
```

## 10.2. **Chained Selectors**

```css
button.primary.large {}
```

Bir elementga bir nechta class orqali specificity oshmasdan aniqlik qo‘shadi.

## 10.3. **Attribute Selectors + State UI**

```css
input[type="checkbox"]:checked + label {}
```

Toggle UI yaratishda kuchli texnika.

---

# 11. Performance Masalalari

* `*` universal selektor sekin.
* `A B` (descendant) juda ko‘p elementni tekshiradi.
* Specificity baland bo‘lsa, override qiyinlashadi.

### Optimal tavsiyalar:

* **ID ishlatma** (kirishmaydi).
* **Maximal class-driven CSS yoz**.
* **Deep nesting dan qoch**.
* Pseudo-elementlarni dekor uchun ishlat.

---

# Xulosa

Bu hujjat CSS selektorlarni profesional darajada tushuntiradi:

* Specificity
* Structural selectors
* Pseudo-classes
* Pseudo-elements
* Attribute-based filtering
* Performance qoidalari