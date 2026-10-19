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
