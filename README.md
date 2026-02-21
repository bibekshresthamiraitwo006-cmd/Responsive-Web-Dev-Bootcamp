# Responsive-Web-Dev-Bootcamp

# CSS Units

## `px` — Pixel (Fixed)
Screen resize garey pani change hudaina. Jasto lekhyo testai raunxa.
```css
font-size: 16px; /* always 16px */
```

---

## `%` — Percentage (Parent dependent)
Parent ko size heri afno size set garxa. Parent thulo = child thulo.
```css
.parent { width: 500px; }
.child  { width: 50%; }  /* = 250px */
```

---

## `vw` — Viewport Width (Screen width dependent)
Browser window ko width heri change hunxa. Screen resize garda automatically adjust hunxa.
```css
width: 50vw; /* = half of screen width */
```

---

## `vh` — Viewport Height (Screen height dependent)
vw jastai, tara height heri hunxa. Hero sections banaune bela sabai bhandha useful!
```css
height: 100vh; /* = full screen height */
```

---

## `em` — Parent Font Size dependent 
Parent ko font-size bata calculate hunxa. Nested garyo bhane **multiply hudai janxa** — yo nai trap ho!
```css
.parent     { font-size: 20px; }
.child      { font-size: 1.5em; } /* 20 × 1.5 = 30px */
.grandchild { font-size: 1.5em; } /* 30 × 1.5 = 45px */
```

---

## `rem` — Root Font Size dependent 
Always HTML root ko font-size heri hunxa = **16px by default**. Em jastai trap hudaina, consistent raunxa.
```css
h1 { font-size: 2rem; } /* 16 × 2 = 32px, always */
p  { font-size: 1rem; } /* 16 × 1 = 16px, always */
```

---

| Unit | Based On | Safe? |
|------|----------|-------|
| `px` | Fixed |
| `%` | Parent size |
| `vw` | Screen width |
| `vh` | Screen height |
| `em` | Parent font-size | ⚠️ Trap! |
| `rem` | Root = 16px |


# CSS Flexbox

Flexbox = ek powerful layout tool ho jole elements lai row/column ma easily arrange garna dinxa. Pehile parent ma `display: flex` lekhnu parxa, tespachi baaki properties kaam garxa.

```css
.parent { display: flex; }
```

---

## `flex-direction` — Kata align garne?
Items kun direction ma janxa bhanne set garxa.

```css
flex-direction: row;            /* → left to right (default) */
flex-direction: row-reverse;    /* ← right to left */
flex-direction: column;         /* ↓ top to bottom */
flex-direction: column-reverse; /* ↑ bottom to top */
```

---

## `justify-content` — Main Axis Alignment
`flex-direction` jun direction ma xa, tesko axis ma items lai align garxa (horizontal by default).

```css
justify-content: flex-start;    /* items left ma (default) */
justify-content: flex-end;      /* items right ma */
justify-content: center;        /* items center ma */
justify-content: space-between; /* items bich equal gap, edges ma gap xaina */
justify-content: space-around;  /* sabai items ko wari pari equal gap */
justify-content: space-evenly;  /* sabai gap exactly equal */
```

---

## `align-items` — Cross Axis Alignment (Single Line)
Main axis ko opposite direction ma align garxa (vertical by default).

```css
align-items: stretch;     /* items purai height samma stretch hunxa (default) */
align-items: flex-start;  /* items top ma */
align-items: flex-end;    /* items bottom ma */
align-items: center;      /* items vertically center ma */
align-items: baseline;    /* items ko text baseline align hunxa */
```

---

## `flex-wrap` — Items wrap garne ki nai?
By default sabai items ek line ma fit huna khojxan. Wrap lekhyo bhane next line ma janxa.

```css
flex-wrap: nowrap;        /* sabai ek line ma (default) */
flex-wrap: wrap;          /* items next line ma janxa */
flex-wrap: wrap-reverse;  /* next line ma janxa tara reverse direction ma */
```

---

## `gap` — Items Bich Ko Gap
Items bich space dina, margin nalagayi directly gap dina milxa.

```css
gap: 10px;        /* sabai direction ma 10px gap */
gap: 10px 20px;   /* row gap 10px, column gap 20px */
```

---

## `flex-grow` — Baaeki Space Line
Parent ma baaki space xa bhane child le tyo space lina milxa. Default 0 hunxa (space lidaina).

```css
.child-a { flex-grow: 1; } /* baaki space ko 1 part lina */
.child-b { flex-grow: 2; } /* baaki space ko 2 part lina (child-a bhandha 2x thulo) */
```

---

## `flex-shrink` — Sano Hune Permission
Space kam bhayo bhane item kati sano hune bhanne set garxa. Default 1 hunxa (shrink hunxa).

```css
.child { flex-shrink: 1; } /* space kam bhayo bhane shrink hunxa (default) */
.child { flex-shrink: 0; } /* space kam bhaye pani shrink hudaina */
```

