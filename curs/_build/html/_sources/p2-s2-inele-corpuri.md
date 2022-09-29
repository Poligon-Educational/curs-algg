# Inele și corpuri

Cazul cel mai simplu al structurilor algebrice este acela al [monoizilor și grupurilor](./p2-s1-grupuri.md).
Este vorba despre structurile algebrice bazate pe o singură mulțime și o singură operație binară
între elementele ei.

Dar exemplele pe care le întîlnim în mod normal rar folosesc o singură operație.
De pildă, am văzut că între toate tipurile de numere, avem cel puțin două operații:
adunarea și înmulțirea, care și interacționează între ele prin așa-numita regulă a
*distributivității* sau de desfacere a parantezelor. Între numere reale, de exemplu,
are loc:

$$ a \cdot (b + c) = a \cdot b + a \cdot c, \quad \forall a, b, c \in \mathbb{R}, $$

astfel că pentru majoritatea scopurilor practice, avem nevoie de cel puțin două operații
care să interacționeze.

Este chiar cazul inelelor și corpurilor, care sînt următoarele structuri algebrice
pe care le prezentăm.

## Exemple și intuiție
Cum am văzut și în secțiunile anterioare, este binevenit să pornim cu cazuri concrete,
de unde să extragem proprietăți abstracte.

Un exemplu prototipic este acela al mulțimii numerelor întregi $ \mathbb{Z} $, împreună
cu operațiile de adunare și înmulțire. Cunoștințe de bază din școală ne conduc la următoarele
observații:
- în raport cu operația de adunare, mulțimea numerelor întregi are o structură de *grup comutativ*.
Altfel spus, dacă studiem structura $ (\mathbb{Z}, +) $, găsim că:
  + adunarea este lege internă între numerele întregi, adică suma a două numere întregi este un număr întreg;
  + adunarea numerelor întregi este comutativă și asociativă;
  + elementul neutru al adunării este numărul 0;
  + simetricul oricărui număr întreg $ x $ este *opusul* său, adică $ -x $;
- în raport cu operația de înmulțire, mulțimea numerelor întregi *fără 0* are o structură de *monoid comutativ*.
Altfel spus, structura $ (\mathbb{Z} \setminus \{ 0 \} = \mathbb{Z}^\ast, \cdot) $ are proprietățile:
  + înmulțirea numerelor întregi este o lege internă, adică produsul a două numere întregi nenule este un număr întreg nenul;
  + înmulțirea numerelor întregi nenule este comutativă și asociativă;
  + elementul neutru al înmulțirii este numărul 1.

Observăm, în plus, că niciun număr întreg nenul nu este inversabil, adică nu are un simetric
față de înmulțire (în afara lui 1, al cărui invers este el însuși).

Pe lîngă aceste proprietăți separate, mai are loc și o proprietate care ne arată interacțiunea
între cele două operații, numită *distributivitate*, pe care o putem scrie în ambele părți,
chiar dacă operațiile sînt comutative în acest caz ($ \forall a, b, c \in \mathbb{Z}^\ast $):

$$
  \begin{align*}
    a \cdot (b + c) &= a \cdot b + a \cdot c \\
    (b + c) \cdot a &= b \cdot a + c \cdot a
  \end{align*}
$$

O structură cu proprietățile de mai sus se numește **inel**. Altfel spus, am demonstrat că
$ (\mathbb{Z}, +, \cdot) $ formează un inel, care este și comutativ, deoarece ambele operații
sînt comutative.

Acum, proprietatea care lipsește -- și pe care o întîlnim în multe situații binecunoscute -- este
clară: putem cere ca și în raport cu a doua operație, cea de înmulțire, să putem simetriza (inversa)
elementele. Într-adevăr, este cazul mulțimilor precum $ \mathbb{Q}, \mathbb{R}, \mathbb{C} $
și altele, unde, practic, putem face toate cele patru operații: adunări, scăderi (= adunări cu opuse),
înmulțiri și împărțiri (= înmulțiri cu inverse).

