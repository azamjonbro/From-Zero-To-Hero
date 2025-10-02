# biz shu vaqtgacha html haqida malumot yig'dik

endi biz bu ichida ishlatiladigan taglarni to'liq qoidasi bilan ko'rib chiqishimiz kerak.

masalan har doim ishlatiladigan ```p``` tagi bu doim malumotlarni yozish uchun va oynada bu oddiy default holatda chiqishi uchun ishlatiladi. Va endi bir nechta do'stlari bor yani ularni vazifasiga ko'ra matnni istalgan qismida ishlatish mumkin bo'lgan taglar mavjud.

Quyidagi taglar matnni turli usullarda ko'rsatish uchun ishlatiladi:

- **`<b>`** — Matnni qalin qilib ko'rsatadi.  
 Misol: `<b>Bu qalin matn</b>` → **Bu qalin matn**

- **`<strong>`** — Matnga kuchli urg'u beradi, ya'ni muhimligini bildiradi.  
 Misol: `<strong>Bu muhim matn</strong>` → **Bu muhim matn**

- **`<em>`** — Matnga urg'u beradi, ya'ni e'tibor qaratadi.  
 Misol: `<em>Bu urg'uli matn</em>` → *Bu urg'uli matn*

- **`<i>`** — Matnni kursiv (egilgan) qilib ko'rsatadi.  
 Misol: `<i>Bu kursiv matn</i>` → *Bu kursiv matn*

- **`<del>`** — Matnni o'chirilgan (chiziq bilan o'ralgan) qilib ko'rsatadi.  
 Misol: `<del>Bu o'chirilgan matn</del>` → ~~Bu o'chirilgan matn~~

- **`<u>`** — Matnni tagiga chiziq tortib ko'rsatadi.  
 Misol: `<u>Bu tagi chiziqli matn</u>` → <u>Bu tagi chiziqli matn</u>

Bu taglarning barchasi oddiy matnni turli ko'rinishda chiqarish uchun ishlatiladi.


## HTML taglar: Blok va Inline

HTML taglari ikki asosiy turga bo'linadi: **blok** va **inline**.

### Blok taglar

Blok taglar har doim yangi qatordan boshlanadi va butun kenglikni egallaydi. Ular ichida boshqa taglar ham bo'lishi mumkin. Eng ko'p ishlatiladigan blok taglar:

- `<div>` — umumiy konteyner, bo'lim yaratish uchun.
- `<p>` — paragraf, matn bo'lagi.
- `<h1>`, `<h2>`, ... `<h6>` — sarlavhalar.
- `<ul>`, `<ol>`, `<li>` — ro'yxatlar.
- `<table>` — jadval.

### Inline taglar

Inline taglar esa faqat o'z joyini egallaydi va yangi qatordan boshlanmaydi. Tepada ko'rib chiqqan `<b>`, `<i>`, `<u>`, `<em>`, `<strong>` va `<del>` taglari inline hisoblanadi.

**Xulosa:**  
Blok taglar butun kenglikni egallaydi va yangi qatordan boshlanadi, inline taglar esa faqat o'z joyida ko'rinadi va matn ichida ishlatiladi.

## HTML taglarni birga ishlatish

Ko'pincha blok va inline taglar birga ishlatiladi. Masalan, paragraf ichida matnni qalin yoki kursiv qilish mumkin:

```html
<p>Bu <b>qalin</b> va <i>kursiv</i> matn.</p>
```

Natija:  
Bu **qalin** va *kursiv* matn.

## Amaliy misol

Quyidagi kodda blok va inline taglar birga ishlatilgan:

```html
<div>
 <h2>HTML taglar misoli</h2>
 <p>Bu <strong>muhim</strong> va <em>urg'uli</em> matn.</p>
 <ul>
  <li><u>Tagi chiziqli</u> element</li>
  <li><del>O'chirilgan</del> element</li>
 </ul>
</div>
```

Bu misolda `<div>` blok sifatida, `<h2>`, `<p>`, `<ul>` va `<li>` ham blok taglar, `<strong>`, `<em>`, `<u>`, `<del>` esa inline taglar sifatida ishlatilgan.

## Foydali maslahatlar

- Har bir tagning vazifasini va joyini to'g'ri tanlang.
- Blok taglar ichida inline taglarni ishlatish mumkin.
- HTML kodni toza va tartibli yozishga harakat qiling.

Keyingi bosqichda har bir tagning atributlari va ularni qanday ishlatish haqida o'rganamiz.


## HTML taglarni qanday ishlatish

HTML taglarni ishlatish juda oddiy. Har bir tag ochuvchi (`<tag>`) va yopuvchi (`</tag>`) shaklda yoziladi. Matn yoki boshqa elementlar shu taglar orasida joylashadi.

### Oddiy misollar

```html
<p>Bu oddiy paragraf matni.</p>
<b>Bu qalin matn.</b>
<i>Bu kursiv matn.</i>
<u>Bu tagi chiziqli matn.</u>
```

### Bir nechta taglarni birga ishlatish

Taglarni birga ishlatib, matnga turli ko'rinish berish mumkin:

```html
<p>Bu <b>qalin</b> va <i>kursiv</i> matn.</p>
```

### Blok va inline taglarni birga ishlatish

Blok taglar ichida inline taglarni ishlatish keng tarqalgan:

```html
<div>
 <h3>Misol sarlavhasi</h3>
 <p><strong>Muhim</strong> va <em>urg'uli</em> matn.</p>
</div>
```

### HTML fayl tuzilmasi

HTML kodni to'g'ri ishlatish uchun uni to'liq fayl ko'rinishida yozish mumkin:

```html
<!DOCTYPE html>
<html>
 <head>
  <title>HTML taglar misoli</title>
 </head>
 <body>
  <h1>Salom, HTML!</h1>
  <p>Bu <b>qalin</b> va <i>kursiv</i> matn.</p>
 </body>
</html>
```

**Eslatma:**  
Har bir tagni to'g'ri ochib-yoping va ichki tartibga e'tibor bering.

Endi siz HTML taglarni qanday ishlatishni bilasiz!