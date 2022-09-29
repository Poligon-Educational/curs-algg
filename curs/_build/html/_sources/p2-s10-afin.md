# Spații afine

Această secțiune poate fi considerată opțională în primă fază, pentru că prezintă
o structură care se adaugă aceleia de spațiu vectorial, cu un scop aparent îngust.
Însă vom vedea în secțiuni ulterioare că transformările din spații afine și chiar
structurile corespunzătoare spațiilor înseși sînt foarte des întîlnite.

Intuitiv, un spațiu afin este unul în care noțiunile din spații euclidiene se 
abstractizează și mai mult. Noțiunile *numerice* de distanță și măsură a unghiurilor
se elimină și se pune accentul pe proprietăți *situaționale* privitoare la drepte,
segmente și puncte. Astfel, concepte esențiale devin *paralelismul* și *asemănarea*,
ultima bazată pe rapoarte ale segmentelor.

O altă trăsătură importantă a spațiilor afine este că, din moment ce nu ne 
interesează să măsurăm distanțe, nu se distinge niciun punct fix ca origine.
Rezultă că vectorii nu mai au origini fixe și nu se mai poate asocia un vector
unic la un punct -- numit, în spații euclidiene, *vectorul de poziție* al punctului.
O altă consecință este că, date două puncte, putem defini *diferența lor* prin 
vectorul care dă deplasarea de la un punct la altul, adică distanța dintre cele
două puncte. Însă nu mai putem defini *suma punctelor*, care s-ar face cu ajutorul
vectorilor de poziție și regulii paralelogramului.

```{figure} ./img/puncte-afine.png
---
name: fig-puncte-afine
---
Diferența a două puncte afine $ B - A $ se poate defini, dar suma lor $ A + B $, nu
```

Orice spațiu vectorial poate fi gîndit ca un spațiu afin cîtă vreme nu mai ținem
cont de rolul special pe care îl are vectorul nul, ca origine a sistemului de
coordonate. Toți vectorii din spațiu devin pur și simplu *vectori de translație*,
adică unii care ne ajută să trecem de la un punct la altul. Vectorul nul rămîne
doar cu semnificația de „translație pe loc“.

## Definiții formale
Prezentarea următoare se va baza pe §3 din {cite}`geotools`.

Un spațiu afin $ A $ este alcătuit dintr-o mulțime de puncte $ P $ și o mulțime
de vectori $ V $ astfel încît $ V $ să fie un spațiu vectorial. Dimensiunea
spațiului afin $ A $ se definește ca fiind dimensiunea spațiului vectorial.
Mulțimea de puncte din $ A $ se mai notează cu $ A.P $, iar mulțimea de vectori,
cu $ A.V $. Relația dintre $ A.P $ și $ A.V $ se bazează pe axiomele:

1. $ \forall P, Q \in A.P, \exists! v \in A.V $ astfel încît $ v = P - Q $;
2. $ \forall Q \in A.P, \forall v \in A.V \exists! P \in A.P $ astfel încît $ P - Q = v $;
3. $ \forall P, Q, R \in A.P $ are loc $ (P - Q) + (Q - R) = P - R $.

Primele două relații ne dau exact legătura biunivocă între puncte și vectori:
pentru orice două puncte, există un vector de translație între ele și pentru orice
vector, există două puncte care-l fac vector de translație între ele.

În contextul de mai sus, vectorul nul este pur și simplu definit prin
$ 0 \in A.V $ astfel încît $ P - P = 0, \forall P \in A.P $.

**Operațiile** permise în spații afine se interpretează în noul context:
- putem aduna doi vectori, rezultînd un al treilea vector; dacă vectorii reprezintă
translații, atunci adunarea a două translații utilizează trei puncte;
- înmulțirea unui vector cu scalar, rezultînd un vector; intuitiv, se modifică
modulul translației reprezentate de vectorul respectiv;
- adunarea unui vector la un punct, rezultînd un punct; acest lucru realizează
translația de la punctul respectiv, translație dată de vectorul respectiv;
- scăderea a două puncte, rezultînd un vector -- chiar vectorul de translație
dintre ele.

Nu au sens, de exemplu, înmulțirea unui punct cu un scalar sau adunarea a
două puncte (pentru cea de-a doua, vezi {ref}`figura de mai sus<fig-puncte-afine>`).