Să luăm cazul $ (\mathbb{R}, +, \cdot) $, unde constatăm că, pe lîngă proprietățile de inel de mai sus,
avem chiar că $ (\mathbb{R} \setminus \{ 0 \} = \mathbb{R}^\ast, \cdot) $ are o structură chiar
de grup comutativ, întrucît orice număr real este și inversabil: inversul lui $ x \neq 0 $ este
$ x^{-1} = \dfrac{1}{x} $.

În acest caz, obținem structura de **corp**, care este chiar comutativ, pentru că ambele operații
sînt comutative. Lucrurile funcționează identic și în cazul mulțimilor $ \mathbb{Q} $ și $ \mathbb{C} $,
deci avem deja 3 exemple de corpuri: $ (A, +, \cdot) $, unde $ A $ poate fi $ \mathbb{Q}, \mathbb{R}, \mathbb{C} $.

```{note}
Trebuie să ținem cont de două detalii din definițiile inelelor și corpurilor:
- indiferent de a doua operație (în cazurile de mai sus, înmulțirea), prima operație (în cazul de mai sus, adunarea)
*trebuie să fie comutativă*. Dacă și a doua operație este comutativă, atunci structura (inelul, corpul) se numește
comutativă;
- atunci cînd studiem proprietățile celei de-a doua operații, trebuie să eliminăm elementul neutru al primei
operații. În cazurile de mai sus, am studiat mulțimile de numere întregi, reale etc. *nenule*. În general,
dacă $ e \in A $ este elementul neutru al primei operații, atunci a doua operație se studiază pe mulțimea
$ A \setminus \{ e \} $.
```

Ca **terminologie**, ca și în cazul grupurilor -- de data aceasta, fiind și mai relevant -- elementele
neutre se numesc, respectiv, element nul și element unitate, indiferent de definiția
concretă a operațiilor folosite. Mai mult, ele se și notează de obicei cu $ 0 $ și $ 1 $,
iar cînd există riscul de confuzie, se pot adăuga indici. De pildă, pentru o mulțime
oarecare, împreună cu două operații generice, $ (A, \ast, \circ) $, putem nota
elementul nul cu $ e_\ast $ sau $ 0_\ast $, iar elementul unitate cu $ e_\circ $
sau $ 1_\circ $.

```{note}
Dacă vă întrebați de unde provin numele acestor structuri, ele au o istorie bogată.
Pe scurt:
- inelele (eng. *rings*, fr. *anneaux*, ger. *Ringe* etc.) au fost denumite astfel de matematicianul
german David Hilbert (1862-1943), dintr-o expresie din germană și engleză, unde *a ring of objects*
sau *ein Ring aus Objekten* însemna pur și simplu „o grupare de obiecte“;
- corpurile (eng. *fields*, fr. *corps*, ger. *Körper* etc.) au fost denumite astfel datorită
aplicațiilor pe care le au în fizică. Inclusiv în română, pînă în jurul anilor 1970, corpurile
erau denumite *cîmpuri*, deoarece se folosesc pentru a modela matematic anumite cîmpuri fizice
(e.g. cîmpuri electromagnetice, gravitaționale etc.).
```

## Definiții formale
Pentru claritate, vom formula acum definițiile abstracte ale inelelor și corpurilor.

```{prf:definition}
:label: def-inel
Fie $ A $ o mulțime nevidă și $ \ast, \circ $ două operații binare pe $ A $.
Spunem că tripletul $ (A, \ast, \circ) $ formează un *inel* dacă:
- $ (A, \ast) $ are structură de grup comutativ;
- $ (A \setminus \{ e_\ast \}, \circ) $ are structură de monoid.

Dacă, în plus, monoidul $ (A \setminus \{ e_\ast \}, \circ) $ este
comutativ, atunci inelul $ (A, \ast, \circ) $ se numește *comutativ*.
```

```{prf:definition}
:label: def-corp
În condițiile și cu notațiile definiției anterioare, inelul $ (A, \ast, \circ) $
se numește *corp* dacă monoidul $ (A \setminus \{ e_\ast \}, \circ) $ are
structură chiar de grup.

Dacă, în plus, grupul $ (A \setminus \{ e_\ast \}, \circ) $ este comutativ,
atunci corpul $ (A, \ast, \circ) $ se numește *comutativ*.
```

