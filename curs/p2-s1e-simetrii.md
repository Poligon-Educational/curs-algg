# Grupuri de simetrie

Această secțiune poate fi considerată opțională la prima lectură, dar, de fapt,
oferă informații și aplicații care clarifică importanța studiului grupurilor.
În același timp, și din punct de vedere istoric, grupurile s-au dezvoltat începînd
chiar cu grupurile de simetrie.

Acestea au început cu grupuri de permutări (numite *grupuri simetrice*) pe exemple
numerice, inspirate din jocuri de noroc (via Joseph Louis Lagrange și alții).
Ulterior, studiul a luat o direcție surprinzătoare, către *simetrii geometrice*,
care și-au găsit apoi aplicații în fizică, chimie și nu numai.

Începem cu cazul standard, abstract: acela al grupurilor de permutări. Este capitolul
care se studiază și în liceu, și ne va deschide calea către cazurile mai deosebite.
Trebuie menționat, totuși, că, în ciuda aparențelor, exact acest caz cu care ar trebui
să fiți familiarizați din liceu este *cel mai greu*, fiind abstract. De aceea, putem
face observația că, din punct de vedere didactic sau dacă gradul de dificultate ori de
complexitate sînt principalele criterii, nu este cel mai indicat punct de pornire.
Totuși, datorită familiarității lui, am ales să începem cu el.

## Caz abstract: Permutări
Cazul permutărilor este studiat în liceu mai întîi la capitolul numit *probleme de numărare*,
împreună cu combinările și aranjamentele. Într-adevăr, modul de calcul al permutărilor
este înrudit cu cel al aranjamentelor, fiind, dintre ele, cel mai simplu:
$ P(n) = n! $, adică modul în care putem „amesteca“ (*permuta*) $ n $ elemente este
$ n! = 1 \cdot 2 \cdot 3 \cdots n $.

După această introducere, contextul abstract în care au fost întîlnite permutările
este acela funcțional și, ulterior, algebric. Definiția fundamentală este:

```{prf:definition}
:label: def-permutare

Se numește *permutare de $ n $ elemente* o funcție bijectivă de forma:

$$
  \sigma : \{ 1, 2, 3, \dots, n \} \to \{ 1, 2, 3, \dots, n \}
$$
```

Intuitiv, lucrurile sînt simple: a permuta $ n $ elemente înseamnă a face să corespundă
perechi de forma $ (a, b) $, cu $ 1 \leq a,b \leq n $. Imaginea funcției $ \sigma $
din definiția de mai sus înseamnă un set de forma $ \{ \sigma(1), \sigma(2), \dots, \sigma(n) \} $,
pe care îl putem gîndi ca un „amestec“: obiectul (de pe poziția) $ 1 $ ajunge (pe poziția) $ \sigma(1) $
ș.a.m.d.

Acum, faptul că am definit permutările ca funcții ne permite să lucrăm cu toate uneltele
disponibile din studiul funcțiilor. În particular, putem defini *compunerea* permutărilor,
așa cum definim compunerea funcțiilor: prin aplicări succesive.

De pildă, dacă $ \sigma $ este o permutare de $ n $ elemente cu proprietatea că $ \sigma(1) = 3 $,
iar $ \tau $ este o altă permutare, tot de $ n $ elemente, cu proprietatea că $ \tau(5) = 1 $,
atunci are sens să considerăm permutarea $ \sigma \circ \tau $, care funcționează prin aplicări
succesive:
```{math}
5 \xrightarrow{\tau} 1 \xrightarrow{\sigma} 3 \Rightarrow (\sigma \circ \tau)(5) = 3.
```