Se poate defini, totuși, un fel de operație specifică de adunare între două puncte,
prin care se obține un al treilea punct, numită *combinație afină*. Date două puncte 
$ P, Q \in A.P $ și un scalar $ \alpha \in \mathbb{R} $, definim combinația lor afină
prin punctul $ R $ astfel încît:
```{math}
R = P + \alpha(Q - P).
```
De fapt, $ Q - P $ produce vectorul de translație dintre $ Q $ și $ P $, pe care îl
putem înmulți cu scalarul $ \alpha $ și producem un vector, pe care apoi îl adunăm
cu punctul $ P $, realizînd o translație de la $ P $, dată de vectorul respectiv.
De fapt, este ca și cum am aduna „fracțiuni“ de puncte, adică fracțiuni ale vectorului
de translație dintre cele două puncte:
```{figure} ./img/combinatie-afina.png
---
name: fig-comb-afin
---
Combinația afină a punctelor $ P + Q = R $
```
Abuzînd de regulile de bază ale algebrei, putem prelucra combinația afină:
```{math}
R = P + \alpha (Q - P) = P + \alpha Q - \alpha P = P(1 - \alpha) + \alpha Q,
```
deși, așa cum am precizat, nu are sens (geometric, cel puțin) înmulțirea unui punct
cu un scalar. Totuși, din expresia de mai sus se înțelege că o combinație afină
de puncte poate fi adusă la forma unei combinații liniare, cu condiția ca suma
scalarilor să fie 1.

## Transformări afine
Similar cu aplicațiile liniare, adică transformările între spații vectoriale,
putem defini și transformări afine, care să țină cont de structura suplimentară
pe care o conține un spațiu afin. Altfel spus, o astfel de transformare trebuie
să păstreze combinațiile afine. Această proprietate, însă, poate fi *dedusă*
din definiția transformărilor afine, care este ceva mai generală:

```{prf:definition}
:label: def-transf-afina

Fie $ A, B $ două spații afine, fiecare cu mulțimea sa de puncte, respectiv
de vectori specifice, $ A.P, A.V, B.P, B.V $.

Se numește *transformare afină* o corespondență $ f : A \to B $ astfel încît
aplicația indusă:

$$
  f.V : A.V \to B.V, \quad f.V(b - a) = f.V(b) - f.V(a)
$$

să fie un morfism de spații vectoriale.
```
Se poate arăta că definiția implică și relația generală:
```{math}
f(a + v) = f.P(a) + f.V(v),
```
unde am notat separat $ f.P $ acțiunea lui $ f $ pe puncte și $ f.V $ acțiunea
pe vectori.

Rezultă, în particular, că, deoarece orice punct $ b \in A.P $ este unic determinat
de un punct fixat și un vector de translație, a ști cum acționează $ f $ pe
un punct fixat arbitrar și componenta ei liniară determină unic întreaga acțiune
a lui $ f $.

De aici putem obține și faptul că $ f $ păstrează combinațiile afine,
adică:
```{math}
f \left( \sum_{i = 1}^n \alpha_i P_i \right) = \sum_{i = 1}^n \alpha_i f(P_i), \quad %
\forall \alpha_i \in \mathbb{R}, P_i \in A.P, 1 \leq i \leq n, \sum_{i = 1}^n \alpha_i = 1
```

Principalele tipuri de aplicații afine relevante în geometrie, pe care le vom studia
într-o secțiune separată, împreună cu implementările lor pe computer, sînt:
- translații;
- reflexii față de o dreaptă sau un plan fixate;
- proiecții paralele;
- rotații în jurul unui punct fixat;
- forfecare (eng. *shearing*) în raport cu drepte sau plane fixate.

## Coordonate baricentrice
În spații vectoriale, coordonatele unui vector se referă la scalarii cu care
se înmulțesc vectorii bazei pentru a obține vectorul dat sub formă de combinație
liniară. Din punct de vedere geometric, acestea se obțin ca proiecțiile
vectorului dat pe axele de coordonate, care sînt multipli ai versorilor bazei.

Însă cum în spații afine nu avem originea ca punct privilegiat din punct de
vedere geometric, va trebui să adaptăm această definiție a coordonatelor.

Fie $ A $ un spațiu afin și $ A.B = \{ v_1, v_2, \dots, v_n \} $ o bază în spațiul
vectorial subiacent, $ A.V $. Putem defini un *cadru* (*sistem de referință*)
$ A.F $ al lui $ A $ (eng. *frame*, de aceea avem notația cu $ F $) ca fiind
alcătuit dintr-un punct arbitrar $ O \in A.P $ și baza lui $ A.V $.

Evident, orice vector din $ A.V $ se descompune în cadrul $ A.F $, cu scalarul
$ 0 $ corespunzător punctului $ O $ și coordonatele sale obișnuite corespunzătoare
bazei $ A.B $.

Dar putem descompune și puncte arbitrare, folosind chiar definiția spațiilor
afine: pentru orice punct $ Q $, există un unic vector de translație de la punctul
fixat $ O $ la $ Q $, deci:
```{math}
:label: eq-desc-punct
Q = u + O = \sum_{i = 1}^n \alpha_i v_i + O.
```
Coordonatele punctului $ Q $ devin, deci, scalarii $ \alpha_i, 1 \leq i \leq n $,
iar „coordonata“ corespunzătoare punctului $ O $ se ignoră, deoarece pentru orice
punct ea ar fi mereu egală cu 1.

```{important}
Dacă folosim o bază de versori (ortonormată) pentru $ A.V $, cadrul care se obține
se numește *cartezian*.
```

