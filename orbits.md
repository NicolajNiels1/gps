# Orbits

## Krefter som påvirker satellittbaner

### Sfæriske effekter

Jorda kan modelleres som en sfære eller – enda enklere – en punktmasse. I tillegg kan tyngdepotensialet for en slik masse modelleres radielt som $\frac{GM}{r}$ hvis man neglisjerer massen til satellitten \(veldig liten sammenlignet med jorda\).

Man antar at satellitten ikke er påvirket av effekter som elektromagnetisk trykk fra sola, atmosfærisk motstand osv.

Tyngdekrefter på grunn av månen, sola og andre himmellegemer nelisjeres også.

Da kan man bruke Keplers 6 bane-elementer til å fastsette satellittens posisjon i rommet.

> **Effekt:** 57 Gal \(1 Gal er 1 cm/s$^2$\)

### Ikke-sfæriske effekter

Jorda er i virkeligheten ikke en perfekt sfære. De fleste vet at den er noe sammenpresset til en ellipsoide. Videre er ikke massetettheten til jorda jevnt fordelt, slik at tyngdefeltet heller ikke er så glatt at man kan se bort i fra disse effektene når man skal bestemme satellittbaner nøyaktig.

Jordas tyngdepotensiale kan uttrykkes som følger



> **Merk:** Effekten fra jordas flattrykning – representert ved $J\_{20}$ – er omtrent tre ganger så stor som effekten fra de andre koeffisientene. Den er likevel bare $10^{-4}$ så stor som de sfæriske tyngdeeffektene beskrevet over.
>
> **Effekt:** 0.005 Gal

### Tyngdekrefter fra månen og sola

Aksellerasjonskreftene på grunn av månen og sola med masse $m$ kan beskrives med hensyn på posisjonen $\overrightarrow{r}_{\text{cel}}$ til himmellegemet og $\overrightarrow{r}_{\text{sat}}$ til satellitten

$$
\overrightarrow{a}_{\text{tide}} = Gm\left[\frac{\overrightarrow{r}_{\text{cel}} - \overrightarrow{r}_{\text{sat}}}{\left|\overrightarrow{r}_{\text{cel}} - \overrightarrow{r}_{\text{sat}}\right|^3} - \frac{\overrightarrow{r}_{\text{cel}}}{\left|\overrightarrow{r}_{\text{cel}}\right|^3}\right]
$$

Tyngdekrefter fra andre himmellegemer en solen og månen er neglisjerbare

> **Effekt:** Månen: $5\cdot 10^{-4}$ Gal \(500 $\mu$Gal\), Solen: $2\cdot 10^{-4}$ 200 \($\mu$Gal\)

**Indirekte effekt på grunn av tidevann på Jorda**

> **Effekt:** Tidevann 0.1 $\mu$Gal \(tilsvarer $10^{-7}$ Gal\)

### Strålingstrykk fra solen