Așa stînd lucrurile, să notăm cu $ S_n $ mulțimea $ \{ 1, 2, \dots, n \} $, pentru orice
număr natural $ n $. O permutare de $ n $ elemente devine, deci, o funcție bijectivă 
$ \sigma : S_n \to S_n $. Însă compunerea funcțiilor bijective are și proprietăți algebrice
foarte bune, pe care le prezentăm în cazul particular al permutărilor:
- este *internă*: compunînd două permutări $ \sigma, \tau : S_n \to S_n $, rezultatul, indiferent
de ordine, $ \sigma \circ \tau $ sau $ \tau \circ \sigma $ este o permutare din $ S_n $;
- este *asociativă*: $ \alpha \circ (\beta \circ \gamma) = (\alpha \circ \beta) \circ \gamma $,
pentru $ \alpha, \beta, \gamma : S_n \to S_n $;
- admite un *element neutru*, numit *permutarea identică* și notată de obicei cu $ e $:
este permutarea care nu mută nimic, adică, de fapt, o restricție a funcției identitate:
$ e(x) = x, \forall x \in S_n $;
- *nu este comutativă* în general;
- orice permutare admite o *inversă*: fiind vorba despre funcții bijective, ele sînt
inversabile. Intuitiv, permutarea inversă unei permutări $ \sigma $ este cea care face
„drumul invers“. Adică, dacă, de exemplu, $ \sigma(3) = 5 $, trebuie să avem $ \sigma^{-1}(5) = 3 $
ș.a.m.d.

Practic, prin cele de mai sus am demonstrat:

```{prf:theorem}
:label: thm-sn-grup

Operația de compunere a permutărilor definește o structură de grup (în general, necomutativ)
pe mulțimea $ S_n = \{ 1, 2, 3, \dots, n \} $.

Structura rezultată, $ (S_n, \circ) $, se numește de obicei *grupul simetric de $ n $ elemente*.
```

De aici, de obicei, în clasa a XII-a, se definesc elemente specifice, precum *transpozițiile, ciclurile*,
*paritatea* unei permutări, *semnul* permutării ș.a.m.d. Însă vom omite aceste elemente
și vom menționa doar *ordinul* unei permutări, noțiune foarte utilă în aplicații, împreună
cu *teorema lui Lagrange* pentru grupuri.

(sec-ord-grup)=
## Ordinul unui element într-un grup
```{prf:definition}
:label: def-ord

Fie $ (A, \ast) $ un grup, cu $ e $ elementul neutru și $ a \in A $ un element oarecare.

Se numește *ordinul* elementului $ a $, notat $ \mathrm{ord}(a) $, cel mai mic
număr natural $ n $ cu proprietatea că $ a^{\ast n} = e $, unde prin $ a^{\ast n} $
am notat compunerea lui $ a $ cu el însuși de $ n $ ori.
```

Cu alte cuvinte, ordinul unui element într-un grup este numărul de compuneri cu sine
ale elementului respectiv pînă (dacă!) se ajunge la elementul neutru.

Două observații importante:

```{important}
- Nu de la orice element se poate ajunge la elementul neutru! De exemplu, în grupul
$ (\mathbb{Z}, +) $, pornind de la $ 1 $, nu putem ajunge la 0. În acest caz,
spunem că $ \mathrm{ord}(1) = \infty $;
- Este posibil ca o egalitate de forma $ a^{\ast n} = e $, interpretată ca o ecuație,
să aibă mai multe soluții pentru $ n $, într-un grup arbitrar. Ordinul elementului $ a $,
însă, este *cea mai mică* astfel de valoare. De exemplu, în cazul 
[inelelor de clase de resturi](./p2-s2-inele-corpuri.md), avem în grupul $ (\mathbb{Z}_6, +) $,
că $ \widehat{3} + \widehat{3} = \widehat{0} $, dar și $ \widehat{3} + \widehat{3} + \widehat{3} + \widehat{3} = \widehat{0} $
și, în general, orice sumă care conține un număr par de termeni ne conduce la $ \widehat{0} $.
Acesta este chiar un rezultat general:
```

```{prf:theorem}
:label: thm-ordin-multiplu

Dacă într-un grup $ (A, \ast) $ cu elementul neutru $ e $ avem $ a^{\ast t} = e $
și $ \mathrm{ord}(a) = n $, atunci $ n \mid t $.
```

Acest lucru rezultă imediat din definiția ordinului, în special partea privitoare
la *minimalitatea* lui $ n $.

