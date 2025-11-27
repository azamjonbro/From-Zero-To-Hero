# JavaScript Texnologiyalari Umumiy Ko'rinish

HTML veb-sahifaning tuzilmasi va tarkibini belgilaydi, CSS esa formatlash va ko'rinishni belgilasa, JavaScript veb-sahifaga interaktivlik qo'shadi va boy veb-ilovalarni yaratadi.

Biroq, brauzer kontekstida tushuniladigan "JavaScript" atamasi bir nechta juda turli xil elementlarni o'z ichiga oladi. Ulardan biri asosiy til (ECMAScript), ikkinchisi esa DOM (Document Object Model) ni o'z ichiga olgan Web API larining to'plami.

## JavaScript, asosiy til (ECMAScript)

JavaScript ning asosiy tili ECMA TC39 qo'mitasi tomonidan ECMAScript nomi bilan standartlashtirilgan. "ECMAScript" til standarti uchun atama, lekin "ECMAScript" va "JavaScript" bir-birining o'rnida ishlatilishi mumkin.

Bu asosiy til brauzerdan tashqari muhitlarda ham qo'llaniladi, masalan Node.js da.

### ECMAScript qamrovi ostiga nima kiradi?

Boshqa narsalar qatori, ECMAScript quyidagilarni belgilaydi:

- Til sintaksisi (tahlil qilish qoidalari, kalit so'zlar, boshqaruv oqimi, ob'ekt literal initsializatsiyasi, ...)
- Xatolarni boshqarish mexanizmlari (throw, try...catch, foydalanuvchi tomonidan belgilangan Error turlarini yaratish qobiliyati)
- Turlar (boolean, number, string, function, object, ...)
- Prototipga asoslangan meros mexanizmi
- O'rnatilgan ob'ektlar va funksiyalar, jumladan JSON, Math, Array metodlari, parseInt, decodeURI va boshqalar
- Qat'iy rejim (Strict mode)
- Modul tizimi
- Asosiy xotira modeli

### Standartlashtirish jarayoni

ECMAScript nashrlari har yili ECMA Bosh Assambleyasi tomonidan standart sifatida tasdiqlanadi va nashr etiladi. Barcha ishlanmalar Ecma TC39 GitHub tashkilotida ochiq bo'lib, u takliflarni, rasmiy spetsifikatsiya matnini va yig'ilish yozuvlarini o'z ichiga oladi.

ECMAScript ning 6-nashri (ES6 deb tanilgan) dan oldin, spetsifikatsiyalar bir necha yilda bir marta nashr etilardi va odatda ularning asosiy versiya raqamlari bilan atalardi - ES3, ES5 va boshqalar. ES6 dan keyin, spetsifikatsiya nashr yili bilan nomlanadi - ES2017, ES2018 va boshqalar. ES6 ES2015 bilan sinonim. ESNext - bu yozish vaqtida keyingi versiya nima bo'lishiga ishora qiladigan dinamik nom. ESNext xususiyatlari to'g'riroq takliflar deb ataladi, chunki ta'rifga ko'ra, spetsifikatsiya hali yakunlanmagan.

Hozirgi qo'mita tomonidan tasdiqlangan ECMA-262 ning suratkopi PDF va HTML formatda Ecma International ning ECMA-262 til spetsifikatsiyasi sahifasida mavjud. ECMA-262 va ECMA-402 spetsifikatsiya muharrirlari tomonidan doimiy ravishda saqlanadi va yangilanadi; TC39 veb-sayti eng so'nggi ECMA-262 va ECMA-402 versiyalarini taqdim etadi.

Yangi til xususiyatlari, jumladan yangi sintaksislar va API larni joriy etish va mavjud xatti-harakatlarni qayta ko'rib chiqish, takliflar shaklida muhokama qilinadi. Har bir taklif 4 bosqichli jarayondan o'tadi va odatda JavaScript dvigatellari tomonidan 3 yoki 4-bosqichda amalga oshiriladi va shu tariqa ommaviy foydalanish uchun mavjud bo'ladi.

