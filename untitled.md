# Signals

## _Hvorfor?_

Grunnleggende kunnskaper om GPS signaler er en forutsetning for å få mest mulig ut av en GPS mottaker.

## Komplisert

* Multi-bruker system
* Sanntids posisjonering
* Høy-nøyaktighets posisjon \(10 m\) og Hastighet \(10 cm/s\)
* Anti-jamming krav \(spread spectrum\)
* Blanding av militære og sivile sluttbrukere \(P og C/A koder\)

## L-bånd

**L-bånd:** 1-2 GHz

### Krav

* Høy båndbredde for kode modulering på bærefrekvensen
* Valgt frekvens må være i et område for signalforplantning ikke blir alt for påvirket av værfenomen som regn, snø og skyer.
* Ionosfæriske forsinkelser må reduseres
* Retningsuavhengig \(rundstrålende\) : må være mindre enn 2GHz

  ![Omidirectional signal propagation](https://upload.wikimedia.org/wikipedia/commons/a/a6/Dipole_xmting_antenna_animation_4_408x318x150ms.gif)

* Kompromiss mellom tap av signal \(_space loss_\) og ionosfæriske forstyrrelser

### Design

**L1**: 1 575,42 MHz, $\lambda = $ 19,05 cm

**L2**\(military\), **L2C**: 1227,60 MHz, $\lambda =$ 24,45 cm

**L5**: 1176,45 MHz, $\lambda =$ 25,48 cm

## Definisjoner

## Signal struktur

* Fundamental frekvens og sammenheng med bærebølge, C/A kode, P-, Y- og W-kode

### Signal modernisering

**L2C**

* Muliggjør flerfrekvente C/A mottakere
* Økt signalstyrke, bedre signalmottakelse

**L5**

* Safety-of-life og andre høyytelses applikasjoner

**L1C**

* Trilaning \(3 frekvenser\)
* Sub-meter nøyaktighet uten utvidelser

### Signal modulering

 Figur: Bildet viser forskjellen på amplitude-, frekvens- og fasemodulasjon

**Pseudo Random Noise Code \(PRN\)**

* Maksimum autokorrelasjon ved null-forsinkelse \(zero-lag\)

**Binary Biphase Modulation**: The technique used to "code" \(modulate\) the coded message on the carrier signal. Bølgeligning:

$$
Y = A(t)\cdot \cos(\omega t + \varphi(t))
$$

Amplituden $A$ har enten verdi 1 \(normal fase tilstand, binær 0\) eller -1 \(speilbilde tilstand, binær 1\).

Vinkelhastighet:

$$
\omega = 2\pi \text{f} = \frac{2\pi}{T}
$$

 **Figur:** Signal karakteristikker

**Modulo-2 addisjon** $0 \oplus 0 = 0$ $0\oplus 1 = 1$ $1\oplus 0 = 1$ $1\oplus 1 = 0$

## Autokorrelasjon

## C/A Kode generering

**Binary Phase Shift Keying \(BPSK\)**: Technique to create NAV message, C/A and P\(Y\) codes.

**Shift register**

**Tapped feedback shift Register \(TFSR\)** 

## Mottakeren

