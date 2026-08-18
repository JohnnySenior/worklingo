# WorkLingo — 성형기 #2

Zavoddagi mashinaga yopishtirilgan QR kod → telefonda ochiladigan ko'p tilli ish
instruksiyasi. Server yo'q, baza yo'q. Faqat oddiy fayllar + GitHub Pages (bepul).

**Sayt:** https://johnnysenior.github.io/worklingo/m/pellet-mill-2/
**QR kod:** `qr/pellet-mill-2.svg`

## Fayllar qayerda

```
worklingo/
├── index.html                  ← mashinalar ro'yxati
├── m/pellet-mill-2/
│   ├── index.html              ← 성형기 #2 vazifalar ro'yxati
│   └── start-check/
│       ├── index.html          ← SOP: shu faylni tahrirlaysan
│       └── photos/             ← rasmlar shu yerga
└── qr/pellet-mill-2.svg
```

**Eng muhim qoida:** QR kod `m/pellet-mill-2/` manziliga bog'langan.
Bu manzil hech qachon o'zgarmaydi. Yangi vazifa qo'shsang ham QR o'sha-o'sha
qoladi — qayta chop etish shart emas.

---

## 1. Matnni qanday o'zgartiraman

Faylni ochasan:

```
m/pellet-mill-2/start-check/index.html
```

Ichida shunday blok bor — **faqat shu blokni** o'zgartirasan:

```js
const SOP = {
  machine: "성형기 #2",
  ...
};
```

Bloki qayerda tugaydi: `};` qatorida. Undan pastda shunday yozuv turadi:

```js
/* ── pastdan boshlab kodga tegma ────────────── */
```

**Shu qatordan pastdagi hech narsaga tegmaysan.** U yerda sahifani ishlatadigan
kod turadi. Buzilsa sahifa ochilmay qoladi.

Matnni o'zgartirganda qo'shtirnoq ichidagini almashtirasan:

```js
uz: "Podshipnik grease'ini tekshir",
```

↓

```js
uz: "Podshipnik moyini tekshir",
```

Qo'shtirnoq va oxiridagi vergulni **o'chirmaysan**.

