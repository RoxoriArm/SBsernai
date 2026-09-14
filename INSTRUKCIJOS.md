# Bendrijos svetainės diegimo instrukcija

Šiame archyve yra pilnai paruošta svetainė (naujienos, renginiai, šiukšlių
grafikas, galerija) ir paprasta redagavimo forma (Sveltia CMS), veikianti
kaip Decap CMS, bet be papildomo OAuth serverio — prisijungsite per GitHub
Personal Access Token.

## 1 žingsnis — GitHub paskyra

Jei dar neturite: `github.com` → `Sign up`.

## 2 žingsnis — repozitorija

Sukurkite naują **viešą** (Public) repozitoriją.

**Paprasčiausia** — pavadinkite ją tiksliai taip: `JUSU-VARDAS.github.io`
(pakeitę `JUSU-VARDAS` į savo tikrą GitHub vartotojo vardą). Toks
pavadinimas leidžia svetainei veikti iš karto pagrindiniu adresu
`https://jusu-vardas.github.io`, be jokio papildomo katalogo pavadinimo
adrese ir be papildomų nustatymų faile `_config.yml`.

*(Jei norite kitokio pavadinimo, tai irgi galima — tuomet faile
`_config.yml` reikės įrašyti `baseurl: "/repozitorijos-pavadinimas"`.)*

## 3 žingsnis — įkelti failus

Repozitorijoje: `Add file` → `Upload files` → nutempkite **visą šio
archyvo turinį** (išlaikant katalogų struktūrą: `_news`, `_events`,
`_data`, `_layouts`, `_includes`, `assets`, `admin` ir kt.) → `Commit
changes`.

Jei jums patogiau naudoti `git` komandinę eilutę, žinoma, galite ir taip.

## 4 žingsnis — įjungti GitHub Pages

Repozitorijoje: `Settings` → `Pages` → ties `Source` pasirinkite
`Deploy from a branch` → šaka `main`, katalogas `/ (root)` → `Save`.

Po 1–2 minučių svetainė bus pasiekiama nurodytu adresu (jį GitHub parodys
tame pačiame lange).

## 5 žingsnis — CMS: nurodyti savo repozitoriją

Atsidarykite failą `admin/config.yml` (repozitorijoje arba lokaliai) ir
pakeiskite eilutę:

```yaml
repo: JUSU-VARDAS/JUSU-REPOZITORIJA
```

į savo tikrą vartotojo vardą ir repozitorijos pavadinimą, pvz.:

```yaml
repo: jonas-petraitis/jonas-petraitis.github.io
```

Išsaugokite (jei redagavote per naršyklę — `Commit changes`).

## 6 žingsnis — prieigos raktas (Personal Access Token)

Kadangi esate vienintelis (ar vienas iš kelių patikimų) redaktorius,
paprasčiausia prisijungti per asmeninį prieigos raktą — nereikia diegti
jokio papildomo serverio.

1. GitHub → viršuje dešinėje savo nuotrauka → `Settings`
2. Kairėje apačioje: `Developer settings`
3. `Personal access tokens` → `Fine-grained tokens` → `Generate new token`
4. `Repository access` → `Only select repositories` → pasirinkite savo
   bendrijos repozitoriją
5. `Permissions` → `Repository permissions` → `Contents` → `Read and
   write`
6. `Generate token` → **nukopijuokite raktą iš karto** (jis parodomas tik
   vieną kartą!)

## 7 žingsnis — prisijungimas prie redagavimo formos

Atsidarykite naršyklėje: `https://jusu-adresas/admin/`

Prisijungimo lange pasirinkite prisijungimą per prieigos raktą (personal
access token) ir įklijuokite raktą, kurį nukopijavote. Atsidarys forma su
keturiomis skiltimis: **Naujienos**, **Renginiai**, **Šiukšlių grafikas**,
**Nuotraukų galerija**.

## Kaip vyks kasdienis naudojimas

- **Nauja naujiena / renginys** — spaudžiate „New", užpildote laukus
  (pavadinimas, data, tekstas), spaudžiate „Publish". Po pusės minutės
  pakeitimas matomas svetainėje.
- **Šiukšlių grafiko keitimas** — atsidarote skiltį, redaguojate eilutes
  formoje (ne kodą).
- **Nuotraukos** — įkeliate paprastu nutempimu, pridedate trumpą aprašymą.

Du pavyzdinės iliustracijos galerijoje (`pavyzdys-1.svg`,
`pavyzdys-2.svg`) skirtos tik parodyti, kaip atrodys išdėstymas — ramiai
jas pakeiskite tikromis nuotraukomis arba ištrinkite.

## Vėliau — savo domenas

Kai nuspręsite pirkti `.lt` domeną: repozitorijos `Settings` → `Pages` →
`Custom domain` → įrašote domeną, o domeno valdyme nustatote DNS įrašus
(GitHub tiksliai nurodys, kokius) į GitHub Pages. Turinys ir CMS liks
lygiai tokie patys, tik svetainės adresas pasikeis.
