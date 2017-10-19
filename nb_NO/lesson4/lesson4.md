---
title: CSS
level: Lesson 4
language: nb_NO
embeds: "*.png"
materials: "ressurser"
stylesheet: web
...

## Introduksjon { .intro}
La oss gjøre nettsiden vår bedre med noen stiler.
I denne og den neste leksjonen skal vi lære hvordan man endrer farge, tekst, størrelser og mer!

Vi styler HTML-sider ved hjelp av et språk som heter __CSS__ (som står for __Cascading Style Sheets__). Det er et veldig enkelt språk å lære. La oss komme i gang.

#Steg 1: Oppsett for å skrive litt stiler { .activity}
Det er mange måter å legge til stiler på: inline, i `<head>`-elementet, eller som en separat CSS-dokument som vi lenker til fra "hodet". I dag skal vi bruke stiler i `<head>`-elementet i vår HTML-side, slik at vi ikke trenger å bekymre oss for å håndtere flere filer.

## Aktivitet { .check}

+ Åpne index.html i Felix mappen vi lagde i siste økt.

+ I "hodet" (det vil si `head` delen) trenger vi en __style tagg__.
```css
  <style>
  </style>
```
Alle stilene våre vil bli puttet mellom disse to elementene. Generelt ser CSS-kode ut som dette:

```css
elementnavn {
	egenskap: verdi;
}
```

+ Kan du finne ‘{‘ og ‘}’ tastene på tastaturet ditt? Hva med ‘:’ og ‘;’ ?
Elementnavnet kan være HTML-elementer som `h1`, `p`, `img`, `a`. Men det kan også være andre ting som vi vil lære senere.

# Steg 2: Legge til farger { .activity}

La oss legge til litt farge med color-egenskapen! Color er engelsk for farge. Det er stavet på den amerikanske måten. Forresten visste du at CSS ble funnet opp av en nordmann, Håkon Wium Lie?

La oss endre `h1` til å være rød i stedet for svart.

```html
<style>
	h1 {
  		color:red;
  	}
</style>
```

## __LAGRE__ filen og se på den i nettlerseren { .save}

Teksten er nå rød, jippi! Det er forskjellige måter å oppgi verdiene for farge på. Det er 16 grunnleggende fargenavn (på engelsk), de heter aqua, black, blue, fuchsia, gray, green, lime, maroon, navy, olive, purple, red, silver, teal, white, og yellow.

+ Prøv å endre fargen til noe annet!
De fleste nettlesere støtter ytterligere 130 fargenavn, en fullstendig alfabetisk liste finnes på
[http://www.w3.org/TR/css3-color/ # svg-color] (http://www.w3.org/TR/css3-color/ # svg-farge) Hva er din favorittfarge på listen?

+ Men vi kan bruke enda flere farger ved hjelp av __hexkode__ i stedet for fargenavn. En hexkode er en `#` fulgt av seks siffer, tallene 0-9 eller bokstavene A, B, C, D, E, F. Med hexcode kan vi bruke mer enn 16 millioner farger!

+ I kodeklubben, er vår favorittfarge `#58AB57`. Kan du gjette hvilken farge det er? Hvorfor ikke prøve å endre litt tekst til den fargen og åpne den i en nettleser for å se.

## __LAGRE__ filen og se på den i nettlerseren { .save}

#Steg 3: Sett farge på spesifikke elementer { .activity}

Hva hvis vi ønsket å gjøre ordet "oransje" i "pelsen hans er oransje" oransje? Ikke hele avsnittet, bare det ordet.

En måte å gjøre det på er å sette `<span>`-tagger rundt ordet, slik:

`<span> oransje </span>`

Så kan vi style `span`-taggen i 'hodet' på dokumentet vårt.

```css
span {
	color:orange;
}
```

## __LAGRE__ filen og se på den i nettlerseren { .save}

#Steg 4: Bakgrunnsfarger { .activity}

Vi kan legge til farger i bakgrunnen også, ikke bare i selve teksten. For eksempel:

```css
body {
	background-color:#D2FAFC;
}
```
Dette gjør hele bakgrunnen lys blå. Du kan bruke hvilken som helst farge fra [www.colourpicker.com](http://www.colourpicker.com) som genererer den hexkoden du trenger, som du kan klippe ut og lime inn der du trenger den.

Nå prøv:

```css
h1 {
	background-color:black;
}
```
Siden vi allerede hadde en `h1`-erklæring der, kunne vi bare legge til bakgrunnsfargen sammen med fargen, vi trenger ikke å skrive alt på nytt.

```css
h1 {
	color:red;
	background-color: black;
}
```

## __LAGRE__ filen og se på den i nettlerseren { .save}

# Steg 5: Moro med tekst
Kanskje 'mistet' overskriften bør være __større__ og også ha store bokstaver. Vi kan angi størrelsen på teksten ved hjelp av `font-size`. Verdiene kan være masse forskjellig, men de mest vanlige er 12, 14, 16, 32, 48 og 72 piksler.
For nå kan du prøve 72px. (px betyr piksel).

```css
h1 {
    color:red;
    background-color:black;
    font-size:72px;
}
```
Nå kan du prøve å endre overskriften til store bokstaver bare ved å bruke `text-transform:uppercase;` Vi kan også gjøre den understreket ved å bruke `text-decoration:underline;`

## __LAGRE__ filen og se på den i nettlerseren { .save}

Det er mye mer merkbart nå, ikke sant?

### Hvis du har Firefox eller Chrome nettleser:
Faktisk finnes det også en annen verdi for `text-decoration` kalt `blink`. Jeg kommer ikke til å fortelle deg hva den gjør. Du må prøve det. `text-decoration: blink;` (det kan bli litt irriterende etter en stund, du kan bytte tilbake til understrek hvis du foretrekker det).

# Steg 6: Sentrere tekst ( og bilder) horisontalt  {.activity}

All teksten vår er helt over til venstre. Vi kan endre det ved hjelp av `text-align:center` (du kan også bruke verdien "right" som betyr høyre eller "left" som betyr venstre og er standard).
1. Vi vil at all teksten skal være sentrert, så vi kan skrive:

```css
body {
    background-color: #F8FAF4;
    text-align: center;
}
```
La du merke til at alt på siden ble plassert på midten når vi la til `text-align:center` på body-elementet? Det er fordi alt inne i body-elementet arver stilen. Dette skjer når et element ligger inni en annet element, slik som her:

```html
<p>Har du sett Felix? <em>Vennligst</em> kontakt eieren hans</p>
```

Ordet 'Vennligst' vil arve stilen til `<p>`-elementet og ha stilen til `<em>`-elementet i tillegg. Dette er grunnen til at stilene kalles __cascading__ , cascading betyr *å fosse* på engelsk, slik som vannet i en elv. Det betyr at stilene flyter fra et element over til alle de andre elementene som er inni det. Vær forsiktig fordi noen stiler ikke blir *arvet* . Vi vil lære om disse senere.

## __LAGRE__ filen og se på den i nettlerseren {.save}

## Ting du kan prøve {.try}
+ Hvordan ville du endret siden slik at den ser bedre ut? Hvorfor ikke prøve å bruke alle favorittfargene dine? Har de fargenavn eller trenger du å bruke hexkode?
+ Hvis du blir tidlig ferdig kan du gå tilbake og legge til stiler i HTML-filene vi har laget i tidligere leksjoner.