ECMAScript tarixi haqida ko'proq ma'lumot uchun Wikipedia ECMAScript yozuviga qarang.

## Xalqarolashtirish API si

ECMAScript Xalqarolashtirish API Spetsifikatsiyasi ECMAScript Til Spetsifikatsiyasiga qo'shimcha bo'lib, u ham Ecma TC39 tomonidan standartlashtirilgan. Xalqarolashtirish API JavaScript ilovalari uchun kollatsiya (satrlarni solishtirish), raqamlarni formatlash va sana-vaqtni formatlashni ta'minlaydi, bu ilovalar tilni tanlash va funksionallikni o'z ehtiyojlariga moslashtirishga imkon beradi. Dastlabki standart 2012 yil dekabr oyida tasdiqlangan; brauzerlarda amalga oshirish holati Intl ob'ekti hujjatlarida kuzatiladi. Xalqarolashtirish spetsifikatsiyasi hozirda ham har yili ratifikatsiya qilinadi va brauzerlar doimiy ravishda o'z amalga oshirishlarini yaxshilaydi.

## Bog'liq resurslar

ECMAScript Til Spetsifikatsiyasi va ECMAScript Xalqarolashtirish API Spetsifikatsiyasi va tegishli resurslardagi joriy ishtirokda qatnashish yoki kuzatishning turli usullari mavjud:

- ECMAScript Til Spetsifikatsiyasi repositoriyasi
- ECMAScript Xalqarolashtirish API Spetsifikatsiyasi repositoriyasi
- ECMAScript takliflari repositoriyasi
- ECMAScript muvofiqlik test to'plami repositoriyasi
- TC39 yig'ilish yozuvlari
- ECMAScript spetsifikatsiyasi munozarasi; joriy pochta ro'yxati
- ECMAScript spetsifikatsiyasi munozarasi; tarixiy pochta ro'yxati arxivlari (2021 yil mart oyigacha)

## DOM API lari

### WebIDL

WebIDL spetsifikatsiyasi DOM texnologiyalari va ECMAScript o'rtasida bog'lovchi vazifasini bajaradi.

### DOM ning asosi

Document Object Model (DOM) - bu HTML, XHTML va XML hujjatlaridagi ob'ektlarni ifodalash va ular bilan o'zaro aloqada bo'lish uchun platformalararo, tildan mustaqil konventsiya. DOM daraxtidagi ob'ektlar ob'ektlardagi metodlardan foydalangan holda murojaatlashilishi va boshqarilishi mumkin. Hozirgi kunda DOM asosiy spetsifikatsiyasi WHATWG tomonidan saqlanmoqda (W3C versiyasini almashtirgan). U HTML va XML hujjatlarini ob'ektlar sifatida abstrakt qiluvchi tildan mustaqil interfeyslarni belgilaydi, shuningdek bu abstraktsiyani boshqarish mexanizmlarini ham belgilaydi. Bunga quyidagilar kiradi: Node, Element, DocumentFragment, Document, DOMImplementation, Event, EventTarget va boshqalar.

ECMAScript nuqtai nazaridan, DOM spetsifikatsiyasida belgilangan ob'ektlar "host ob'ektlari" deb ataladi.

### HTML DOM

HTML, vebning belgilash tili, DOM nuqtai nazaridan aniqlanadi. DOM Core da belgilangan abstrakt tushunchalar ustiga qatlamli tarzda, HTML elementlarning ma'nosini ham belgilaydi. HTML DOM HTML elementlaridagi className xususiyati yoki Document.body kabi API larni o'z ichiga oladi.

HTML spetsifikatsiyasi hujjatlarga cheklovlarni ham belgilaydi; masalan, u tartiblangan ro'yxatni ifodalovchi `<ul>` elementining barcha bolalari `<li>` elementlari bo'lishini talab qiladi, chunki ular ro'yxat elementlarini ifodalaydi. Umuman olganda, u standartda belgilanmagan elementlar va atributlardan foydalanishni ham taqiqlaydi.

