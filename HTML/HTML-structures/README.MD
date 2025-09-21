# Har bir ishni qilishdan oldin uni rejalashtirib  olamiz va biz uchun eng yaxshisini qidiramiz.

dasturlashda ham shunday. qaysi bir yoldan yursam va qaysi strukturadan foydalansam to'g'ri boladi degan savollar har doim yangi loyiha boshlashdan oldin miyyada aylanadi. Bu bizga muammoni 50% ni hal qilishga olib keladi va keyinchalik biz muammoga uchramasligimizga olib keladi.


htmlni nechanchi versiyasi qaysi kutubxonalarni ishlatish uni qanday ishlatish va uni tezligini oshirib foydalanuvchilarga qulaylik keltirishni o'ylaydigan dasturchi bolish ozgina mehnat talab qiladi.

keling endi biz birin ketib korib boramiz.

bizdagi butun web browser sahifasidagi oynada koringan qisim yoki korinmagan qisimlar bular elementlar hisoblanadi.

va u elementlarni biz belgilar bilan ifodalashimiz kerak 
```<tagnomi attribute_joyi> content </tagnomi> ```

korayotgan bo'lsangiz bu htmldagi tag yozilish strukturasi.

Bizdagi tag nomi uchun bir qancha taglar mavjud va ularni har birini yozishimizdan asosiy maqsad bor. Bu haqda oldingi sahifada javob berganman. Eslatma uchun screenReader. 

taglar bolimini o'rganish uchun [Havola]()


## attribute
bolsa bizda har doim uy ishlarida bizni ishimizni yengillashtirib beradigan qoshimcha toollar mavjud. masalan ovqatni aralashtirish uchun kapkir kerak bolganidek bizni ham taglardan to'liq foydalanish uchun attributelar kerak bo'ladi.

bular haqida men keyingi sahifalarda birin ketin javob berib boraman.


## endi biz siz bilan html structure bilan tanishadigan bo'lsak.

har doim bizga kerak boladigan qism bu eng birinchi qatorda yozib qo'yiladigan tag hisoblanib u bizga browser bizni codelarimizni qaysi tilda o'qishini yani qaysi belgilash tilida o'qishini korsatib beradi.

```<DOCTYPE html>```

yani bu yerda bizni codelarimizni browser screenReader qanday o'qib oynaga chiqarishini ko'rib oynaga qanday chiqarishni belgilaydi.

va bizda umumiy sahifani o'rab  turish uchun kerak boladigan sematik tag mavjud va bu umumiy parent element hisoblanadi.

```<html></html>```

va butun sahifa shuni orasiga yozilishi kerak.
biz bundan tashqariga code yozsak ham oynaga korinadi.


```<!DOCTYPE html>
<html lang="en">
<head>
 <style>
  .hello{
   color: red;
  }
  
 </style>
</head>
</html>

<div class="hello">
 salom
</div>
```

bu yerda korib turganingizday htmldan tashqarida yangi tag elon qildim va bu hato hisoblanadi. 

1.sababi bizni doctype bizda html nechanchi versiyadaligini va html esa uni aniqlab korsatib ketadi. 
2.aniq siz hohlaganday o'qimasligi ham mumkin.
3.bizni codelarimiz ketma ketligini oqilishini va qulayligini buzadi.
4.seo ni tushirishi ham mumkin.
va bir qancha muammolarga olib keladi.

demak biz har doim html 5-chi versiyada yozishimiz kerak sababi u hozirgi kunda eng yaxshi ishlayotgan versiya hisoblanadi.

bu dokumnetatsiya 2025-yil sentabr oyida yozildi.