Acum, fiindcă am prezentat în detaliu noțiunile privitoare la [grupuri și monoizi](./p2-s1-grupuri.md)
într-o secțiune separată, avem avantajul de a fi deja familiarizați cu multe dintre
noțiunile care se prezintă foarte asemănător și în cazul inelelor și corpurilor.

De exemplu, o substructură (subinel, subcorp) înseamnă pur și simplu o submulțime
care are aceeași structură. Iar fiindcă avem două operații -- pe care le vom denumi
generic *adunare* și *înmulțire* --, echivalentul teoremelor {prf:ref}`thm-subgrup`
și {prf:ref}`thm-submonoid` se prezintă așa cum intuiți:

```{prf:theorem}
:label: thm-subinel

Fie $ (A, +, \cdot) $ un inel și $ B \subseteq A $ o submulțime.

Atunci $ (B, +, \cdot) $ este *subinel* dacă:
- $ \forall x, y \in B, x - y \in B $;
- $ 1 \in B $;
- $ \forall x, y \in B, x \cdot y \in B $.

În cazul *subcorpurilor*, cerințele sînt:
- $ \forall x, y \in B, x - y \in B $;
- $ \forall x, y \in B, x \cdot y^{-1} \in B $.
```

```{note}
În unele cărți, se cere explicit ca substructura să preia elementele neutre.
Astfel, în notațiile de mai sus, se adaugă explicit cerințele $ 0 \in B $ și
$ 1 \in B $.

Dar, așa cum am văzut, dacă operația admite simetrice, elementele neutre pot fi
obținute ca $ x - x = 0 $, respectiv $ x \cdot x^{-1} = 1 $, deoarece elementele
$ x $ în discuție sînt arbitrare.
```

Nu insistăm pe exemple sofisticate și remarcăm doar că, pornind de la incluziunea
de mulțimi:

```{math}
\mathbb{Z} \subseteq \mathbb{Q} \subseteq \mathbb{R} \subseteq \mathbb{C},
```

avem imediat că $ (\mathbb{Z}, +, \cdot) $ este subinel în oricare dintre inelele
$ \mathbb{Q}, \mathbb{R}, \mathbb{C} $ (care sînt, de fapt, corpuri, însă orice
corp este și inel). Totodată, $ \mathbb{Q} $ este subcorp în $ \mathbb{R} $,
care este subcorp în $ \mathbb{C} $ etc.

```{note}
În cazul inelelor și corpurilor, noțiunile de substructură sînt ceva mai subtile,
în special deoarece avem cele două operații. Astfel, pe lîngă subinele și subcorpuri,
mai există un alt tip de substructură, numit *ideal*. Nu intrăm în astfel de detalii,
însă existența idealelor și problemele specifice sînt motivele principale pentru
care nu detaliem alte construcții și rezultate privitoare la substructuri în cazul
inelelor și corpurilor.
```

---

## Unități și divizori ai lui zero
Această secțiune poate fi considerată opțională, deoarece prezintă două proprietăți
deosebite ale inelelor, care sînt relevante în special în studiul aritmeticii.
Cu toate acestea, am ales să le expunem, deoarece ilustrează fenomene aparent
contraintuitive, dar care se manifestă destul de natural în contexte nu tocmai
complicate.

În cazul mulțimilor de numere, sîntem obișnuiți cu faptul că dacă un produs este
nul, atunci cel puțin unul dintre factori este nul. Formal,

```{math}
x \cdot y = 0 \Leftrightarrow x = 0 \text{ sau } y = 0,
```

oricînd $ x, y $ sînt numere naturale, întregi, raționale, reale sau complexe.

Interpretarea acestui fenomen într-un inel oarecare ar suna așa:

> Dacă $ (A, \ast, \circ) $ este un inel și $ x \circ y = e_\ast $, atunci
> $ x = e_\ast $ sau $ y = e_\ast $.