Una dintre principalele aplicații ale ordinului este *teorema lui Lagrange*.

Dar pentru aceasta, mai avem nevoie de o definiție simplă.

```{prf:definition}
:label: def-ord-grup

Se numește *ordinul unui grup* $ G $, notat $ |G| $ sau $ \mathrm{ord}(G) $
sau chiar $ \# G $ numărul de elemente ale mulțimii subiacente.
```

De exemplu, $ \mathrm{ord}(\mathbb{Z}) = \infty $, iar $ \mathrm{ord}(\mathbb{Z}_7) = 7 $,
indiferent dacă lucrăm cu grupul aditiv sau multiplicativ.

```{prf:theorem}
:label: thm-lagrange-grupuri

Fie $ G $ un grup *finit* și $ g \in G $ un element oarecare.

Atunci $ \mathrm{ord}(g) $ este un divizor al $ \mathrm{ord}(G) $.
```

Altfel spus, un grup finit nu poate avea decît elemente al căror ordin este un divizor
al ordinului grupului.

---

În cazul grupurilor de permutări, această proprietate este utilă în mod special,
deoarece, cum $ P(n) = n! $, rezultă că $ \mathrm{ord}(S_n) = n! $. Așadar,
folosind teorema lui Lagrange, rezultă că o permutare de $ n $ elemente nu poate 
avea decît un ordin care să fie divizor al lui $ n! $.

---

(sec-gr-klein)=
## Caz geometric: Grupul lui Klein
Un anumit grup de inspirație geometrică este studiat de obicei în clasa a XII-a.
Este vorba despre așa-numitul *grup al lui Klein*, care amintește de matematicianul
german Felix Klein (1849-1925), unul dintre primii care au propus utilizarea metodelor
de algebră abstractă în geometrie.

Acest grup se poate defini în mai multe moduri. O variantă abstractă, care nu transmite
foarte multe informații la prima vedere este aceasta: Vom nota cu $ K $ mulțimea subiacentă
acestui grup[^klein]. În forma abstractă $ K = \{ e, a, b, c : \mathbb{R}^2 \to \mathbb{R}^2 \} $,
unde cele 4 elemente sînt definite, pentru orice $ (x, y) \in \mathbb{R}^2 $, prin:
[^klein]: O notație care să țină cont de istorie este cu $ V $, de la cuvîntul german
*Vierrengruppe*, adică *grup cu 4 elemente*.

```{math}
\begin{align*}
	e(x, y) &= (x, y) \\
	a(x, y) &= (-x, y) \\
	b(x, y) &= (x, -y) \\
	c(x, y) &= (-x, -y)
\end{align*}
```
Folosind operația de compunere, adică aplicarea succesivă a acestor funcții, găsim
următoarea tabelă:

| $ \circ $ | $ e $ | $ a $ | $ b $ | $ c $ |
|:---------:|:-----:|:-----:|:-----:|:-----:|
| $ e $     | $ e $ | $ a $ | $ b $ | $ c $ |
| $ a $     | $ a $ | $ e $ | $ c $ | $ b $ |
| $ b $     | $ b $ | $ c $ | $ e $ | $ a $ |
| $ c $     | $ c $ | $ b $ | $ a $ | $ e $ |

Vă puteți convinge imediat de aceste calcule foarte simplu. De exemplu:
```{math}
(a \circ b)(x, y) = a(b(x, y)) = a(x, -y) = (-x, y) = c(x, y).
```

Se mai poate vedea, în plus, că grupul este comutativ -- lucru rar întîlnit
în cazul operației de compunere a funcțiilor.

Totodată, putem observa și o aplicație simplă a teoremei lui Lagrange:
cum $ \mathrm{ord}(K) = 4 $, rezultă că fiecare element nu poate avea
decît ordinul $ 1, 2 $ sau $ 4 $. Elementul neutru este mereu singurul exemplu
de element de ordinul $ 1 $ și observăm că toate celelalte elemente au ordinul $ 2 $.
Altfel spus,
```{math}
f \circ f = e, \forall f \in \{ a, b, c \} \subseteq K,
```
deci fiecare element este propriul invers.