Document ob'ekti, Window ob'ekti va boshqa DOM elementlarini qidiryapsizmi? DOM hujjatlarini o'qing.

## Boshqa muhim API lar

- setTimeout() va setInterval() funksiyalari dastlab HTML Standartidagi Window interfeysida belgilangan.
- XMLHttpRequest asinxron HTTP so'rovlarini yuborish imkonini beradi.
- Fetch API tarmoq so'rovlari uchun qulayroq abstraktsiyani ta'minlaydi.
- CSS Object Model CSS qoidalarini ob'ektlar sifatida abstrakt qiladi.
- WebWorkers parallel hisoblash imkonini beradi.
- WebSockets past darajadagi ikki tomonlama aloqani ta'minlaydi.
- Canvas 2D Context `<canvas>` uchun rasm chizish API si.
- WebAssembly interfeysi JavaScript kodi va WebAssembly modullari o'rtasida aloqa uchun yordamchi vositalarni taqdim etadi.

Brauzerdan tashqari muhitlar (masalan, Node.js) ko'pincha DOM API lariga ega emas - chunki ular hujjat bilan o'zaro aloqada bo'lmaydi - lekin ular hali ham ko'plab veb API larni amalga oshiradi, masalan fetch() va setTimeout().

## JavaScript implementatsiyalari

Hozirgi veb-brauzerlarda qo'llaniladigan JavaScript dvigatellariga quyidagilar kiradi:

- Mozilla ning SpiderMonkey, Firefox, Servo va Flow da qo'llaniladi. Brauzerdan tashqari boshqa foydalanish MongoDB, CouchDB va boshqalarni o'z ichiga oladi. Bu Brendan Eich tomonidan Netscape da yaratilgan birinchi JavaScript dvigatel edi.
- Google ning V8, Chrome va Chromium asosidagi brauzerlar, masalan Opera, Edge va Brave da qo'llaniladi. Brauzerdan tashqari boshqa foydalanish Node.js, Deno, Electron va boshqalarni o'z ichiga oladi.
- Apple ning JavaScriptCore (SquirrelFish/Nitro nomi bilan ham tanilgan), Safari va boshqa WebKit asosidagi brauzerlarda qo'llaniladi. Brauzerdan tashqari boshqa foydalanish Bun ni o'z ichiga oladi.
- LibJS, Ladybird da qo'llaniladi.

Ilgargi brauzerlarda qo'llaniladigan ba'zi JavaScript dvigatellariga quyidagilar kiradi:

- Carakan, Opera Chromium asosidagi brauzerga aylanishidan oldin qo'llanilgan.
- Microsoft ning Chakra, Internet Explorer da qo'llanilgan (garchi u amalga oshiradigan til rasmiy ravishda savdo belgisi muammolarini oldini olish uchun "JScript" deb atalgan bo'lsa ham). Edge ning oldingi versiyalari Chromium asosidagi brauzerga aylanishidan oldin, chalkashtirib yuboradigan tarzda, yana Chakra deb ataladigan boshqa JavaScript dvigateli ishlatgan.

Brauzerdan tashqari maqsadlar uchun maxsus moslashtirilgan ba'zi JavaScript dvigatellariga quyidagilar kiradi:

- Engine262, JavaScript da yozilgan va asosan tilning mos yozuvlar implementatsiyasi sifatida mo'ljallangan.
- Meta ning Hermes, React Native uchun optimallashtirilgan.
- Mozilla ning Rhino, Java da yozilgan.
- Oracle ning GraalJS, Java da yozilgan va GraalVM ustiga qurilgan.
- Moddable XS, IoT/o'rnatilgan tizimlar uchun mo'ljallangan.
- QuickJS, kichik va engil bo'lishi uchun mo'ljallangan.