Dar lucrurile nu stau mereu așa și deja cunoaștem exemple de elemente ale căror
produs este (elementul) nul, deși fiecare dintre ele este nenul. De exemplu,
în cazul matricelor din $ M_2(\mathbb{R}) $, avem:

```{math}
\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} \cdot %
\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix} = %
\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix}.
```

Așadar, nu este o surpriză posibilitatea ca un produs să fie (elementul) nul, deși
niciunul dintre factori nu este (elementul) nul. Elementele cu această proprietate
se numesc **divizori ai lui zero** într-un inel oarecare. Explicația numelui este
clară: un divizor al unui element (număr) este un element (număr) care, prin compunere
(înmulțire), poate produce elementul (numărul) pe care îl divide. De pildă,
$ 2 $ este divizor al lui $ 6 $, deoarece există numărul $ 3 $ cu ajutorul căruia
din $ 2 $ se poate obține $ 6 $ prin înmulțire: $ 2 \cdot 3 = 6 $. Din același
motiv, în acest exemplu, și $ 3 $ este divizor al lui $ 6 $, evident.

Rezultă că un divizor al lui zero este un element care, prin compunere cu un alt element
(ce devine la rîndul său un divizor al lui zero), produce elementul nul. Formal, avem:

```{prf:definition}
:label: def-div-zero

Fie $ (A, \ast, \circ) $ un inel.

Elementul $ x \in A $ se numește *divizor al lui zero* dacă $ x \neq e_\ast $
și există un element $ y \in A, y \neq e_\ast $ astfel încît $ x \circ y = e_\ast $.
```

```{note}
În cazul în care inelul nu este comutativ (adică are doar prima operație comutativă,
nu și pe a doua), se face distincție între *divizor al lui zero la stînga*
și *divizor al lui zero la dreapta*. De pildă, unul la stînga este cel din definiția
de mai sus, cînd $ x $ poate sta doar la stînga lui $ y $ pentru a obține $ e_\ast $.

Însă nu vom insista pe asemenea detalii, întrucît majoritatea exemplelor vor fi de
inele comutative.
```

Alte exemple ceva mai tehnice de divizori ai lui zero, în afară de matrice, se pot da
în *inele de clase de resturi*. Se notează cu $ \mathbb{Z}_n $ sau, în cărțile anglo-saxone,
cu $ \mathbb{Z}/n\mathbb{Z} $, mulțimea claselor de resturi modulo $ n $, cu $ n $ fixat.
Altfel spus, $ \mathbb{Z}_n $ conține resturile posibile la împărțirea prin $ n $.

De exemplu:

```{math}
\mathbb{Z}_7 = \{ \widehat{0}, \widehat{1}, \widehat{2}, \dots, \widehat{6} \}
```

deoarece atunci cînd împărțim la 7, putem obține resturile din $ \{ 0, \dots, 6 \} $.
Fiecare element din mulțime este o *clasă de resturi*, adică o mulțime la rîndul
său. În particular, $ \widehat{0} $ conține toți multiplii de 7 (adică numerele care dau
restul 0 la împărțirea prin 7), $ \widehat{1} $ conține toate numerele de forma
$ 7k + 1, k \in \mathbb{Z} $ etc.

Operațiile de adunare și înmulțire pentru astfel de elemente se definesc natural:
pentru orice $ \widehat{x}, \widehat{y} $ din $ \mathbb{Z}_n $, cu $ n $ fixat, avem:

```{math}
\widehat{x} + \widehat{y} = \widehat{x + y} \quad \text{și} \quad \widehat{x} \cdot \widehat{y} = \widehat{x \cdot y}.
```

De exemplu, în $ \mathbb{Z}_7 $, avem că $ \widehat{2} + \widehat{3} = \widehat{5} $
și $ \widehat{3} \cdot \widehat{5} = \widehat{15} = \widehat{1} $, deoarece $ 15 $ dă,
de fapt, restul $ 1 $ la împărțirea prin $ 7 $.

Inelele de clase de resturi sînt foarte importante în aplicații de criptografie, de exemplu,
unde sînt folosite pentru a facilita operațiile cu numere foarte mari. În ce privește
lecția noastră, vom da doar un exemplu de divizor al lui zero.