Această prezentare abstractă, însă, nu este suficient de grăitoare. Mai ales fiindcă
am menționat că Felix Klein a fost preocupat de aplicarea algebrei în geometrie.
Așa că putem face o identificare geometrică foarte simplă: $ K = \mathbb{R}^2 $
este, de fapt, *planul real*, așa că $ (x, y) \in K $ înseamnă un punct din plan,
identificat prin coordonatele sale (abscisa și ordonata). Apoi, dacă luăm un punct
arbitrar $ P(x, y) $ și reprezentăm grafic imaginile lui $ P $ prin funcțiile
$ e, a, b, c $, constatăm:
- $ e(P) = P $, este transformarea identică, care nu schimbă punctul;
- $ a(P) = Q(-x, y) $ este simetricul lui $ P $ față de axa $ OY $;
- $ b(P) = R(x, -y) $ este simetricul lui $ P $ față de axa $ OX $;
- $ c(P) = S(-x, -y) $ este simetricul lui $ P $ față de originea $ O(0, 0) $.

```{figure} ./img/geogebra-klein.png
---
name: fig-klein
---
Acțiunea elementelor grupului Klein asupra unui punct din plan
```

Mai mult, din tabel, dar și din observații simple, putem vedea că o simetrie
față de $ O(0, 0) $ înseamnă *simultan* o simetrie față de $ OX $ și de $ OY $.

Dacă este să fim riguroși, facem observația că nu am menționat exact ce înseamnă
simetria (o vom face chiar în secțiunea următoare). Însă totodată, în liceu,
am studiat *simetricul unui punct față de o dreaptă*: este punctul care se obține
ducînd o perpendiculară din punctul inițial pe dreapta respectivă și prelungind
perpendiculara pînă cînd distanța de la punctul inițial la dreaptă este egală
cu distanța de la punctul căutat la dreaptă.

```{figure} ./img/simetric-punct-dreapta.png
---
name: fig-simetric-punct-dreapta
---
Simetricul punctului $ P $ față de dreapta $ d $ este $ P' = S_P(d) $
```

În secțiunile care urmează, vom vedea că este vorba despre o *simetrie de reflexie*.

## Simetrii de rotație

### Ce este simetria?
Am parcurs deja o bună parte a acestei secțiuni, dar nu am adresat nicăieri
întrebarea fundamentală *Ce este o simetrie?* Răspunsurile sînt, în general,
complexe, dat fiind că acest concept este foarte important în matematică,
fizică, natură și nu numai. Dar în esență, putem reține următoarele „definiții“
(oarecum informale)

```{prf:definition}
:label: def-simetrie

O *operație de simetrie* este o transformare care se poate aplica unui
obiect astfel încît starea obiectului de după aplicarea operației să fie
identică cu cea dinaintea aplicării.
```

Exemple de transformări includ *rotații* și *reflexii*. În practică, spunem
că un obiect are o simetrie de un anumit tip (caracterizată printr-o operație
de simetrie) dacă i se poate aplica operația respectivă. De pildă, spunem
că *un pătrat are o simetrie de rotație de 90 grade*, deoarece dat un pătrat,
lui i se poate aplica o rotație de 90 grade, iar starea va fi identică cu cea
dinaintea rotației.

O observație importantă este că trebuie să gîndiți pătratul ca *nefiind notat*,
de exemplu, $ ABCD $. Dacă avem o astfel de notație și rotim pătratul cu 90 grade
în sensul acelor de ceasornic (centrul de rotație fiind în centrul său, adică 
la intersecția diagonalelor), atunci pătratul $ ABCD $ devine pătratul $ DABC $,
ca în imaginea de mai jos:

```{figure} ./img/patrat-rotatie.png
---
name: fig-patrat-rotatie-90
---
Rotația pătratului $ ABCD $ în jurul centrului $ O $ cu $ 90^\circ $ produce pătratul $ DABC $
```

Am putea spune că în acest caz, cele două pătrate nu sînt identice, diferența
fiind la „identitatea“ vîrfurilor (vîrful $ A $ nu este același lucru cu vîrful
$ B $, de exemplu -- tocmai faptul că poartă nume diferite le separă).