---

## `flex-basis` — Default Size
Item ko starting size set garxa (width jastai, tara flex bela use garxa).

```css
.child { flex-basis: 200px; } /* item suru ma 200px hunxa */
.child { flex-basis: auto; }  /* content ko size heri hunxa (default) */
```

---

## `flex` — Shorthand (grow + shrink + basis)
Tintai ek saath lekhna milxa.

```css
.child { flex: 1; }          /* grow:1, shrink:1, basis:0 */
.child { flex: 1 0 200px; }  /* grow:1, shrink:0, basis:200px */
```

---

## `order` — Items Ko Order Change Garne
HTML ma jुन order xa, tesलाई CSS bata change garna milxa.

```css
.child-a { order: 2; } /* yo pachhi dekhinxa */
.child-b { order: 1; } /* yo pehile dekhinxa */
```

---

## Quick Cheatsheet

| Property | Kaam |
|----------|------|
| `flex-direction` | Row/Column set garne |
| `justify-content` | Main axis align |
| `align-items` | Cross axis align |
| `flex-wrap` | Items wrap garne |
| `gap` | Items bich space |
| `flex-grow` | Baaki space lina |
| `flex-shrink` | Sano hune permission |
| `flex-basis` | Starting size |
| `flex` | grow+shrink+basis shorthand |
| `order` | Items ko order change |

---

- `display: flex` = *"Flex suru gara, timro children lai flexible banau!"*

- `flex-direction: row` = *"Items left to right janxa!"* (default)
- `flex-direction: column` = *"Items top to bottom janxa!"*

- `justify-content: flex-start` = *"Sabai items left ma basxa!"* (default)
- `justify-content: flex-end` = *"Sabai items right ma basxa!"*
- `justify-content: center` = *"Sabai items center ma basxa!"*
- `justify-content: space-between` = *"Items haru bich gap hunxa, edges ma hudaina!"*
- `justify-content: space-around` = *"Timro sabai items ko waripaari ma equally gap hunxa!"*
- `justify-content: space-evenly` = *"Timro sabai gap exactly equal barabar ma hunxa!"*

- `align-items: stretch` = *"Timro items haru purai height samma stretch hunxa!"* (default)
- `align-items: flex-start` = *"Timro items sabai top ma basxa!"*
- `align-items: flex-end` = *"Timro items sabai bottom ma basxa!"*
- `align-items: center` = *"Timro items sabai vertically center ma basxa!"*

- `flex-wrap: nowrap` = *"Items haru Ek line ma nai basxa, squeeze bhaye pani!"* (default)
- `flex-wrap: wrap` = *"Space xaina bhane next line ma aru Items haru janxa!"*
- `flex-wrap: wrap-reverse` = *"Next line ma janxa reverse way ma!"*

- `flex-grow: 0` = *"Extra space malai chaidaina jati xa ma tesmai thik xu!"* (default)
- `flex-grow: 1` = *"jati space baki xa teti space sabai maile linxu!"*

- `flex-shrink: 1` = *"Space kam bhayo bhane ma sano hunxu!"* (default)
- `flex-shrink: 0` = *"Mero size touch nagara, arulai sano gara!"*

- `flex-basis: auto` = *"Content jati xa, tehi mero starting size hunxa!"* (default)
- `flex-basis: 200px` = *"Mero starting size 200px ho!"*

- `flex: 1` = *"grow:1 shrink:1 basis:0 — flex:1 vaneko tin otai ekai saath kam garnu ho !"*

- `order: 0` = *"HTML ma jun order xa tehi!"* (default)
- `order: 1` = *"Malai pachhi rakha!"*
- `order: -1` = *"Malai sabai bhandha pehile rakha!"*

- `gap: 10px` = *"Timro sabai items bich 10px gap dinxu!"*

# CSS Grid

- `display: grid` = *"Grid suru garyo vane, children lai 2D ma arrange garna sakinxa!"*

- `grid-template-columns: 200px 200px 200px` = *"3 fixed columns, sabai 200px ma hunxa!"*
- `grid-template-columns: 1fr 2fr 1fr` = *"Baaki space fraction ma badhxa, middle 2x thulo!"*
- `grid-template-columns: repeat(3, 1fr)` = *"Same value baar baar lekhnu pardaina!"*

- `grid-template-rows: 100px 200px` = *"Pahilo row 100px, doshro row 200px!"*

- `gap: 10px` = *"Sabai items bich 10px space de!"*
- `column-gap: 30px` = *"Sirf columns bich thulo gap!"*
- `row-gap: 10px` = *"Sirf rows bich sano gap!"*

- `grid-column: span 2` = *"Malai 2 columns deu!"*
- `grid-row: span 2` = *"Malai 2 rows deu!"*
- `grid-column: 1 / 3` = *"Line 1 bata Line 3 samma jana milxa!"*

