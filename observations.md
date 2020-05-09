# Observations

## Grunnleggende prinsipp

For å måle avstanden mellom satellitt og mottaker, måler man tiden det tar for signalet å strømme gjennom rommet mellom satellitten og mottakeren. Svært nøyaktige tidsmålinger er derfor nødvendig. Signalet har en hastighet på ca. 300 000 km/s \(lysets hastighet _c_\). Ved å gange med reisetiden får man avstanden signalet har forplantet seg.

4 satellitter er nødvendig for å bestemme en mottakerposisjon. De tre første er for å bestemme en romlig posisjon \($X, Y, Z$\). Den fjerde satellitten trenger vi for å korrigere for klokkefeil i mottakeren. GPS satellittene har atomklokker installert, så de er svært nøyaktige. Det er nødvendig når satellittene beveger seg med en hastighet på 4 km/s. GPS mottakeren i hånda de kan av praktiske og økonomiske årsaker ikke ha en atomklokke installert, så denne klokka vil som oftest være usynkronisert med GPS klokkene. Klokkedrift er også et problem. Derfor kreves minimum 4 signaler fra ulike satellitter for å kunne beregne mottakerposisjonen.

## Pseudo-avstands målinger

Pseudo-avstandsmålinger gjøres ved å lese koden på signalet fra satellittene og måle tiden det har tatt fra signalet forlot satellitten til den ankom mottakeren.

 **Figur:** Binært signal \(01010010100011...\) som transmitteres. $\Delta t$ er tidsforsinkelsen mellom når signalet sende og når det mottas. Denne kalles for "pseudo-avstandsmåling".

### Observasjon

$$
P = c(T - T^S)
$$

$T$ er klokkeavlesningen i mottakeren når signalet mottas, $T^S$ er klokkeavlesningen i satellitten når signalet ble avsendt. $c$ er lysets hastighet.

### Sann tid

$$
\begin{align}
&t \ \ = T + dT\\
&t^S = T^S + dt
\end{align}
$$

Den sanne mottakertiden $t$ er mottakerens klokkeavlesning $T$ pluss klokkefeilen i mottakeren \(_clock bias_\) $dT$. Det samme gjelder for satellittklokken. Selv om satellitten bruker en atomklokke, så oppstår det likevel feil mellom GPS klokker og internasjonale klokkestandarder.

$$
\begin{align}
P(t) &= c[(t-dT) - (t^S - dt)]\\
&=  c(t-t^S) - cdT + cdt
\end{align}
$$

### Sann avstand

Den euklidiske avstanden $\rho$ kan også skrives som en funksjon av x, y og z.

$$
\rho(t,t^S) = \sqrt{[x^S(t^S) - x(t)]^2 + [y^S(t^S) - y(t)]^2 + [z^S(t^S) - z(t)]^2}
$$

Ved å substitutuere avstanden kan vi skrive pseudo-avstandsmålingen som

$$
P(t) = \rho(t,t^S) + cdt - cdT
$$

Ved å lese Navigasjonsmeldingen på satellittsignalet kan vi regne ut $x^S$, $y^S$, $z^S$ og klokkefeilen i satellitten $dt$ . De ukjente i ligningen over er mottaker posisjonen \($x$,$y$, $z$ \) og klokkefeilen i mottakeren $dT$.

### Utsendelsesepoke

En ytterligere komplikasjon er at avstandsmålingen $\rho\(t, t^S\)$ gir en sammenheng mellom satellittens posisjon ved _utsendelsesepoken_ \(tidspunkt\) og mottakerens posisjon ved _mottakelsesepoken_. En sammenheng mellom mottakelsesepoken og utsendelsesepoken vil være nødvendig for å få tak i sann tidspunkt for utsendelsesepoken.

Dette kan gjøres ved å se at pseudoavstanden _P_ er en direkte måling av klokkeforskjellen mellom begge epokene.

$$
P = c(T - T^S) = c\Delta t
$$

Slik at

$$
\Delta t = T - T^S = \frac{P}{c}
$$

og

$$
T^S = T - \Delta t
$$

Fra tidligere har vi sett at den sanne tiden i satellitten kan skrives som

$$
t^S = T^S + dt
$$

Hvis vi substituerer $T^S$ får vi

$$
t^S = T - \frac{P}{c} + dt
$$

Denne formelen relaterer sann utsendelsesepoken $t^S$ i GPS tidsrammen med mottakelsesepoken $T$ observert i mottakeren.

### Fullstendig formel

Når vi inkluderer banefeil for satellitten $d\rho$, det vil si feil i $x^S$, $y^S$, og $z^S$, atmosfæriske feil \($d_{\text{ion}}$ og $d_{\text{trop}}$ \) og støy $\varepsilon\(p\)$, så blir den endelige observasjonsligninga for pseudoavstander

$$
P = \rho + d\rho + c(dt - dT) + d_{\text{ion}} + d_{\text{trop}} + \varepsilon(P)
$$

## Bærer \(beat-\) fasemåling

### Beatfase og beatfrekvens

$$
\varphi_B(t) = \varphi_R(t) - \varphi_G(t)\\
f_B = \frac{d\varphi_B}{dt} = f_R - f_G
$$

Observasjonsparameter:

$$
\phi(T) = \varphi^S(T) - \varphi(T) - N^S
$$

#### Ambiguitet

_Ambiguiteten_ i beatfasen $N$ \(antall sykler mellom satellitt og mottaker\) er ukjent til å begynne med, og må regnes ut. Når $N$ er utregnet forblir den konstant for én satellitt \(forutsatt ingen fase-slipp\), mens den faktiske fasen $\phi$ varierer. $N$ varierer normalt fra satellitt til satellitt.

### Faseverdi

En faseverdi ved tidspunkt $t$ kan skrives som en funksjon av initiell faseverdi ved $t=0$ og frekvens

$$
\varphi(T) = \varphi_0 + fT\\
\varphi_{\text{uts}}(T^S) = \varphi_0^S + fT_{\text{trans}}^S
$$

Faseobservasjonen blir derfor

$$
\begin{align}
\phi(T) &= \varphi^S(T) - \varphi(T) - N^S\\
&= \varphi_0^S + fT^S - \varphi_0 - fT - N^S\\
&= \varphi_0^S - \varphi_0 + f(T^S - T) - N^S
\end{align}
$$

\($\varphi\_0$ og $\varphi\_0^S$ er instrumentelle konstanter og benevnes ikke videre.\)

Avstanden målt fra fase kan beskrives som

$$
\begin{align}
\Phi(T) &= -\lambda \phi(T)\\
&= -\lambda f(T^S -T) + \lambda N^S\\
&= c(T - T^S) + \lambda N^S
\end{align}
$$

\($c = \lambda f$ \)

### Fullstendig formel

Vi har den samme formelen for den euklidiske avstanden som for pseudoavstandsmålinger

$$
\rho(t,t^S) = \sqrt{[x^S(t^S) - x(t)]^2 + [y^S(t^S) - y(t)]^2 + [z^S(t^S) - z(t)]^2}
$$

Ved å følge den samme algoritmen for å relatere $t^S$ med $T$, og legge til banefeil, atmosfærisk feil og støy får vi den fullstendige formelen for fasemåling

$$
\Phi = \rho + d\rho + c(dt - dT) + \lambda N - d_{\text{ion}} + d_{\text{trop}} + \varepsilon(\Phi)
$$

## Tidsdefinisjoner

**GPS uke**

**Skuddsekund**