Așadar, reținem ca idee principală că o *simetrie a unui obiect* este o transformare
(geometrică) prin care obiectul pare că este nemodificat, adică forma sa de după
aplicarea transformării este identică cu cea de dinaintea aplicării.

---

Revenim acum la *simetria de rotație*. Precum intuiți, ea se referă la
transformările de rotație în jurul unui punct fix (numit *centru de rotație*).

```{note}
Dacă nu se precizează altfel, toate operațiile de rotație vor fi considerate
*în sens trigonometric*, adică în sens invers acelor de ceasornic.
```

Să presupunem că fixăm un obiect geometric. Pentru simplitate, vom alege
un poligon regulat, să zicem un pătrat și centrul de rotație fiind centrul
pătratului (intersecția diagonalelor sale). Remarcăm că el are:
- o simetrie de rotație de 90 grade;
- o simetrie de rotație de 180 grade;
- o simetrie de rotație de 270 grade;
- o simetrie de rotație de 360 grade, care, practic, este echivalentă cu
o simetrie de rotație de 0 grade;

Dar lucrurile sînt și mai interesante, deoarece *operațiile de rotație se pot compune*,
adică aplica succesiv. Dacă aplicăm de 2 ori la rînd o rotație de 90 grade,
de exemplu, este ca și cum am fi aplicat o rotație de 180 grade.
Puteți vedea acest lucru imaginîndu-vă că pătratul este, totuși, notat $ ABCD $,
dar nu țineți cont de „numele“ vîrfurilor în analiza simetriei:
- o rotație de 90 grade produce pătratul $ DABC $;
- încă o rotație de 90 grade aplicată succesiv produce pătratul $ CDAB $;
- o rotație de 180 grade a pătratului $ ABCD $ produce pătratul $ CDAB $.

Pentru simplitate, vom prelua notația care se folosește de obicei în cazul rotațiilor:

```{note}
Se notează cu $ R_\theta $ operația de rotație de unghi $ \theta $ a unui obiect în jurul
unui centru de rotație stabilit.
```

Așadar, dacă notăm cu $ \circ $ operația de compunere (aplicare succesivă) a rotațiilor,
am găsit că $ R_{90^{\circ}} \circ R_{90^{\circ}} = R_{180^{\circ}} $.

În esență, lucrurile nu sînt cu mult diferite de compunerea funcțiilor. Este ca și cum
am avea o funcție definită pe „cuvîntul“ $ ABCD $ cu valori într-o permutare a literelor
acestui cuvînt $ f : ABCD \to P(ABCD) $, dar încă și mai interesant este ce fel de 
permutări permitem. Este vorba despre așa-numitele *permutări circulare* sau *cicluri*,
care mută elementele într-o anumită direcție. În cazul pătratului $ ABCD $, permutări
circulare de cîte o poziție, aplicate succesiv, produc:
```{math}
ABCD \to BCDA \to CDAB \to DABC \to ABCD.
```
Se vede în acest caz că, lucrînd cu o permutare (circulară) de 4 elemente, ea are
ordinul 4 (a se vedea {ref}`ordinul unui element într-un grup<sec-ord-grup>`).

Nu ar trebui să fie surprinzător faptul că aici este vorba despre un concept general:

```{important}
Un ciclu de lungime $ n $ are ordinul $ n $.
```

În exemplul de mai sus am prezentat doar cicluri de lungime $ n $ aplicate unor obiecte
de aceeași lungime. Însă are sens să vorbim și despre cicluri de lungime 3 pentru o permutare
de 7 elemente, de exemplu. Aceasta înseamnă pur și simplu că se permută circular
3 dintre cele 7 elemente. Nu continuăm cu detalii, întrucît în cazul simetriilor,
vom lucra doar cu cicluri care permută toate elementele.

Pornind de la observația privitoare la $ R_{90^{\circ}} $, putem scrie o relație mai
generală pentru rotații:

```{math}
:label: eq-rot
R_\alpha \circ R_\beta = R_{2 \pi - \alpha - \beta}, \forall \alpha, \beta \in [0, 2\pi].
```

Continuăm acum analiza proprietăților acestei operații și ne întoarcem la cazul
particular al pătratului. Am văzut că el admite 4 simetrii de rotație, de unghiuri
$ 90^\circ, 180^\circ, 270^\circ $ și $ 360^\circ $, ultima putînd fi identificată
cu rotația de $ 0^\circ $. Cum acestea pot fi privite ca funcții[^func-rot], avem asigurată
și proprietatea de *asociativitate* a compunerii rotațiilor.

[^func-rot]: Fiind vorba de doar 4 elemente, puteți și calcula concret toate compunerile
posibile și verificați asociativitatea direct.

Mai departe, un calcul direct, împreună cu intuiția, arată că rotația de unghi $ 0^\circ $
nu are niciun efect la compunere, deci, de fapt, se comportă ca un *element neutru*.

Totodată, folosind ecuația {eq}`eq-rot` privitoare la compunerea rotațiilor, găsim că 
fiecare operație de rotație este inversabilă. Mai concret, inversa rotației de unghi 
$ \theta $ este rotația de unghi $ 2 \pi - \theta $.

În esență, am demonstrat că **simetriile de rotație descriu o structură de grup**
pe mulțimea reprezentată de vîrfurile (sau laturile) *nenotate* ale unui pătrat.

În general, în cazul grupurilor finite, este util de multe ori să realizăm *tabla compunerii*,
care ne arată exact toate rezultatele operației. Pentru pătrat și rotații, avem:

| $ \circ $           | $ R_{0^{\circ}} $   | $ R_{90^{\circ}} $  | $ R_{180^{\circ}} $ | $ R_{270^{\circ}} $ |
|:-------------------:|:-------------------:|:-------------------:|:-------------------:|:-------------------:|
| $ R_{0^{\circ}} $   | $ R_{0^{\circ}} $   | $ R_{90^{\circ}} $  | $ R_{180^{\circ}} $ | $ R_{270^{\circ}} $ |
| $ R_{90^{\circ}} $  | $ R_{90^{\circ}} $  | $ R_{180^{\circ}} $ | $ R_{270^{\circ}} $ | $ R_{0^{\circ}} $   |
| $ R_{180^{\circ}} $ | $ R_{180^{\circ}} $ | $ R_{270^{\circ}} $ | $ R_{0^{\circ}} $   | $ R_{90^{\circ}} $  |
| $ R_{270^{\circ}} $ | $ R_{270^{\circ}} $ | $ R_{0^{\circ}} $   | $ R_{90^{\circ}} $  | $ R_{180^{\circ}} $ |

## Simetrii de reflexie
Operațiile de simetrie sînt ceva mai diverse pe lîngă rotații, însă. De pildă, o operație
pe care o cunoaștem deja este cea de *reflexie*. Aceasta poate fi gîndită ca o oglindire
într-o oglindă imaginară, plasată în lungul unei axe. De fapt, am întîlnit o astfel de situație
într-un caz mai simplu -- acela al {ref}`grupului lui Klein<sec-gr-klein>`: simetrizarea
unui punct față de o axă înseamnă *reflexia* punctului față de o oglindă plasată chiar
pe axa respectivă.

În cazul pătratului pe care l-am analizat anterior, putem plasa 4 oglinzi:
- două în lungul diagonalelor;
- două în lungul mediatoarelor perechilor de laturi paralele:

```{figure} ./img/patrat-reflexie.png
---
name: fig-patrat-refl
---
„Oglinzile“ care se pot plasa pentru simetriile de reflexie ale unui pătrat
```

