# HTML Semantikasi

HTML semantikasi — bu HTML elementlarining ma'nosini va ularning veb-sahifadagi rolini aniqlashga yordam beradigan tamoyillar to'plamidir. Semantik elementlar brauzerlar, yordamchi texnologiyalar va dasturchilar uchun kontentning tuzilishini aniqroq ko'rsatadi.

## Asosiy semantik elementlar

- `<header>` — sahifa yoki bo'lim sarlavhasi
- `<nav>` — navigatsiya menyusi
- `<main>` — asosiy kontent
- `<section>` — tematik bo'lim
- `<article>` — mustaqil kontent (maqola, blog posti)
- `<aside>` — asosiy kontentdan tashqari ma'lumotlar (yon panel)
- `<footer>` — sahifa yoki bo'limning pastki qismi

## Semantik elementlardan foydalanish afzalliklari

- **SEO** (Qidiruv tizimlari optimizatsiyasi) uchun qulaylik
- **Accessibility** (foydalanuvchilar uchun qulaylik, jumladan, ekranni o'qiydiganlar)
- Kodingizni o'qish va tushunishni osonlashtiradi

## Misol

```html
<!DOCTYPE html>
<html lang="uz">
 <head>
  <meta charset="UTF-8">
  <title>HTML Semantikasi</title>
 </head>
 <body>
  <header>
   <h1>HTML Semantikasi</h1>
   <nav>
    <ul>
     <li><a href="#asosiy">Asosiy</a></li>
     <li><a href="#kontakt">Kontakt</a></li>
    </ul>
   </nav>
  </header>
  <main>
   <section>
    <h2>Semantik elementlar haqida</h2>
    <p>HTML semantikasi veb-sahifa tuzilishini aniq ko'rsatadi.</p>
   </section>
   <article>
    <h2>Semantik elementlar misollari</h2>
    <p>Yuqoridagi elementlar veb-sahifani to'g'ri tuzishda yordam beradi.</p>
   </article>
   <aside>
    <p>Qo'shimcha ma'lumotlar yoki reklama joylash mumkin.</p>
   </aside>
  </main>
  <footer>
   <p>&copy; 2024 HTML Semantika</p>
  </footer>
 </body>
</html>
```

## Foydali manbalar

- [MDN Web Docs: Semantics](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
- [HTML Living Standard](https://html.spec.whatwg.org/)
- [W3Schools: HTML Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)


## Semantik elementlardan foydalanmaslik oqibatlari

Agar semantik elementlardan foydalanilmasa, quyidagi muammolar yuzaga kelishi mumkin:

- **SEO yomonlashadi** — Qidiruv tizimlari sahifani to'g'ri indekslay olmaydi, natijada sahifa reytingi pasayadi.
- **Accessibility pasayadi** — Ekranni o'qiydiganlar va yordamchi texnologiyalar kontentni to'g'ri aniqlay olmaydi.
- **Kodni tushunish qiyinlashadi** — Dasturchilar uchun kod strukturasini anglash va ishlash murakkablashadi.
- **Brauzerlar uchun noaniqlik** — Brauzerlar sahifa tuzilishini noto'g'ri ko'rsatishi mumkin.

Semantik elementlardan tashqarida oddiy `<div>` va `<span>` kabi elementlardan foydalanish mumkin, lekin ular kontent ma'nosini ifodalamaydi. Bu esa yuqoridagi muammolarga olib keladi.
