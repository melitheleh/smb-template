# SMB-mal – felles nettsidemal

Én sammenhengende mal (design + tekststil) inspirert av [smbnorge.no](https://smbnorge.no/bli-medlem/) og strukturen på [sme-d.se](https://sme-d.se/). Bygget som statisk prototype med **Bootstrap 5** (via CDN). Malen er laget for å gjenbrukes av flere medlemsorganisasjoner:

- **SMB Forsvar og Sikkerhet** – brukt som eksempeldesign her
- **Norsk-Sveitsisk Handelskammer**
- **Norsk Bårebærerforening**

## Innhold

```
SMB_mal_wp/
├── index.html          # Forside (hero, medlemmer, saker, nyheter, medlemskap, nyhetsbrev)
├── kontakt.html        # Kontaktside med kontaktskjema + nyhetsbrevpåmelding
├── assets/
│   ├── css/theme.css   # Tema: farger, typografi, komponenter (bygger på Bootstrap)
│   └── img/
│       ├── logo.svg        # Logo (mørk) – skjold + ordmerke
│       ├── logo-white.svg  # Logo (hvit) til mørk bakgrunn
│       └── hero.svg        # Abstrakt hero-bakgrunn
└── README.md
```

## Funksjoner (bevisst enkelt)

- 5 menypunkter: **Våre saker · Medlemmer · Medlemskap · Om oss · Kontakt**
- Kontaktskjema (klientvalidering, bekreftelsesmelding)
- Påmelding til nyhetsbrev (forside + kontaktside)
- Responsivt, ingen avanserte funksjoner

## Rebranding per organisasjon

Designet følger SMB Norges profil: **rød + sort + hvit**, pille-knapper, skrå striper og fonten **Mulish**. Alt av farger styres av CSS-variabler øverst i `assets/css/theme.css`:

```css
:root {
  --red:      #E8112D;  /* primær (SMB Norge-rød) */
  --red-dark: #C20D24;  /* hover */
  --red-deep: #B00C20;  /* mørk stripe */
  --ink:      #1A1A1A;  /* tekst / overskrifter */
  --black:    #1C1C1C;  /* footer / mørke felt */
  --gray-100: #F4F4F5;  /* lyst seksjonsfelt */
}
```

For en ny organisasjon: bytt disse verdiene, erstatt `logo.svg` / `logo-white.svg`, og oppdater tekst/navn i `index.html` og `kontakt.html`.

> Merk: fargene og fonten er lest av fra skjermbilder av smbnorge.no. Rødtonen (`#E8112D`) er et nært estimat – juster ved behov mot offisiell profilhåndbok. Fonten Mulish er valgt som nærmeste frie match til SMB Norges typografi.

## Se malen lokalt

Åpne `index.html` direkte i nettleseren, eller kjør en enkel server:

```bash
python3 -m http.server 8000
# åpne http://localhost:8000
```

## Vei videre til WordPress

Dette er designprototypen. Neste steg er å dele opp i WordPress-maler (`header.php`, `footer.php`, `front-page.php`, `page.php`) og koble skjemaene til en plugin (f.eks. Contact Form 7 / WPForms) og nyhetsbrev (Mailchimp/Sendinblue).

## Git

```bash
git init
git add .
git commit -m "SMB-mal: designprototype (Bootstrap 5)"
```
