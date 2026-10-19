# 🥗 Kalorije — osobni dnevnik prehrane

Jednostavna web aplikacija za brojanje kalorija. Radi bez servera, bez baze i bez registracije — svi podaci se spremaju **lokalno u tvom pregledniku** (localStorage), pa nitko drugi nema pristup tvojim unosima.

---

## Što aplikacija radi

| Tab | Što je unutra |
|---|---|
| **Danas** | Ukupno kcal u danu + koliko još možeš pojesti, traka do cilja s postotkom, te masti / ugljikohidrati / vlakna / proteini (svaki s vlastitim ciljem). Ispod toga 4 obroka: **Doručak, Užina, Ručak, Večera** — svaki sa svojim zbrojem kcal i unosima. |
| **Kalendar** | Mjesečni pregled: svaki dan obojen prema tome jesi li u cilju (zeleno = u cilju, žuto = blizu cilja, crveno = preko cilja, sivo = bez unosa). Klikom na dan skačeš na taj dan i možeš naknadno upisati što si jela. Dots ispod broja = taj dan si se vagala. Gore su i mjesečni sažeci (dana s unosom, prosjek kcal, ukupno kcal). |
| **Namirnice** | **Tvoj vlastiti popis** namirnica s vrijednostima na 100 g. Nema nikakve tvorničke baze hrane ni *premade meals*. |
| **Težina** | BMI iz tvoje visine i zadnjeg vaganja (s oznakom pothranjenost / normalno / prekomjerna / pretilost), praćenje kilaže od početne do ciljne težine, graf kretanja težine i povijest vaganja s razlikom po vaganju. |
| **Ciljevi** | Visina, početna i ciljna težina, dnevni ciljevi za kcal i sve makronutrijente + gumb za prijedlog raspodjele. Tu je i **backup** (izvoz/uvoz .json) i brisanje svih podataka. |

---

## Kako se unosi (tvoj način rada)

1. Klikni **„+ Dodaj · Doručak“** (ili Užina / Ručak / Večera).
2. Upiši naziv i vrijednosti **na 100 g**: kcal, masti, ugljikohidrate, vlakna, proteine.
3. Upiši **koliko grama si pojela** (npr. 137).
4. Odmah ispod ti se u živo prikaže izračun za tu gramažu: kcal + svi makronutrijenti.
5. **Spremi.**

### Namirnice se NE spremaju same
Kvačica **„Spremi u Moje namirnice“** je **zadano isključena**. Dok je isključena, unos postoji samo u tom danu — ništa se ne pamti, ništa se ne grupira, ništa se ne dodaje na popis. Ako je uključiš, unos dobije zvjezdicu **★** i namirnica ide na tvoj popis (na 100 g) — pa je sljedeći put dovoljno početi tipkati naziv i vrijednosti se same popune.

> Zato možeš istu namirnicu svaki put jesti u drugoj gramaži bez ikakvog automatskog „pamćenja“ i bez ikakvih gotovih obroka.

Sve unose možeš urediti (✎) ili obrisati (✕) klikom na dan u kalendaru — i za dane unatrag.

---

## Kako je hostati besplatno

Potrebna su ti samo 4 filea iz ove mape (`index.html`, `manifest.webmanifest`, `sw.js` i ikone). Aplikacija je statična, bez ikakvog backenda.

### Opcija A — Netlify Drop (najbrže, ~1 min)
1. Otvori <https://app.netlify.com/drop>
2. Prereži cijelu mapu `kalorije` u prozor.
3. Dobiješ link tipa `https://tvoje-ime.netlify.app` — radi odmah, bez računa. Za trajni link napravi besplatni račun.

### Opcija B — GitHub Pages
1. Napravi repozitorij na GitHubu i ubaci sve fileove (index.html mora biti u rootu).
2. **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
3. Za minutu je dostupno na `https://tvoje-ime.github.io/ime-repozitorija/`.

### Opcija C — Cloudflare Pages
1. <https://pages.cloudflare.com> → *Create a project* → *Direct upload* → prereži mapu. Besplatno, bez računa za karticu.

### Opcija D — samo jedna datoteka
Možeš hostati i **samo `index.html`** (npr. na bilo kojem static hostingu) — sve funkcije rade bez dodatnih fileova; jedino nema „instaliraj na mobitel“ ikone i offline cachea.

### Na mobitelu kao aplikacija
Kad je hostano preko https, otvori link u Chromeu/Safariju → **Dodaj na početni zaslon**. Aplikacija se otvara preko cijelog ekrana kao prava app i radi i kad nema interneta.

---

## Važno o podacima

- Podaci žive **u localStorage onog preglednika i uređaja** na kojem unosiš. Ako obrišeš povijest preglednika / „site data“, podaci nestaju.
- Zato povremeno u **Ciljevi → Podaci → Izvezi backup (.json)** i spremi datoteku negdje sigurno.
- Na drugom uređaju napraviš **Uvezi backup** i nastaviš gdje si stala.
- Ako više ljudi koristi isti link — svatko ima svoje podatke, ništa se ne dijeli, jer nema servera.

## Tehnički detalji

- Čisti HTML + CSS + JavaScript, bez frameworka, bez vanjskih biblioteka i bez internetskih fontova — učitava se trenutno.
- Prilagođeno mobitelu (jednoručno korištenje), radi i na desktopu.
- Unos decimalnih brojeva ide i s decimalnim zarezom (`12,5`) i s točkom (`12.5`).
- PWA: service worker cacheira aplikaciju za offline rad.