Astfel, dacă este să privim operația de „oglindire“ ca pe un fel de funcție
aplicată vîrfurilor denumite ale unui pătrat și dacă notăm cu $ d_1, d_2 $
cele două „oglinzi“ plasate în lungul diagonalelor, respectiv cu $ m_1, m_2 $
cele două oglinzi plasate în lungul mediatoarelor, am avea:
```{math}
\begin{align*}
  d_1(ABCD) &= CBAD \\
  d_2(ABCD) &= ADCB \\
  m_1(ABCD) &= BADC \\
  m_2(ABCD) &= CDBA
\end{align*}
```
Privite astfel, operațiile de simetrie se pot și compune, dar constatăm o proprietate
aparent nefericită: aplicarea succesivă a două astfel de oglindiri nu produce
o stare dintre cele 4 de mai sus (la care putem adăuga oricînd pe cea identică,
adică $ e(ABCD) = ABCD $). De exemplu:
```{math}
(d_1 \circ d_2)(ABCD) = d_1(d_2(ABCD)) = d_1(ADCB) = CDAB,
```
or această configurație nu se regăsește printre cele de mai sus.

Trebuie, însă, puțină atenție, pentru că rezultatul nu este întîmplător.
De fapt, am obținut:
```{math}
(d_1 \circ d_2)(ABCD) = CDAB = R_{180^{\circ}}(ABCD).
```

Prezentăm acum contextul general.

## Grupul diedral
Începem cu definiția abstractă, care ne va motiva să explorăm mai multe exemple.

```{prf:definition}
:label: def-diedral

Se numește *grupul diedral de ordin $ n $*, notat $ D_n $, grupul operațiilor
de simetrie -- rotații și reflexii -- ale unui poligon regulat cu $ n $ laturi,
împreună cu operația de compunere (aplicare succesivă) a simetriilor.
```

Așadar, în cazul pătratului pe care îl studiam mai devreme, eram pe cale de a
descoperi grupul $ (D_4, \circ) $. Știind acum ce căutăm, putem să-l prezentăm
în întregime.

Grupul $ D_4 $ conține operațiile pe care le-am întîlnit pînă acum.
În notațiile anterioare, mulțimea se scrie:

```{math}
D_4 = \{ e, R_{90^{\circ}}, R_{180^{\circ}}, R_{270^{\circ}}, d_1, d_2, m_1, m_2 \}
```
El are multe proprietăți deosebite și începem cu două dintre cele mai evidente:
- operația care „nu face nimic“, adică operația identică, poate fi gîndită fie ca
o rotație de unghi $ 0^{\circ} = 360^{\circ} $, fie ca o reflexie într-o oglindă
plasată nicăieri. Așadar, vom folosi o singură notație, $ e $, pentru această simetrie;
- rotațiile sînt, de fapt, *generate* de $ R_{90^{\circ}} $, în sensul că aplicarea
succesivă a acestei rotații le produce și pe celelalte două:
```{math}
\begin{align*}
  R_{90^{\circ}} \circ R_{90^{\circ}} &= R_{180^{\circ}} \\ 
  R_{90^{\circ}} \circ R_{90^{\circ}} \circ R_{90^{\circ}} &= R_{270^{\circ}}
\end{align*}
```

În plus, folosind teorema lui Lagrange (teorema {prf:ref}`thm-lagrange-grupuri`),
întrucît $ \mathrm{ord}(D_4) = 8 $, rezultă că ordinele elementelor nu pot fi decît
$ 1, 2, 4 $ sau $ 8 $. Ca de obicei, $ \mathrm{ord}(e) = 1 $, fiind singurul
element de ordin $ 1 $. Apoi:
- $ \mathrm{ord}\left(R_{90^{\circ}}\right) = 4 $;
- $ \mathrm{ord}\left(R_{180^{\circ}}\right) = 2 $;
- $ \mathrm{ord}\left(R_{270^{\circ}}\right) = 4 $;
- $ \mathrm{ord}(d_1) = \mathrm{ord}(d_2) = \mathrm{ord}(m_1) = \mathrm{ord}(m_2) = 2 $,
deoarece dubla oglindire aduce la starea inițială.

De asemenea, mai facem observația că grupul $ D_4 $ *nu* este comutativ.
Iar pentru a-i înțelege și mai bine funcționarea, vă îndemnăm să-i alcătuiți tabla
de compoziție.

**#TODO: De pus aici, cu spoiler/dropdown**