---

Dar mai putem gîndi și altfel coordonatele unui punct. Relația {eq}`eq-desc-punct`
poate fi interpretată ca și cum coordonatele punctului $ Q $ sînt $ n $ *puncte*,
anume $ P_i = \alpha_i v_i + O $ și în plus, mai notăm $ P_0 = O $.

Atunci punctul $ Q $ se poate scrie:
```{math}
\begin{align*}
  Q &= P_0 \left( 1 - \sum_{i = 1}^n \alpha_i \right) + \sum_{i = 1}^n P_i \alpha_i \\
    &= \sum_{i = 0}^n P_i a_i,
\end{align*}
```
unde $ a_0 $ este definit astfel încît $ a_0 + a_1 + \dots + a_n = 1 $.
Această egalitate arată o *combinație afină*, deci rezultă că punctul $ Q $ se poate
scrie ca o combinație afină a punctelor $ P_i $ definite ca mai sus.

În acest context, scalarii $ \alpha_i, 0 \leq i \leq n $ se numesc *coordonatele baricentrice*
ale lui $ Q $ în raport cu cadrul $ A.F $.

Descrierea se poate extinde acum și la vectori. Dacă avem un vector $ u \in A.V $,
pe care îl descompunem în baza $ A.B $ sub forma:
```{math}
u = \sum_{i = 1}^n \alpha_i v_i, \quad \alpha_i \in \mathbb{R}, 1 \leq i \leq n,
```
definim similar $ \alpha_0 = -(\alpha_1 + \alpha_2 + \dots + \alpha_n) $ și, folosind
notațiile anterioare, $ P_0 = O $, apoi $ P_i = v_i + O, 1 \leq i \leq n $,
găsim:
```{math}
u = \sum_{i = 0}^n \alpha_i P_i.
```

```{important}
Punctele corespunzătoare unui cadru, $ P_i, 0 \leq i \leq n $ în notația de mai sus,
alcătuiesc un *simplex*.

Se numește $ n $-simplex unul care se definește într-un spațiu afin al cărui spațiu
vectorial subiacent are dimensiunea $ n $. De remarcat că, așa cum am văzut mai sus,
un $ n $-simplex va conține $ n + 1 $ puncte, unul dintre ele fiind „originea“,
$ P_0 = O $, în notația de mai sus.

Așadar, în general, un $ n $-simplex este alcătuit dintr-un punct distins
și translațiile care se pot obține de la punctul respectiv cu vectorii bazei
spațiului vectorial subiacent.
```

Să vedem cîteva exemple de simplexe. 

- Pentru dimensiune $ n = 1 $, spațiul vectorial
corespunzător este chiar $ \mathbb{R} $, de bază $ \{ v_1 = 1 \} $. Alegerea unui
punct distins de pe dreapta reală înseamnă să alegem un număr. Fie acesta $ O = \pi $,
de pildă. Atunci simplexul 1-dimensional conține 2 puncte: $ \{ P_0 = O = \pi, P_1 = O + v_1 = \pi + 1 \} $.
Acestea determină un segment.

- Pentru dimensiune $ n = 2 $, spațiul vectorial este planul real, $ \mathbb{R}^2 $,
de bază $ \{ v_1 = (1, 0), v_2 = (0, 1) \} $, care este chiar ortonormată.
Să alegem un punct arbitrar distins, $ O = (1, 2) $. Atunci simplexul bidimensional
conține 3 puncte: $ \{ P_0 = O(1, 2), P_1 = O + v_1 = (2,2), P_2 = O + v_2 = (1, 3) \} $.
Acestea determină un triunghi.

- Pentru dimensiune $ n = 3 $, spațiul vectorial este cubul $ \mathbb{R}^3 $.
Baza canonică (ortonormată) este $ \{ v_1 = (1, 0, 0), v_2 = (0, 1, 0), v_3 = (0, 0, 1) \} $.
Fie un punct oarecare fixat, $ O = (-1, 2, 0) $. Simplexul tridimensional conține 4 puncte:
```{math}
\{ P_0 = O(-1, 2, 0), P_1 = O + v_1 = (0, 2, 0), P_2 = O + v_2 = (-1, 3, 0), P_3 = O + v_3 = (-1, 2, 1) \}
```
Aceste puncte determină un tetraedru, adică o piramidă triunghiulară.

```{note}
Simplexele se întîlnesc în așa-numită problemă a *triangulării*, prin care se descompune
un spațiu în „triunghiuri“, într-un sens ceva mai general, nu neapărat vizual.

Aplicații în grafica pe computer includ imagini precum cea de mai jos, care arată că
alegerea unor triunghiuri tot mai mici produce o acuratețe mai mare în descompunerea
unei figuri tridimensionale complexe.
```
```{figure} ./img/triangulare-fata.png
---
name: fig-triangulare-fata
---
Triangularea unei figuri cu forme tot mai mici crește acuratețea
```
