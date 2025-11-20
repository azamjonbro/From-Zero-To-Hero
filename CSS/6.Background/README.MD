# CSS `background` Advanced Guide

CSS background — bu sahifani vizual jihatdan boyitish, dizaynni chuqurlashtirish va elementlarga estetika berish uchun ishlatiladigan eng kuchli vositalardan biridir. Juda ko‘p loyihalarda hech qanday rasm yoki bezak elementlar joylashtirmasdan, faqat background yordamida chiroyli, professional dizaynlar yaratish mumkin.

Ushbu qo'llanma sizga CSS background tizimini chuqur (advanced) darajada tushuntirib beradi.

---

## ## `background` vs `background-image` — Asosiy farqlar

CSS’da background bilan ishlaganda har doim bir savol tug‘iladi: "qaysi biri yaxshi — `background`mi yoki `background-image`?"

Bu savolga javob juda oddiy:

### ### ✔ `background` — Shorthand (qisqa) yozuv

Agar siz bir elementga **bir vaqtning o'zida**:

* background rangi,
* rasm manzili,
* rasmning joylashuvi,
* rasmning kattaligi,
* qaytarilish-qaytarilmasligi,
* qaysi hududdan boshlanishi,
* scroll yoki fixed bo‘lishi

kabi **bir nechta xususiyatlarni bir joyda** yozmoqchi bo‘lsangiz, **faqat `background:` shorthand** ishlatiladi.

**Sintaksis:**

```
background: [background-color]
            [background-image]
            [background-position] / [background-size]
            [background-repeat]
            [background-attachment]
            [background-origin]
            [background-clip]
            [background-blend-mode];
```

Bu tartib qat’iy shart emas — CSS parsers o‘zi to‘g‘ri ajratadi.

**Misol:**

```
background: url(bg.jpg) center/cover no-repeat fixed border-box content-box multiply;
```

Bu bir qatorda juda ko‘p parametrni boshqarishga imkon beradi.

---

### ### ✔ `background-image` — faqat rasm belgilaydi

Agar sizga faqat rasmni ko‘rsatish kerak bo‘lsa, yoki xossalarni **alohida-alohida** boshqarishni xohlasangiz, unda `background-image` ishlatiladi.

**Misol:**

```
background-image: url(bg.jpg);
background-repeat: no-repeat;
background-position: center;
background-size: cover;
```

Bu usul ko‘proq **an’anaviy va aniq boshqaruv** uchun ishlatiladi.

---

## ## Har bir background xossasining chuqur (advanced) tahlili

Keling backgroundning barcha asosiy xossalarini professional darajada ko‘rib chiqamiz.

---

## ### 1. `background-color`

Elementning orqa fon rangini belgilaydi.

```
background-color: #000;
```

---

## ### 2. `background-image`

Orqa fon sifatida rasm, gradient yoki ko‘p rasm ulanganda foydalaniladi.

```
background-image: url(image.jpg);
background-image: linear-gradient(45deg, red, blue);
background-image: url(layer1.png), url(layer2.svg);
```

**Multiple background** — juda kuchli texnika.

---

## ### 3. `background-position`

Rasmning element ichida qayerda turishini belgilaydi.

Standart qiymatlar:

* `left`, `center`, `right`
* `top`, `center`, `bottom`

**Advanced qiymatlar:**

```
background-position: 20% 80%;
background-position: calc(100% - 20px) center;
```

---

## ### 4. `background-size`

Rasmning qanchalik kattalikda ko‘rinishini belgilaydi.

Eng muhim qiymatlar:

* `cover` → rasm ekran bo‘ylab to‘liq yopadi (qirqib yuboriladi)
* `contain` → rasm elementga sig‘diriladi (bo‘sh joy qolishi mumkin)
* `auto` → asl o‘lcham

**Misol:**

```
background-size: cover;
```

---

## ### 5. `background-repeat`

Rasm takrorlanishini boshqaradi.

Qiymatlar:

* `repeat` (default)
* `no-repeat`
* `repeat-x`
* `repeat-y`
* `space` — rasm orasida bo‘sh joy qoldiradi
* `round` — rasmlar sig‘adigan qilib qayta o‘lchamlaydi

---

## ### 6. `background-attachment`

Rasmning scrollga qanday munosabatda bo‘lishini belgilaydi.

Eng mashhur qiymat:

* `fixed` → Parallax effekt yaratadi

Misol:

```
background-attachment: fixed;
```

Bu sahifa scroll bo‘lganda rasm joyida turadi.

---

## ### 7. `background-origin`

Background rasm qaysi hududdan boshlanishini belgilaydi.

Qiymatlar:

* `padding-box`
* `border-box`
* `content-box`

---

## ### 8. `background-clip`

Background rasm elementning qaysi qismida ko‘rinishini belgilaydi.

Qiymatlar:

* `border-box`
* `padding-box`
* `content-box`
* `text` → backgroundni text ichiga joylaydi (**super advanced**)!

Misol:

```
background-clip: text;
color: transparent;
```

---

## ### 9. `background-blend-mode`

Ko‘p rasm yoki ranglar bir-biri bilan qanday aralashishini belgilaydi.

Photoshop blending rejimlari bilan bir xil:

* `multiply`
* `overlay`
* `screen`
* `darken`
* `lighten`
* `difference`

**Example:**

```
background-blend-mode: multiply;
```

---

# ## Yakuniy xulosa

**`background` — bu kompleks, shorthand ishlatish uchun eng qulay variant.**
Agar siz ko‘p parametrlarni bir qatorda boshqarishni xohlasangiz, aynan shuni ishlating.

**`background-image` — faqat rasm ko‘rsatish uchun, yoki har bir xossani alohida yozmoqchi bo‘lsangiz ishlatiladi.**

Agar dizayn professional bo‘lishini xohlasangiz — backgroundning barcha xossalarini chuqur tushunish juda muhim.