Strålingstrykk fra solen \(eng: _Solar Radiation Pressure \(SRP_\) kommer av at den elektromagnetiske strålingen i verdensrommet ikke bare inneholde energi, men også impuls fra fotonene som treffer sattelittens overflate.

![Solar radiation pressure](https://upload.wikimedia.org/wikipedia/commons/8/8f/Sail-Force1.gif?1574754323661)

**Hovedkomponent**

Strålingstrykket har en hovedkomponent $d\boldsymbol{\ddot{\varrho}\_1}$ i stråleretningen \(linje fra solen gjennom satellitten\). Den kan uttrykkes som:

$$
d\boldsymbol{\ddot{\varrho}_1} = \nu K\varrho_{\odot}^2 \frac{\boldsymbol{\varrho} - \boldsymbol{\varrho}_{\odot}}{\left\|\boldsymbol{\varrho} - \boldsymbol{\varrho}_{\odot}\right\|^3}
$$

$\nu$ er en "formørkelsesfaktor" og brukes til å vekte komponenten . F.eks. dersom satellitten er bak jorden i forhold til sola, så er $\nu=0$.

$K$ er en faktor som er proporsjonal med forholdet mellom areal og masse. Det vil si at en satelitt med liten overflate og høy masse blir mindre påvirket av solstrålingstrykk. Dette er viktig å tenke på når man designer GPS satellitter.

> **Effekt:** 10 $\mu$Gal

**Y-bias**

Strålingstrykket har også en sekundær komponent $d\boldsymbol{\ddot{\varrho}}\_2$, også kalt Y-bias. Denne skyldes at strålingen ikke treffer ortogonalt på satellitten pluss effekten av varmestråling langs y-aksen. Y-aksen er ortogonal på strålingsretningen og satellittens antenne-retning \(normal peker antenna mot jordsentrum\).

> **Effekt:** 0.1 $\mu$Gal

**Albedo**

_Albedo_ er navnet på effekten som skyldes stråling som reflekteres tilbake fra jordas overfalte. For MEO satellitter kan denne effekten neglisjeres da den er mindre en Y-bias komponenten.

### Andre effekter

* Atmosfærisk motstand \(neglisjerbar for MEO satellitter\)
* Relativistisk effekt for satellitt posisjon, 0.003 $\mu$Gal \(neglisjerbar\)
* Solvind \(neglisjerbar\)
* Magnetiske kraftfelt \(neglisjerbar\)

#### Relativistisk effekt for GPS klokke

GPS $45$ $\mu$sek raskere enn klokker på jorda. Tilsvarer ca. 11 km feil \(mtp. lysets hastighet\).

## Banebestemmelse

### Keplers lover

**1. Banen til en hver satellitt er en ellipse og Jorda er i en av dens foci.**

**2. En satelitt beveger seg langs sin bane med en konstant "arealhastighet".** 

**3. Forholdet mellom kvadratet av omløpstiden** $T$ **til satelitter, er det samme som forholdet mellom størrelsen til de store halvaksene** $a$ **til de respektive satelittbanene.**

Ved å bruke **Newtons tyngdelov**

$$
F_g = \frac{GM_1M_2}{D^2}
$$

Kan vi med elementær algebra finne at hastigheten til satelitter i bane rundt jorda ikke avhenger av massen til jorda. $D$ er avstanden mellom masse 1 og masse 2.

$$
V_{sat} = \frac{GM_{jord}}{D}
$$

Veg, fart, tid gir oss

$$
\frac{4\pi^2D^2}{P^2} = \frac{GM_{jord}}{D}
$$

Her er $P$ omløpsperiode. Ved å flytte litt rundt på komponentene får vi ut perioden

$$
P^2 = \frac{4\pi^2}{G}\frac{1}{M_{jord}}D^3
$$

$D = a$ stor halvakse

### Banetyper

### Koordinatsystemer

#### Keplerelementer og keplerbane

Gjennomsnittlig angulær hastighet \(hvis banen hadde vært sirkulær med radius $a$, konstant hastighet\)

$$
n = \frac{2\pi}{P} = \sqrt{\frac{GM}{a^3}}
$$

For GPS baner: $a = 26560$

$GM = 3 986 004.418 x 10^8 \frac{m^3}{s^2}$

Som gir en omløpsperiode på 12 siderale timer.

$$
\boldsymbol{\overrightarrow{r}}_{OR} = 
\left[
\begin{array}{c}
  x\\[2mm]
  y\\[2mm]
  z
\end{array}
\right]_{OR}
=
a \left[
\begin{array}{c}
    \cos{E} - e\\[2mm]
  \sqrt{1-e^2}\sin{E}\\[2mm]
  0
\end{array}
\right ]
= r\left[
\begin{array}{cc}
    \cos{f}\\[2mm]
    \sin{f}\\[2mm]
    0
\end{array}
\right]
$$

**Keplerelementene**

I _normale_ baner er gjennomsnittlig anomali den eneste tidsvarierende parameteren. I virkeligheten er ikke situasjonen like enkel. Selv z-komponenten i bane-planet er ikke konstant null. Slike parametre kalles da for _Oscillerende Kepler elementer_.

#### Celestial referansesystem

Et Celestialt referansesystem er vanligvis definert som en koordinatsystem som ikke roterer med jorda. Det internasjonale konvensjonelle referansesystemet \(ICRS\) er definert ved at:

**ICRS:**

* Origo er jordas geosenter
* Z-aksen peker mot gjennomsnittlig celestial Efemeris pol \(CEP\)
* X-aksen peker mot gjennomsnittlig 
* Y-aksen gjør systemet til et høyrehåndssystem

**Realisering:** ICRF2

#### Terrestialt referansesystem

**ITRS:**

* Origo er jordas geosenter
* Z-aksen er gjennomsnittlig posisjon av jordas rotasjons akse \(CIO, Conventional International Origin = IRP, Internasjona referanse pol\).
* X-aksen mot gjennomsnittlig Greenwich meridian \(IRM\). Merk: ikke på Greenwich campus!
* Y-aksen kompletterer høyrehåndssystemet

**Realisering:** ITRF14, WGS84\(G1762\)

### Transformasjon mellom koordinatsystemer

**GAST:** Greenwich Apparent Sidereal Time

### Beregning

#### Kepler ellipse

#### Håndtere de ulike forstyrrende effektene

## GPS Efemerider

### Almanac data

### Kringkastede efemerider

### Presise efemerider

## Utover GPS – Internasjonale referanserammer

