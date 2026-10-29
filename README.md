# Mushtariy Premium Restaurant — landing sahifa

Sayt: https://abdul0018.github.io/Mushtari-landing/

Statik sayt (HTML + CSS + JS, kutubxonasiz). `main` branchga har bir push `.github/workflows/pages.yml` orqali
GitHub Pages'ga avtomatik joylanadi. Lokal ko'rish:

```bash
python3 -m http.server 8080   # http://localhost:8080
```

## Buyurtma qanday ishlaydi

Server kerak emas. Mijoz savatchani to'ldiradi, ism, telefon va manzilni yozadi, «Telegram'da yuborish»ni bosadi —
menejerning Telegram chati tayyor xabar bilan ochiladi (`https://t.me/<username>?text=...`), mijoz faqat «Yuborish»ni bosadi.
Stol band qilish ham shunday ishlaydi. Telegram bo'lmasa — sahifadagi telefon raqami.

Keyingi bosqich (TZ, 7-bo'lim): buyurtma bot orqali menejerga to'g'ridan-to'g'ri tushishi va status tugmalari — buning uchun
[Fast-Delivery-Bot](https://github.com/abdul0018/Fast-Delivery-Bot) backendiga `POST /api/web-orders` qo'shiladi.
Texnik topshiriq: o'sha repodagi `docs/TZ-Mushtariy-Landing.pdf`.

## Ishga tushirishdan oldin almashtiriladi

`app.js` boshidagi `CONFIG`:

| Maydon | Hozir (namuna) | Nima yoziladi |
|---|---|---|
| `managerTelegram` | `mushtariy_manager` | Menejerning haqiqiy Telegram username'i (@ belgisisiz) |
| `phone`, `phoneText` | `+998 00 000 00 00` | Restoran telefoni |
| `address`, `mapUrl`, `coords` | Buxoro, Namozgoh 1-tor ko'chasi (Yandex Xarita) | Tayyor — Yandex'dagi restoran sahifasidan olingan |
| `hours` | `10:00 – 23:00` | Haqiqiy ish vaqti |

Shuningdek:
- **Menyu** (`DISHES` / `CATEGORIES` — `app.js`): taomlar, tavsiflar va narxlar namuna.
- **Sharhlar** (`index.html`, «Mehmonlarimiz» bo'limi): namuna, haqiqiy sharhlar bilan almashtiriladi.
- **Va'dalar** (afzalliklar qatori, «Shinam zal», banket bo'limi): restoran bajara oladiganini qoldiring.

## Rasmlar va ularning manbasi

| Fayl | Manba |
|---|---|
| `assets/img/logo-badge*.png` | Restoranning Instagram profilidagi logotip (skrinshotdan kesilgan). Asl vektor fayl bilan almashtirish tavsiya etiladi |
| `assets/img/facade.jpg` | Restoran binosi — Instagram'dagi videodan kadr (odamlar kesib tashlangan) |
| `assets/img/og.jpg` | Ulashish rasmi: logotip + `hero-osh.jpg` |
| taom va zal suratlari | **Pexels** fotosuratlari ([Pexels litsenziyasi](https://www.pexels.com/license/): bepul, tijoriy foydalanish mumkin, muallifni ko'rsatish shart emas). Restoranning o'z taomlari emas — o'z fotosuratlari tayyor bo'lganda **shu nomlarda** almashtiriladi |

| Fayl | Pexels |
|---|---|
| `hero-osh.jpg` | https://www.pexels.com/photo/10541694/ |
| `osh.jpg` | https://www.pexels.com/photo/10522937/ |
| `lagmon.jpg` | https://www.pexels.com/photo/27588093/ |
| `manti.jpg` | https://www.pexels.com/photo/12716792/ |
| `qovurma.jpg` | https://www.pexels.com/photo/27588084/ |
| `shashlik.jpg` | https://www.pexels.com/photo/8707683/ |
| `somsa.jpg` | https://www.pexels.com/photo/19441250/ |
| `salat.jpg` | https://www.pexels.com/photo/1639555/ |
| `non.jpg` | https://www.pexels.com/photo/20045238/ |
| `choy.jpg` | https://www.pexels.com/photo/4589177/ |
| `zal.jpg` | https://www.pexels.com/photo/12688995/ |

O'lchamlar: taomlar 900×900 (+ 160×160 `*-160.jpg`), `hero-osh` 1200×1200, `zal` 1600 kenglik.

## Tuzilma

```
.
├── index.html     # bo'limlar: hero, afzalliklar, muammo→yechim, hikoya, menyu, Telegram orqali buyurtma,
│                  # sharhlar, banket, kafolatlar + FAQ, aloqa, footer; savatcha va stol band qilish oynalari
├── styles.css     # dizayn tokenlari (:root) va barcha stillar
├── app.js         # CONFIG, menyu, UZ/RU tarjimalar, savatcha, forma, Telegram xabari
├── assets/img/
└── .github/workflows/pages.yml   # GitHub Pages'ga joylash
```

Tillar: o'zbekcha (asosiy, HTML ichida) va ruscha (`app.js` → `I18N.ru`). Tanlangan til va savatcha brauzerda eslab qolinadi.