JavaScript dvigatellar dastur ishlab chiquvchilar JavaScript ni o'z dasturiy ta'minotlariga integratsiya qilish uchun foydalanishi mumkin bo'lgan ochiq API ni taqdim etadi. JavaScript uchun eng keng tarqalgan muhit veb-brauzerlardir. Veb-brauzerlar odatda DOM ni JavaScript ga aks ettirishdan mas'ul bo'lgan host ob'ektlarini yaratish uchun ochiq API dan foydalanadi.

JavaScript uchun yana bir keng tarqalgan qo'llanma (Veb) server tomonidagi skript tili sifatida. JavaScript veb-serveri HTTP so'rovi va javob ob'ektlarini ifodalovchi host ob'ektlarini taqdim etadi, keyinchalik ular veb-sahifalarni dinamik tarzda yaratish uchun JavaScript dasturi tomonidan boshqarilishi mumkin. Node.js buning mashhur namunasi.

## Shelllar

JavaScript shell veb-sahifani qayta yuklashga hojat qolmasdan JavaScript kodi parçalarini tezda sinash imkonini beradi. Ular kodni ishlab chiqish va nosozliklarni tuzatish uchun juda foydali.

### Mustaqil JavaScript shellari

Quyidagi JavaScript shellari Perl yoki Python kabi mustaqil muhitlardir.

### Brauzer asosidagi JavaScript shellari

Quyidagi JavaScript shellari brauzerning JavaScript dvigatel orqali kodni ishga tushiradi.

- Firefox da ko'p qatorli tahrirlashni qo'llab-quvvatlaydigan o'rnatilgan JavaScript konsoli mavjud.
- Babel REPL - Kelajakdagi JavaScript ni tajriba qilish uchun brauzer asosidagi REPL.
- TypeScript playground - Yangi JavaScript xususiyatlarini (tsc kompilyatori orqali) va TypeScript sintaksisini tajriba qilish uchun brauzer asosidagi o'yin maydoni.

## Vositalar va resurslar

JavaScript kodingizni yozish va nosozliklarni tuzatishda foydali vositalar.

- **Firefox Developer Tools** - Web Console, JavaScript Profiler, Debugger va boshqalar.
- **Learn JavaScript** - Istiqbolli veb-ishlab chiquvchilar uchun ajoyib resurs — JavaScript ni interaktiv muhitda o'rganing, qisqa darslar va interaktiv testlar bilan, avtomatlashtirilgan baholash tomonidan boshqariladi. Birinchi 40 dars bepul va to'liq kurs kichik bir martalik to'lov uchun mavjud.
- **TogetherJS** - Hamkorlik osonlashtirildi. TogetherJS ni saytingizga qo'shish orqali, foydalanuvchilaringiz veb-saytda real vaqtda bir-birlariga yordam berishlari mumkin!
- **Stack Overflow** - "JavaScript" bilan belgilangan Stack Overflow savollari.
- **JSFiddle** - JavaScript, CSS va HTML ni tahrirlang va jonli natijalarni oling. Tashqi resurslardan foydalaning va jamoangiz bilan onlayn hamkorlik qiling.
- **Plunker** - Plunker veb-ishlab chiqish g'oyalaringizni yaratish, hamkorlik qilish va baham ko'rish uchun onlayn hamjamiyat. JavaScript, CSS va HTML fayllaringizni tahrirlang va jonli natijalar va fayl tuzilmasini oling.
- **JS Bin** - JS Bin ochiq manbali hamkorlikdagi veb-ishlab chiqish nosozliklarni tuzatish vositasi.
- **CodePen** - CodePen jonli natija o'yin maydoni sifatida ishlatiladigan yana bir hamkorlikdagi veb-ishlab chiqish vositasi.
- **StackBlitz** - StackBlitz React, Angular va boshqalardan foydalangan holda to'liq stek ilovalarni joylashtirishi va joylashtirishi mumkin bo'lgan yana bir onlayn o'yin maydoni/nosozliklarni tuzatish vositasi.
- **RunJS** - RunJS jonli natijalar va Node va Brauzer API lariga kirishni ta'minlovchi ish stoli o'yin maydoni/scratchpad vositasi.