> **Ehtiyot bo'l:** o'zbekchada apostrof bor (`bo'lmasa`). U oddiy apostrof `'`.
> Agar matn ichiga qo'shtirnoq `"` yozish kerak bo'lsa — oldiga `\` qo'y:
> `uz: "\"Stop\" tugmasini bos",`

---

## 2. Yangi qadam qanday qo'shaman

`steps: [` ichida har bir qadam `{ ... }` bo'lib turadi. Oxirgi qadamdan keyin
vergul `,` qo'yib, pastdagi blokni **butunlay copy-paste** qilasan:

```js
    {
      ko: "체인 장력 확인",
      uz: "Zanjir tarangligini tekshir",
      vi: "Kiểm tra độ căng của dây curoa",
      img: "photos/photo-05.jpg",
      ring: { x: "50%", y: "50%" },
      note: {
        ko: "느슨하면 반장에게 알린다",
        uz: "Bo'shashgan bo'lsa — ustaga ayt",
        vi: "Nếu lỏng thì báo tổ trưởng"
      }
    }
```

Nimalarni o'zgartirasan:

| Nima | Ma'nosi |
|---|---|
| `ko:` | koreyscha matn |
| `uz:` | o'zbekcha matn |
| `vi:` | vetnamcha matn |
| `img:` | rasm nomi — `photos/` bilan boshlanadi |
| `ring:` | qizil doira qayerda tursin (3-bo'limga qara) |
| `note:` yoki `stop:` | pastdagi izoh (4-bo'limga qara) |

Qadam raqamlari (01, 02, 03…) **o'zi chiqadi** — qo'lda yozish shart emas.

Rasm kerak bo'lmasa `img:` va `ring:` qatorlarini olib tashla — sahifa buzilmaydi.

### note va stop farqi

**`note:`** — oddiy izoh. Kulrang blok, chap tomonida qora chiziq.
Ma'nosi: "shuni ham bilib qo'y".

```js
      note: {
        ko: "부족하면 주입한다",
        uz: "Yetarli bo'lmasa — grease quy",
        vi: "Nếu thiếu thì bơm thêm"
      }
```

**`stop:`** — qizil blok, ustida `STOP · 정지` yozuvi.
Ma'nosi: "**o'zing qilma, to'xta**".

```js
      stop: {
        ko: "풀려 있으면 직접 조이지 말고 반장에게 알린다",
        uz: "Bo'shashgan bo'lsa — o'zing tortma, ustaga ayt",
        vi: "Nếu lỏng, không tự siết — báo tổ trưởng"
      }
```

Bittasini yozasan — `note` yoki `stop`. Ikkitasi birga yozilsa, faqat `stop`
ko'rinadi.

---

## 3. Qizil doirani qanday suraman

```js
ring: { x: "50%", y: "50%" }
```

- `x` — **chapdan** qancha foiz
- `y` — **tepadan** qancha foiz

Doira markazi shu nuqtaga tushadi. Rasmning o'lchami muhim emas, faqat foiz.

Misollar:

```js
ring: { x: "50%", y: "50%" }   // aynan o'rtada
ring: { x: "20%", y: "30%" }   // chap tepada
ring: { x: "80%", y: "75%" }   // o'ng pastda
ring: { x: "50%", y: "15%" }   // yuqori o'rtada
```

Eslab qol: `x` ni **oshirsang** doira **o'ngga** suriladi.
`y` ni **oshirsang** doira **pastga** suriladi.

To'g'ri joyni topish: sonni o'zgartir → faylni saqla → brauzerda sahifani
yangila (F5). Ko'rinmaguncha 2-3 marta urin.

---

## 4. Rasmni qanday almashtiraman

Rasmni shu papkaga tashlaysan:

```
m/pellet-mill-2/start-check/photos/
```

Nomi **aynan** `photo-01.jpg`, `photo-02.jpg` … bo'lishi kerak.
Yangi rasm o'sha nom bilan tashlansa, eskisining ustiga yozadi — kodda hech
narsa o'zgartirish shart emas.

### Rasmni siqish — buni tashlab ketma

Telefondan olingan rasm 3–8 MB bo'ladi. Zavodda LTE zaif — sahifa 20 soniya
ochiladi. Har bir rasmni siqish kerak:

- kengligi **1200px**
- JPEG sifat **80**
- natija: har biri **100 KB atrofida** (eng ko'pi 200 KB)

> **Nega 100 KB:** sahifaning o'zi 15 KB, shriftlar ~80 KB. Butun sahifa
> 500 KB dan oshmasligi kerak, ya'ni 4 rasmga jami ~400 KB joy qoladi.
> Sifat 80 da 1200px rasm odatda 80–120 KB bo'ladi — bu yetarli.

Mac'da (hech narsa o'rnatish shart emas):

```bash
sips -Z 1200 -s format jpeg -s formatOptions 80 photo-01.jpg --out photo-01.jpg
```

ImageMagick bo'lsa:

```bash
magick photo-01.jpg -resize 1200x -quality 80 photo-01.jpg
```

Hajmini tekshirish:

```bash
ls -lh m/pellet-mill-2/start-check/photos/
```

Rasm hali yo'q bo'lsa sahifa buzilmaydi — o'rniga bo'sh ramka chiqadi.

---

## 5. Yangi vazifa (yangi SOP) qanday qo'shaman

Masalan "filtrni almashtirish" qo'shmoqchisan.

**1-qadam.** `start-check` papkasidan nusxa olib yangi nom ber:

```bash
cp -r m/pellet-mill-2/start-check m/pellet-mill-2/filter-change
```

**2-qadam.** `m/pellet-mill-2/filter-change/index.html` ni ochib, `const SOP = {`
blokidagi matnlarni yangi vazifaga moslab yoz. Kerak bo'lmagan qadamlarni
o'chir. `photos/` ichidagi eski rasmlarni ham almashtir.

**3-qadam.** `m/pellet-mill-2/index.html` ni ochasan. Ichida shunday izoh bor:

```
YANGI VAZIFA QO'SHISH
```

O'sha izoh ichidagi blokni copy-paste qilib, izohdan **tashqariga** chiqarasan
va 3 joyni o'zgartirasan: raqam (`02`), havola (`filter-change/`), ikkita matn.

**4-qadam.** Tamom. **QR kodga tegmaysan** — u mashina sahifasiga bog'langan,
yangi vazifa o'sha ro'yxatda o'zi paydo bo'ladi. Qayta chop etish shart emas.

---

## 6. O'zgarishni internetga qanday chiqaraman

Uch buyruq. Papka ichida turib:

```bash
git add -A
git commit -m "matn o'zgardi"
git push
```

1–2 daqiqadan keyin sayt yangilanadi. Telefonda ko'rmasang — sahifani yangila
yoki brauzer keshini tozala.

`commit -m "..."` ichiga nima qilganini o'zbekcha yozsang bo'ladi — bu faqat
o'zing uchun eslatma.

---

## Yangi mashina qo'shish

`m/` ichida yangi papka (masalan `m/hammer-mill-1/`), ichiga `index.html`,
keyin root `index.html` ga qator qo'shasan — u yerda ham
`YANGI MASHINA QO'SHISH` izohi turadi.

Har bir yangi mashinaga **o'z QR kodi** kerak — manzili boshqa bo'ladi.

---

## QR kod

`qr/pellet-mill-2.svg` — SVG, ya'ni qancha kattalashtirsang ham sifat yo'qolmaydi.
A4 ga chop etganda QR 8 cm kvadrat bo'ladi.

Ichida error correction **H** darajasi ishlatilgan — chang yoki moy bilan
qisman ifloslansa ham o'qiladi.

**Laminatsiya qilib yopishtir.** Pellet zavodida chang va moy bor — oddiy
qog'oz 2 haftada o'qilmay qoladi.

Ostidagi yozuvni o'zgartirish kerak bo'lsa: SVG ni matn muharririda ochib,
`<text>` qatorlaridagi so'zlarni almashtirasan.