- `justify-items: center` = *"Harek cell bhitra item horizontally center garna milxa!"*
- `align-items: center` = *"Harek cell bhitra item vertically center garna milxa!"*
- `justify-content: center` = *"Purai grid nai parent bhitra center ma rakhna milxa!"*

---

# Media Queries & Tailwind CSS — Responsive Notes

---

## Media Queries

Screen size heri CSS change garne technique ho. Desktop, tablet, mobile — sabai ko lagi alag CSS lekhna milxa!

**Syntax:**
```css
@media (max-width: 640px) {
  /* yo CSS sirf 640px bhandha sano screen ma lagxa */
}
```

**max-width vs min-width:**
```css
/* max-width = yo bhandha SANO screen ma */
@media (max-width: 640px) { ... }

/* min-width = yo bhandha THULO screen ma */
@media (min-width: 640px) { ... }
```

**Common Breakpoints:**
```css
@media (max-width: 1280px) { /* Large laptop */ }
@media (max-width: 1024px) { /* Tablet landscape */ }
@media (max-width: 768px)  { /* Tablet portrait */ }
@media (max-width: 640px)  { /* Mobile */ }
@media (max-width: 480px)  { /* Small mobile */ }
```

**Real Example:**
```css
/* Desktop */
.gallery { grid-template-columns: repeat(4, 1fr); }

/* Tablet */
@media (max-width: 1024px) {
  .gallery { grid-template-columns: repeat(3, 1fr); }
}

/* Mobile */
@media (max-width: 640px) {
  .gallery { grid-template-columns: repeat(2, 1fr); }
  .nav-links { display: none; }
  .hamburger { display: flex; }
}
```

**Simply bhanyo bhane:**
- `max-width` = *"Yo screen bhandha sano bhayo bhane yo CSS laga!"*
- `min-width` = *"Yo screen bhandha thulo bhayo bhane yo CSS laga!"*

---

## TailwindCSS Responsive

Tailwind ma media query lekhnu pardaina — class name agadi **breakpoint prefix** matra lagauxa!

**Tailwind Breakpoints:**
```
default  →  Mobile (kei prefix xaina)
sm:      →  640px maathi
md:      →  768px maathi
lg:      →  1024px maathi
xl:      →  1280px maathi
2xl:     →  1536px maathi
```

**Syntax:**
```html
<div class="text-sm md:text-lg lg:text-2xl">Hello</div>
```
- Mobile → `text-sm`
- 768px maathi → `text-lg`
- 1024px maathi → `text-2xl`

**Tailwind = Mobile First!**

Tailwind ma default = mobile. Maathi maathi breakpoint add garxa:
```html
<!-- Normal CSS = Desktop First (max-width use garxa) -->
<!-- Tailwind   = Mobile First (min-width use garxa) -->

<div class="grid-cols-1 sm:grid-cols-2 lg:grid-cols-4">
```
- Mobile → 1 column
- 640px maathi → 2 columns
- 1024px maathi → 4 columns

**Real Examples:**

Navbar responsive:
```html
<nav class="flex justify-between items-center px-8 h-16 bg-gray-900">

  <a class="text-white font-bold">eli19</a>

  <!-- Mobile ma hidden, Desktop ma flex -->
  <ul class="hidden md:flex gap-4 list-none">
    <li><a class="text-gray-400 hover:text-white">Home</a></li>
    <li><a class="text-gray-400 hover:text-white">About</a></li>
  </ul>

  <!-- Mobile ma dekhauxa, Desktop ma hidden -->
  <button class="md:hidden text-white">☰</button>

</nav>
```

Gallery responsive:
```html
<div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 p-8">
  <div class="bg-white rounded-xl shadow-md overflow-hidden">...</div>
  <div class="bg-white rounded-xl shadow-md overflow-hidden">...</div>
  <div class="bg-white rounded-xl shadow-md overflow-hidden">...</div>
</div>
```

---

## Media Query vs Tailwind — Side by Side

```css
/* ===== Normal CSS ===== */
.box { font-size: 14px; }

@media (min-width: 768px) {
  .box { font-size: 18px; }
}
@media (min-width: 1024px) {
  .box { font-size: 24px; }
}
```

```html
<!-- ===== Tailwind ===== -->
<p class="text-sm md:text-lg lg:text-2xl">Hello</p>
```

Same result — Tailwind = **3 lines bata 1 line!**

---

**Simply bhanyo bhane:**
- Media Query = *"Screen size heri CSS manually lekhne - aafai control!"*
- Tailwind Responsive = *"`md: lg:` prefix lagau — media query lekhnu pardaina!"*
- Tailwind = **Mobile First** — *"Mobile bata suru gara, thulo screen ma add gara!"*

<!-- ************ END ************ -->