Să luăm, de pildă, inelul $ \mathbb{Z}_{10} $ al claselor de resturi modulo $ 10 $, deci
care conține resturile posibile la împărțirea prin $ 10 $, anume $ \widehat{0}, \dots, \widehat{9} $.
Adunarea și înmulțirea fiind definite ca mai sus, elementul nul este $ \widehat{0} $, iar elementul
unitate este $ \widehat{1} $. Acest inel conține divizori ai lui zero, deoarece avem, de exemplu:

$$
  \begin{align*}
     \widehat{2} \cdot \widehat{5} &= \widehat{0} \\
     \widehat{4} \cdot \widehat{5} &= \widehat{0} \\
     \widehat{6} \cdot \widehat{5} &= \widehat{0} \\
     \widehat{8} \cdot \widehat{5} &= \widehat{0}
  \end{align*}
$$

de unde rezultă că $ \widehat{2}, \widehat{4}, \widehat{5}, \widehat{6}, \widehat{8} $ sînt cu toții
divizori ai lui zero.

Noțiunea de *unitate* este una complementară divizorilor lui zero. Am spus că, în general,
prin *unitate* se înțelege elementul neutru în cazul unei operații notate multiplicativ,
fiind echivalentul lui $ 1 $. Noțiunea poate fi generalizată și se numește unitate orice
*divizor al elementului neutru-unitate*, adică orice element inversabil:

```{prf:definition}
:label: def-unitate

Fie $ (A, \ast, \circ) $ un inel și $ e_\circ $ elementul neutru corespunzător.

Elementul $ x \in A $ se numește *unitate* dacă $ x \neq e_\circ $ și există
$ y \in A, y \neq e_\circ $ astfel încît $ x \cdot y = e_\circ $.
```

Ca în cazul divizorilor lui zero, putem face distincția între *unități la stînga*
și *unități la dreapta*, însă vom omite această distincție, presupunînd că lucrăm
cu inele comutative.

Mulțimea unităților unui inel $ A $ se notează cu $ U(A) $ și conține, deci,
toate elementele inversabile. Cu alte cuvinte, în $ U(A) $ găsim exact elementele
care ar face inelul să fie corp. De aceea, dat un inel $ A $, putem obține foarte
ușor un corp dacă păstrăm operațiile, dar schimbăm mulțimea $ A $ cu mulțimea $ U(A) $.

Similar, în cazul monoizilor, dacă $ M $ este un monoid și notăm cu $ U(M) $ elementele
sale inversabile, atunci $ U(M) $ devine grup, cu aceeași operație.

Aici putem da exemple mai simple:

**Exemplu:** Pentru inelul $ (\mathbb{Z}, +, \cdot) $, avem $ U(\mathbb{Z}) = \{ \pm 1 \} $.

