# CSS Transitions --- Very Advanced Guide

CSS **transition** --- UI elementlarning bir holatdan boshqasiga silliq
o'tishini ta'minlaydigan eng kuchli frontend mexanizmlaridan biridir.
Advanced darajada transitionlar: micro-interactionlar, UI/UX flow,
component-based arxitektura va performance optimallashtirishning asosiy
qismidir.

## 🚀 Nima uchun Transitions kerak?

-   UI o'zgarishlari "natural" seziladi\
-   Micro-interaction UXni chuqur yaxshilaydi\
-   JavaScript'siz professional animatsiyalar\
-   Skeleton loader, tooltip, dropdown, modal, nav menu kabi
    componentlarda ishlaydi\
-   Performance jihatdan tejamkor --- 60FPS ga yaqin natija

## 📦 Syntax (To'liq shakli)

``` css
transition: <property> <duration> <timing-function> <delay>;
```

## 🎛 Transition parametrlar

  Parametr                       Tavsif
  ------------------------------ -------------------------------------
  `transition-property`          Qaysi xususiyat animatsiya qilinadi
  `transition-duration`          Animatsiya davomiyligi
  `transition-timing-function`   Harakatning tezlik egrisi
  `transition-delay`             Kechikish

## ⏳ Timing Function --- Advanced

### Standartlar:

-   ease
-   ease-in
-   ease-out
-   ease-in-out
-   linear

### Custom cubic-bezier (Ultra Advanced)

``` css
transition-timing-function: cubic-bezier(x1, y1, x2, y2);
```

## 🎨 Transform bilan Transition (60FPS)

``` css
.card {
  transform: translateZ(0);
  transition: transform .35s cubic-bezier(.3,1,.3,1);
}
.card:hover {
  transform: translateY(-8px) scale(1.02);
}
```

## 🔥 Multiple property transition

``` css
.button {
  transition:
    background-color .2s ease-in-out,
    box-shadow .3s cubic-bezier(.25,.8,.25,1),
    transform .25s ease;
}
.button:hover {
  background-color: #000;
  box-shadow: 0 10px 25px rgba(0,0,0,.15);
  transform: translateY(-4px);
}
```

## 🧩 Advanced Toggle Example (Bounce effect)

``` css
.toggle {
  width: 50px;
  height: 26px;
  background: #ccc;
  border-radius: 20px;
  position: relative;
  cursor: pointer;
  transition: background .3s ease;
}
.toggle::after {
  content: "";
  width: 22px;
  height: 22px;
  background: white;
  border-radius: 50%;
  position: absolute;
  left: 2px;
  top: 2px;
  transition: transform .25s cubic-bezier(.34,1.56,.64,1);
}
.toggle.active {
  background: #4ade80;
}
.toggle.active::after {
  transform: translateX(24px);
}
```

## 🌗 Transition + Visibility (Professional Pattern)

``` css
.dropdown {
  opacity: 0;
  transform: translateY(10px);
  pointer-events: none;
  transition:
      opacity .25s ease,
      transform .25s ease;
}
.dropdown.open {
  opacity: 1;
  transform: translateY(0);
  pointer-events: auto;
}
```

## 🎉 Modal Example

``` css
.modal {
  opacity: 0;
  transform: scale(.9) translateY(20px);
  transition:
    opacity .25s ease,
    transform .35s cubic-bezier(.25,.8,.25,1);
  pointer-events: none;
}
.modal.open {
  opacity: 1;
  transform: scale(1) translateY(0);
  pointer-events: auto;
}
```