**Exemplu:** Pentru inelul $ (M_2(\mathbb{R}), +, \cdot) $, avem $ U(M_2(\mathbb{R}) = GL_2(\mathbb{R}) $.

**Exemplu:** Pentru inelul $ (\mathbb{Z}_{n}, +, \cdot) $, elementele inversabile au o proprietate specială.
Fără demonstrație, bazată pe algoritmul lui Euclid extins, enunțăm:

```{math}
U(\mathbb{Z}_n) = \{ x \in \mathbb{Z}_{n} \mid \mathrm{cmmdc}(x, n) = 1 \}.
```

Cu alte cuvinte, unitățile sînt elementele coprime cu $ n $. Rezultă, de exemplu:

$$
  \begin{align*}
    U(\mathbb{Z}_{10}) &= \{ \widehat{1}, \widehat{3}, \widehat{7}, \widehat{9} \} \\
    U(\mathbb{Z}_{13}) &= \mathbb{Z}_{13}.
  \end{align*}
$$

Din al doilea exemplu, deducem imediat o proprietate foarte importantă,
pe care o enunțăm fără demonstrație.

```{prf:theorem}
:label: thm-zn-corp
Inelul $ \mathbb{Z}_n $ este corp dacă și numai dacă $ n $ este număr prim.
```

Ne oprim aici cu aceste noțiuni, pe care le întîlniți din abundență dacă veți studia
elemente de criptografie și securitatea informației. Pentru scopurile noastre de geometrie
și algebră liniară, vor prezenta interes minor.


---

## Morfisme, nucleu, imagine
Trecem mai departe la morfisme, care nu ar trebui să fie o surpriză că se definesc
foarte asemănător cu cazul {ref}`grupurilor și monoizilor <sec-substructuri-morfisme>`.
Ideea de bază -- anume că morfismele sînt funcții între structuri, care respectă operațiile,
făcînd, astfel, un *transport de structură* -- se păstrează.

```{prf:definition}
:label: def-morfism-inele

Fie $ (A, +, \cdot) $ și $ (B, \ast, \circ) $ două inele și $ f : A \to B $ o funcție.

$ f $ este *morfism de inele* dacă simultan au loc:
- $ f(x + y) = f(x) \ast f(y), \forall x, y \in A $;
- $ f(x \cdot y) = f(x) \circ f(y), \forall x, y \in A $.

Putem cere, suplimentar, ca $ f(e_+) = e_\ast $ și $ f(e_\cdot) = e_\circ $,
caz în care unele cărți denumesc morfismul *unitar*.
```

Cum din punctul de vedere al operațiilor, corpurile se definesc identic cu inelele,
morfismele de corpuri au exact aceeași definiție cu cea pentru inele.

În ce privește *nucleul* unui morfism de inele, trebuie doar să fim atenți
cu care dintre elementele neutre lucrăm în definiție:

```{prf:definition}
:label: def-ker-img-inel
Fie $ (A, +, \cdot) $ și $ (B, \ast, \circ) $ două inele (corpuri), iar
$ f : A \to B $ un morfism.

Se definesc:
- *nucleul morfismului*, $ \mathrm{Ker}(f) = \{ x \in A \mid f(x) = e_\ast \} $;
- *imaginea morfismului*, $ \mathrm{Im}(f) = f(A) = \{ y \in B \mid \exists x \in A, f(x) = y \} $.
```

Și tot ca în cazul monoizilor și grupurilor, avem:

```{prf:definition}
:label: thm-ker-inj-img-surj

În condițiile și cu notațiile din definiția anterioară:
- $ f $ este injectivă dacă și numai dacă $ \mathrm{Ker}(f) = \{ e_+ \} $;
- $ f $ este surjectivă dacă și numai dacă $ \mathrm{Im}(f) = B $.
```

Merită menționată o proprietate surprinzătoare privitoare la corpuri:

```{prf:theorem}
:label: thm-morf-corpuri-inj

Orice morfism de corpuri este injectiv.
```

```{prf:proof}
Fie $ (A, +, \cdot) $ și $ (B, \ast, \circ) $ două corpuri, iar $ f : A \to B $
un morfism de corpuri.

Este suficient să demonstrăm că $ \mathrm{Ker}(f) = \{ e_+ \} $.

Presupunem, prin reducere la absurd, că există $ A \ni x \neq e_+, x \in \mathrm{Ker}(f) $.
Rezultă, prin definiție, că $ f(x) = e_+ $. Dar în același timp, deoarece $ A $ este corp,
rezultă că $ x $ este inversabil, deci există $ x^{-1} \in A $.

Atunci am avea:

$$ e_\circ = f(e_{\cdot}) = f(x \cdot x^{-1}) = f(x) \circ f(x^{-1}) = e_+ \circ f(x)^{-1}, $$

ceea ce este imposibil, deoarece $ e_+ $ nu poate fi inversabil (în cazul numerelor, ar însemna
că am obținut o egalitate de forma $ 1 = 0 \cdot t $, ceea ce este imposibil).

Am obținut o contradicție, deci $ f $ este injectivă.
```

---

Ne oprim aici cu noțiunile abstracte privitoare la inele și corpuri și continuăm cu structurile
mai complicate -- spațiile vectoriale --, care folosesc simultan cîte două structuri deja studiate.
În același timp, acest grad de sofisticare ne va permite și mai multă flexibilitate și aplicații,
precum veți vedea.
