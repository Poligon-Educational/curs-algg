# Bază și dimensiune
## Intuiție
*Baza* unui spațiu vectorial este, într-un fel, „esența“ acestuia, așa cum
arată și numele. Intuitiv, lucrurile sînt deja cunoscute, mai ales dacă
vom detalia cele două componente care alcătuiesc o bază: sistemul liniar
independent și sistemul de generatori.

Dar să rămînem puțin la noțiunea de bază și să ne întoarcem la cazul
{ref}`vectorilor din plan<sec-intuitie-spvect>`. Am spus că preferăm să
lucrăm cu vectorii descompuși în funcție de *versorii* $ \vec{i} $ și
$ \vec{j} $, știind că putem face asta pentru *orice* vector din plan.
Cu alte cuvinte, indiferent de vectorul ales $ \vec{v} $, cu siguranță
există două numere reale (scalari, cum știm acum că se numesc) 
$ \alpha, \beta \in \mathbb{R} $ astfel încît vectorul $ \vec{v} $ 
să se scrie ca o *combinație liniară* a acestor vectori speciali 
$ \vec{i} $ și $ \vec{j} $:
```{math}
\vec{v} = \alpha \vec{i} + \beta \vec{j}.
```
Mai mult decît atît, o astfel de descompunere este *unică*, adică nu se poate
să folosim alți scalari decît aceștia pentru a obține același vector.
Altfel spus, egalitatea de mai jos este posibilă doar dacă scalarii sînt
identici ($\alpha = \gamma$ și $ \beta = \delta $):
```{math}
\vec{v} = \alpha \vec{i} + \beta \vec{j} = \gamma \vec{i} + \delta \vec{k}.
```

Aceasta este exact esența bazei:
```{important}
O *bază* a unui spațiu vectorial conține vectorii în funcție de care se pot scrie
*în mod unic* toți vectorii spațiului.
```

Iar noțiunea de *dimensiune* oferă o caracterizare numerică a acestei situații:
este numărul de vectori din bază.

---

Puteam face această introducere și altfel. Vă propunem următoarea întrebare:
Cum ați explica afirmațiile binecunoscute precum cea că linia este 1-dimensională,
planul este bidimensional și un cub, de pildă, este tridimensional?
Gîndiți-vă la propriile răspunsuri, apoi citiți mai departe.

O posibilitate de a explica lucrurile este aceasta: figurile menționate se caracterizează
prin cîte una, respectiv două sau trei trăsături:
- linia are o lungime, dar nu are lățime sau altă caracteristică;
- planul „se întinde“ pe lungime și lățime;
- cubul are lungime, lățime și înălțime.

Sau, dacă ar fi să facem lucrurile și mai abstracte, am spune:
- linia (dreapta) poate reprezenta axa numerelor reale, unde fiecare punct se caracterizează
printr-o singură componentă: valoarea sa. Punctele corespunzătoare numerelor reale $ \pi $
sau $ \sqrt{2} $ sînt complet caracterizate doar de aceste valori;
- planul corespunde sistemului de coordonate $ XOY $, unde fiecare punct este caracterizat
de cîte două informații: abscisa și ordonata sa, $ P(x_P, y_P) $;
- cubul poate fi gîndit ca o versiune mărginită a sistemului de coordonate $ Oxyz $, unde
fiecare punct se caracterizează prin 3 informații: $ P(x_P, y_P, z_P) $.

Mai mult, în ambele caracterizări se adaugă o trăsătură de *unicitate*: punctele
de pe dreaptă, din plan sau dintr-un cub nu pot fi scrise în mai multe moduri, cu informații
diferite. În plan, nu putem avea, de pildă $ P(x_P, y_P) = (x'_P, y'_{P}) $
pentru un același punct $ P $, cu $ x_P \neq x'_P $ și $ y_P \neq y'_{P} $.

Oricare ar fi răspunsul la care v-ați gîndit, cele două direcții de raționament
de mai sus conțin exact informația principală:
```{important}
Dimensiunea este numărul de componente (informații) de care avem nevoie pentru a caracteriza
unic și complet orice obiect (vector) din spațiu.
```

Ieșind în afara matematicii, am putea spune că „spațiul“ oamenilor din România este 1-dimensional:
orice persoană este unic și complet caracterizată de CNP.

--- 

Vom vedea că o astfel de perspectivă nu este doar corectă, dar oferă și un grad de
„dezvrăjire“ în ce privește așa-numitele *spații cu mai multe dimensiuni* (chiar o infinitate).
În esență, un spațiu de dimensiune $ n $ este unul în care, pentru a ști precis despre
ce obiect este vorba, avem nevoie de exact $ n $ informații.

```{note}
Nu am adăugat explicit în remarcile de mai sus, dar ar trebui să fie clar că informațiile
pe care le cerem pentru a preciza un obiect din spațiu trebuie să fie și *independente*.

De pildă, dacă am cere CNP-ul și data nașterii unei persoane, am avea o redundanță,
pentru că cele două informații nu sînt idependente: dat CNP-ul, se poate deduce data nașterii.

Similar, în plan, de exemplu, nu este nevoie să precizăm și perechea (abscisă, ordonată)
și distanța față de origine, pentru că informațiile nu sînt independente.
```

Mergem acum la definițiile riguroase, unde va fi foarte util să ținem cont de această
caracterizare intuitivă, deoarece lucrurile nu vor fi mereu transparente, la prima vedere.

## Definiții formale -- Independență liniară
Baza unui spațiu vectorial este o mulțime de vectori cu două trăsături importante. De obicei,
acestea se prezintă separat, deoarece pot caracteriza și individual o mulțime de vectori.

```{prf:definition}
:label: def-indep
Fie $ V $ un $ K $-spațiu vectorial și $ S = \{ x_1, x_2, \dots, x_n \} $ o mulțime de vectori
din $ V $.

Spunem că $ S $ este un *sistem liniar independent* (sau, mai simplu, că mulțimea $ S $ este
independentă sau liberă) dacă orice combinație liniară nulă a vectorilor din $ S $ cu scalari
din $ K $ este trivială. În simboluri, pentru $ \alpha_i \in K, 1 \leq i \leq n $:

$$
  \alpha_1 x_1 + \alpha_2 x_2 + \dots + \alpha_n x_n = 0 \Rightarrow \alpha_1 = \alpha_2 = \dots = \alpha_n = 0.
$$

Cu alte cuvinte, nu putem obține vectorul nul din vectorii din $ S $ decît în varianta trivială,
anume cînd toți scalarii sînt nuli.
```

```{note}
Cum înmulțirea unui vector cu scalari produce un vector, rezultă că în definiție,
combinația liniară $ \displaystyle\sum_{1 \leq i \leq n} \alpha_i x_i = 0 $
are drept rezultat *vectorul* nul, $ 0_V $.
```

Prin negarea acestei definiții, obținem noțiunea de *sistem liniar dependent*. În acest caz,
păstrînd notațiile anterioare, există scalarii $ \alpha_1, \alpha_2, \dots, \alpha_n $,
*nu toți nuli*, astfel încît să avem o combinație liniară nulă cu vectorii din $ S $:
```{math}
\alpha_1 x_1 + \alpha_2 x_2 + \dots + \alpha_n x_n = 0.
```

```{note}
Ar trebui să fie clar, dar notăm, totuși, faptul că $ S $ nu trebuie să fie *subspațiu* al lui $ V $.
Este pur și simplu o mulțime, o selecție de vectori. De asemenea, dacă în definiția formală
am scris că $ S $ ar conține $ n $ vectori, adică un număr finit, precizăm, totuși, că este
permis și ca $ S $ să fie infinită. Însă în exerciții și în secțiunile pe care le vom
prezenta în continuare vom lucra doar cu mulțimi finite.
```

---

### Explicație intuitivă
Acum, facem o pauză de apel la intuiție. Dacă întîlniți într-un context oarecare o expresie
precum *Variabilele (cantitățile) $ x, y, z $ sînt independente*, la ce vă gîndiți?

În general, o astfel de expresie este înțeleasă prin faptul că nu putem obține niciuna dintre
cele 3 variabile (cantități) în funcție de celelalte. Cu alte cuvinte, pentru scopul pentru
care le-am obținut, cu siguranță avem nevoie de toate 3.

Iată cum se leagă această înțelegere intuitivă de definiția -- aparent opacă -- de mai sus.

Să presupunem că variabilele $ x, y, z $ sînt *dependente*, adică putem, totuși, să scriem
una dintre ele în funcție de celelalte două, de pildă. Să zicem că avem o relație de forma:
```{math}
x = 3y - 2z.
```
Vom arăta că, pornind de la aceasta, putem ajunge la definiția formală de mai sus a dependenței
liniare. Avem succesiv:
```{math}
x = 3y - 2z \Leftrightarrow x - 3y + 2z = 0.
```
Rezultă că am obținut o combinație liniară a celor 3 variabile (vectori) $ \{ x, y, z \} $,
cu scalari reali în cazul acesta, combinație liniară care este nulă. Însă în mod evident, nu toți
scalarii sînt nuli. De fapt, preluînd notațiile din definiție, avem 
$ \alpha_1 = 1, \alpha_2 = -3, \alpha_3 = 2 $. Or acest lucru este exact definiția dependenței liniare:
avem o combinație liniară care folosește vectorii în cauză, combinație care este nulă, fără ca
(toți) scalarii să fie nuli.

Independența neagă acest lucru, deci face imposibilă obținerea oricărei relații de forma
$ x = ay + bz $ sau altele, cu scalari (coeficienți) nenuli.

---

### Exemple și calcul
Acum să vedem cum am demonstra concret că o anume mulțime de vectori este liniar (in)dependentă.

**Exemplu:** Fie spațiul vectorial real $ V = \mathbb{R}^3 $ și mulțimea de vectori:
```{math}
S = \{ v_1 = (-1, 2, 0), v_2 = (2, 0, 1) \}.
```
Să vedem dacă $ S $ este independentă.

Aplicăm definiția: presupunem că am reușit să obținem o combinație liniară nulă, care folosește
vectorii din $ S $ și scalarii reali $ \alpha, \beta $, adică:
```{math}
\alpha v_1 + \beta v_2 = (-\alpha, 2\alpha, 0) + (2\beta, 0, \beta) = (-\alpha + 2\beta, 2\alpha, \beta) = 0 = (0, 0, 0).
```
Dar egalitatea a doi vectori nu se poate realiza decît dacă cei doi vectori coincid pe componente,
deci ajungem la:
```{math}
\begin{cases}
  -\alpha + 2\beta &= 0 \\
  2\alpha &= 0 \\
  \beta &= 0
\end{cases}
```
Acest sistem de ecuații are evident soluția nulă, $ \alpha = \beta = 0 $, deci am demonstrat
că o combinație liniară a vectorilor din $ S $ cu scalari reali nu poate fi nulă decît
în cazul trivial. Concluzia este că sistemul $ S $ este independent.

**Exemplu:** Folosim acum spațiul vectorial $ V = \mathbb{R}^2 $ și fie mulțimea de vectori:
```{math}
S = \{ v_1 = (-1, 2), v_2 = (3, 1), v_3 = (0, 5), v_4 = (2, -1) \}.
```
Să verificăm dacă $ S $ ar putea fi independentă. Lucrăm tot cu definiția, deci presupunem că
avem o combinație liniară nulă care folosește scalarii $ \alpha_{1,2,3,4} $ și cei 4 vectori
din $ S $:
```{math}
\alpha_1 v_1 + \alpha_2 v_2 + \alpha_3 v_3 + \alpha_4 v_4 = \dots = %
(-\alpha_1 + 3\alpha_2 + 2\alpha_4, 2\alpha_1 + \alpha_2 + 5\alpha_3 - \alpha_4) = (0, 0).
```
Ca mai devreme, sîntem conduși la sistemul:
```{math}
\begin{cases}
  -\alpha_1 + 3\alpha_2 + 2\alpha_4  &= 0 \\
  2\alpha_1 + \alpha_2 + 5\alpha_3 - \alpha_4 &= 0
\end{cases}
```
Cum acesta este un sistem de 2 ecuații cu 4 necunoscute, rezultă că el este compatibil
dublu nedeterminat. Deci cu siguranță are și soluții nenule, pe care le putem obține,
de pildă, considerînd necunoscutele secundare $ \alpha_3 $ și $ \alpha_4 $.

Concluzia este că putem obține o combinație liniară a vectorilor din $ S $ cu scalari
care să nu fie toți nuli, dar rezultatul să fie vectorul nul. Așadar, mulțimea $ S $
este *dependentă*.

**Exemplu:** Să luăm acum din nou $ V = \mathbb{R}^3 $ și sistemul:
```{math}
S = \{ v_1 = (-1, 2, 0), v_2 = (1, 1, 1), v_3 = (0, 3, 1) \}.
```

Studiem independența ca pînă acum. Presupunem că avem scalarii $ \alpha, \beta, \gamma \in \mathbb{R} $
astfel încît:
```{math}
\alpha v_1 + \beta v_2 + \gamma v_3 = \dots = (-\alpha + \beta, 2\alpha + \beta + 3 \gamma, \beta + \gamma) = (0, 0, 0)
```
și ajungem la:
```{math}
\begin{cases}
  -\alpha + \beta &= 0 \\
  2\alpha + \beta + 3\gamma &= 0 \\
  \beta + \gamma &= 0
\end{cases}
```
Fiind vorba despre un sistem de 3 ecuații cu 3 necunoscute, să încercăm o abordare matriceală.
Construim matricea sistemului:
```{math}
A = \begin{pmatrix}
  -1 & 1 & 0 \\
  2 & 1 & 3 \\
  0 & 1 & 1
\end{pmatrix}
```
și calculăm $ \det(A) = 0 $. Rezultă că sistemul nu este Cramer, deci nu are soluție unică
și, fiind omogen, rezultă că admite și soluții nenule. Așadar, pot exista scalari nenuli
$ \alpha, \beta, \gamma $ care să conducă la o combinație liniară nulă. În concluzie,
$ S $ este *dependentă*.

---
### Observație tehnică

Să analizăm mai atent acest exemplu și în special, metoda matriceală folosită.
Motivul pentru care $ \det(A) = 0 $ este că a treia coloană a matricei este suma
primelor două coloane. Ce constatați, însă, privitor la această matrice? O privire
atentă arată că vectorii $ v_1, v_2, v_3 $ sînt tocmai coloanele matricei!
Așadar, observația legăturii între coloane pe care am făcut-o înseamnă, de fapt,
o legătură între vectorii din $ S $: $ v_3 = v_1 + v_2 $.

Aceasta este o legătură foarte importantă între metodele matriceale și cele specifice
spațiilor vectoriale. Vedem, de fapt, o aplicație directă a proprietăților determinanților.

Și chiar mai mult, analizînd exemplul din $ \mathbb{R}^2 $, vedem că, dacă am scrie
matricea sistemului respectiv pentru $ \alpha_{1,2,3,4} $, am obține o matrice de rang
maximum 2. Aceasta înseamnă că cel mult 2 coloane sînt independente, iar cum coloanele
sînt tocmai vectorii din $ S $, rezultă că rangul matricei ne dă numărul maxim de vectori
independenți!

În exercițiile ulterioare, putem folosi aceste informații direct, pe care le colectăm mai jos:

```{important}
Rangul matricei care se obține aranjînd vectorii din $ S $ *pe coloane* este numărul
de vectori independenți din $ S $. Mai mult, minorul care dă rangul ne arată și care
sînt acești vectori independenți.
```
---

### Alte exemple
Ce facem, însă, dacă nu lucrăm cu spații de forma $ \mathbb{R}^n $, pentru a scrie direct
matricea care conține vectorii din $ S $ pe coloane? După ce vom studia (izo)morfismele
de spații vectoriale, răspunsul la această întrebare va fi imediat. Deocamdată, însă,
continuăm cu astfel de exemple, pe care le rezolvăm cu definiția, fiind, totuși, atenți
și la legătura cu metodele matriceale menționate anterior.

**Exemplu:** Fie spațiul $ V = M_2(\mathbb{R}) $ și mulțimea de vectori:
```{math}
S = \left\{ A = \begin{pmatrix} 1 & -1 \\ 0 & 2 \end{pmatrix}, %
            B = \begin{pmatrix} 2 & 0 \\ -1 & 1 \end{pmatrix}, %
            C = \begin{pmatrix} 0 & 1 \\ 1 & 1 \end{pmatrix} \right\}
```
Studiem independența lui $ S $. Presupunem că avem scalarii $ \alpha, \beta, \gamma \in \mathbb{R} $
astfel încît:
```{math}
\alpha A + \beta B + \gamma C = \dots = % 
\begin{pmatrix}
\alpha + 2 \beta & -\alpha + \gamma \\
-\beta + \gamma & 2\alpha + \beta + \gamma
\end{pmatrix} = 0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}
```
Ajungem la sistemul:
```{math}
\begin{cases}
  \alpha + 2\beta &= 0 \\\
  -\alpha + \gamma &= 0 \\
  -\beta + \gamma &= 0 \\
  2\alpha + \beta + \gamma &= 0
\end{cases}.
```
Cum acesta este un sistem omogen cu 3 necunoscute și 4 ecuații, va fi compatibil. Scriem matricea
sistemului, pentru a-i calcula rangul (de unde vom deduce dacă este Cramer sau nedeterminat):
```{math}
M = \begin{pmatrix}
1 & 2 & 0 \\
-1 & 0 & 1 \\
0 & -1 & 1 \\
2 & 1 & 1
\end{pmatrix}
```
Observăm că $ \mathrm{rang}(M) = 3 $ și putem neglija, de exemplu, a treia ecuație.
Cum rangul este maxim, rezultă că sistemul este Cramer și, cum este omogen, rezultă că are
doar soluția nulă $ \alpha = \beta = \gamma = 0 $. Așadar, $ S $ este independent.

Dacă vrem, totuși, să înțelegem soluția folosind o metodă matriceală, trebuie doar
să fim atenți la construcția matricei $ M $ în funcție de matricele $ A, B, C $.
Vom vedea că aceasta este obținută ca și cum am „desfășura“ cele trei matrice
sau, altfel spus, ca și cum le-am considera matrice-coloană, de exemplu:
```{math}
A = \begin{pmatrix}
1 & -1 \\ 0 & 2
\end{pmatrix} \mapsto %
\begin{pmatrix}
1 \\ -1 \\ 0 \\ 2
\end{pmatrix}
```
și similar cu celelalte.

Există și o explicație riguroasă în acest sens, pe care o vom da de îndată ce lămurim
definiția formală a bazei.

**Exemplu:** Fie acum $ V = \mathbb{R}_2[X] $ și mulțimea de vectori:
```{math}
S = \{ p_1 = 1 - X, p_2 = 3, p_3 = 2 + X - X^2 \}
```
Verificăm independența liniară cu definiția. Presupunem că avem scalarii reali
$ \alpha_{1,2,3} $ astfel încît:
```{math}
\alpha_1 p_1 + \alpha_2 p_2 + \alpha_3 p_3 = \dots = %
\alpha_1 + 3\alpha_2 + 2\alpha_3 + (-\alpha_1 + \alpha_3) X + (-\alpha_3)X^2 = 0 = %
0 + 0 \cdot X + 0 \cdot X^2.
```
Rezultă:
```{math}
\begin{cases}
  \alpha_1 + 3\alpha_2 + 2\alpha_3 &= 0 \\
  -\alpha_1 + \alpha_3 &= 0 \\
  -\alpha_3 &= 0
\end{cases}
```
Rezolvînd sistemul de la a treia ecuație în sus, ajungem imediat la soluția
trivială $ \alpha_1 = \alpha_2 = \alpha_3 = 0 $, deci $ S $ este independent.

Dacă am scrie matricea sistemului de ecuații, am avea:
```{math}
A = \begin{pmatrix}
  1 & 3 & 2 \\
  -1 & 0 & 1 \\
  0 & 0 & -1
  \end{pmatrix}.
```
Se vede că pe coloanele matricei $ A $ avem coeficienții polinoamelor:
coloana $ (1, -1, 0) $ corespunde polinomului $ p_1 = 1 + (-1) \cdot X + 0 \cdot X^2 $
și celelalte. Desigur, situația nu este accidentală și o vom detalia riguros
odată cu definiția bazei.

## Definiții formale -- Sistem de generatori
A doua componentă de care avem nevoie pentru a defini o bază este *sistemul de generatori*.
Începem cu definiția formală, apoi cîteva explicații intuitive.

```{prf:definition}
:label: def-sist-gen
Fie $ V $ un $ K $-spațiu vectorial și $ S = \{ x_1, x_2, \dots x_n \} $ 
o mulțime de vectori din $ V $.

Spunem că $ S $ este un *sistem de generatori* pentru $ V $ și notăm aceasta
cu $ \langle S \rangle = V $ sau $ V = \mathrm{Sp}(S) $[^span] dacă orice
vector din $ V $ poate fi scris ca o combinație liniară de vectori din $ S $
cu scalari din $ K $.

În simboluri:

$$
  \forall v \in V, \exists \alpha_i \in K, 1 \leq i \leq n, v = \sum_{1 \leq i \leq n} \alpha_i x_i.
$$
```

[^span]: Notația $ \mathrm{Sp}(S) $ provine de la denumirea în engleză, *span*.
De fapt, și în română, vectorii obținuți ca o combinație liniară a unora dintr-o
mulțime fixată poartă numele de *acoperirea liniară* a mulțimii respective.
În cazul sistemului de generatori, deci, spațiul întreg este acoperirea liniară
a sistemului. Iar notația $ \langle S \rangle = V $ este folosită în mai multe contexte
pentru a arăta generatorii. De pildă, putem scrie $ \langle 1 \rangle = \mathbb{Z} $
dacă ne referim la grupul aditiv al numerelor întregi, deoarece orice număr întreg
poate fi obținut din 1, cu adunări (și scăderi).

---

### Explicație intuitivă
Cînd ne gîndim, în sens general, la un *generator* pentru un proces, un obiect sau o mulțime
anume, avem în minte un element sau un obiect din care se pot obține toate celelalte elemente
sau obiecte, folosind doar niște „reguli interne“, ca să ne exprimăm vag.

De exemplu, un generator de curent electric este un obiect care produce (în principiu, oricît)
curent electric, folosind regulile fizicii.

În algebră, regulile pe care le folosim sînt impuse de operațiile utilizate. De pildă,
orice număr întreg poate fi obținut din 1, cu adunări (și scăderi). Rezultă că 1 este un generator
pentru întreaga mulțime $ \mathbb{Z} $. În cazul înmulțirii, am putea spune că 2 *generează*
toată mulțimea de puteri ale sale, $ \{\dots, \dfrac{1}{4}, \dfrac{1}{2}, 1, 2, 4, \dots \} $.

În cazul spațiilor vectoriale, avem mai multe operații. Dar, așa cum am precizat, putem gîndi
că toate sînt concentrate în *combinații liniare*. Altfel spus, atunci cînd ne gîndim la a genera
unul sau mai mulți vectori dintr-o mulțime fixată de vectori, avem în vedere o combinație liniară
a vectorilor-generatori, din care obținem vectorii doriți. „Regula jocului“, așadar, este
*combinația liniară*.

De aceea, definiția ar trebui să fie clară: spunem că o mulțime fixată de vectori $ S $ generează
(sau, echivalent, vectorii din $ S $ sînt generatori pentru) întreg spațiul $ V $ dacă, folosind
numai „regulile jocului“ -- adică combinațiile liniare cu scalari -- putem obține orice vector din $ V $.

Evident, definiția are sens și într-un context mai puțin general: ne putem gîndi și la cazuri cînd
o mulțime $ S $ generează doar un subspațiu al spațiului studiat. Și, într-adevăr, aceasta este
o metodă simplă de a obține noi spații: se iau mulțimi arbitrare de vectori și li se calculează
*acoperirea liniară*, adică mulțimea tuturor combinațiilor liniare care folosesc vectorii respectivi
și scalari. Rezultatul este un subspațiu al spațiului inițial. Profităm de ocazie și vă invităm
să completați cu detaliile riguroase, rezolvînd exercițiul de mai jos.

**Exercițiu:** Fie $ V $ un $ K $-spațiu vectorial și $ S = \{ x_1, x_2, \dots, x_n \} $ o mulțime
de vectori. Arătați că acoperirea liniară a lui $ S $, adică mulțimea:
```{math}
\langle S \rangle = \left\{ \displaystyle\sum_{1 \leq i \leq n} \alpha_i x_i \mid \alpha_i \in K, 1 \leq i \leq n \right\}
```
este un subspațiu al lui $ V $.

Puteți începe chiar cu condiția necesară: este adevărat că $ 0_V \in \langle S \rangle $?

---

### Exemple și calcul
În continuare, cîteva exemple rezolvate pentru a demonstra că o mulțime de vectori este
un sistem de generatori pentru un spațiu vectorial.

**Exemplu:** Fie spațiul vectorial $ V = \mathbb{R}^3 $ și mulțimea de vectori:
```{math}
S = \{ v_1 = (-1, 1, 1), v_2 = (1, 0, 2), v_3 = (0, 1, -1) \}.
```
Verificăm dacă $ S $ este sistem de generatori, cu definiția.
Pentru aceasta, alegem un vector *arbitrar* $ v = (a, b, c) \in V $ și vrem să vedem
dacă el poate fi obținut din vectorii din $ S $. Ar trebui să existe scalarii
$ \alpha_{1,2,3} \in \mathbb{R} $ astfel încît:
```{math}
v = (a, b, c) = \alpha_1 v_1 + \alpha_2 v_2 + \alpha_3 v_3 = \dots = %
(-\alpha_1 + \alpha_2, \alpha_1 + \alpha_3, \alpha_1 + 2\alpha_2 - \alpha_3).
```
Ajungem la sistemul:
```{math}
\begin{cases}
  -\alpha_1 + \alpha_2 &= a \\
  \alpha_1 + \alpha_3 &= b \\
  \alpha_1 + 2\alpha_2 - \alpha_3 &= c
\end{cases}.
```
La prima vedere, sistemul arată intimidant, deoarece lasă impresia că are 3 ecuații
și 6 necunoscute. Însă această observație este falsă, deoarece, dacă citim cu atenție
procesul prin care am ajuns aici, vedem că vectorul $ v $ a fost *ales* (arbitrar),
deci îl putem presupune cunoscut. Ceea ce căutăm în demonstrație sînt doar scalarii
$ \alpha_{1,2,3} $, deci acestea sînt necunoscutele sistemului. 

Mai mult decît atît, în principiu, a arăta că $ S $ este sistem de generatori nu înseamnă
neapărat să și găsim scalarii -- ci doar să arătăm că ei există, adică *ar putea fi* găsiți.
Cu alte cuvinte, trebuie să arătăm că sistemul de ecuații de mai sus are soluție, i.e. este
compatibil.

Conform cunoștințelor din liceu, acest lucru este echivalent cu a arăta că
rangul matricei sistemului este egal cu rangul matricei extinse. În cazul nostru, matricea
sistemului fiind:
```{math}
A = \begin{pmatrix}
-1 & 2 & 0 \\
1 & 0 & 3 \\
1 & 2 & -1
\end{pmatrix},
```
rezultă că dacă $ \mathrm{rang}(A) = 3 $, atunci am terminat, deoarece indiferent de valorile
$ a, b, c $, matricea extinsă nu poate avea rangul 4. Acest lucru este echivalent cu a arăta
că $ \det(A) \neq 0 $ și, într-adevăr, avem $ \det(A) = 14 $, deci avem concluzia.

Evident, dacă vrem neapărat, putem rezolva efectiv sistemul și să găsim scalarii în funcție
de $ a, b, c $, adică să știm cum îi găsim în funcție de componentele unui vector. Dar în general,
definiția sistemului de generatori ne spune că este suficient să arătăm că *există* acești scalari,
indiferent de vectorul ales.

**Exemplu:** Fie acum același spațiu vectorial, $ V = \mathbb{R}^3 $ și mulțimea de vectori:
```{math}
S = \{ v_1 = (-1, 1, 1), v_2 = (3, 2, 1) \}.
```
Pentru ca $ S $ să fie sistem de generatori, ar trebui să existe scalarii $ \alpha_{1,2} $ astfel
încît pentru orice vector $ v = (a, b, c) \in \mathbb{R}^3 $ să avem:
```{math}
v = (a, b, c) = \alpha_1 v_1 + \alpha_2 v_2 = \dots = (-\alpha_1 + 3\alpha_2, \alpha_1 + 2\alpha_2, \alpha_1 + \alpha_2).
```
Ajungem la sistemul:
```{math}
\begin{cases}
  -\alpha_1 + 3\alpha_2 &= a \\
  \alpha_1 + 2\alpha_2 &= b \\
  \alpha_1 + \alpha_2 &= c
\end{cases}
```
a cărui matrice este $ A = \begin{pmatrix} -1 & 3 \\ 1 & 2 \\ 1 & 1 \end{pmatrix} $.

În acest caz, nu mai este la fel de clară compatibilitatea sistemului. Aceasta deoarece, deși $ \mathrm{rang}(A) = 2 $,
este posibil ca $ \mathrm{rang}(\overline{A}) = 3 $, unde matricea extinsă este:
```{math}
\overline{A} = \begin{pmatrix}
-1 & 3 & a \\
1 & 2 & b \\
1 & 1 & c
\end{pmatrix}.
```
Totul se datorează arbitrarului coloanei $ (a, b, c) $, care este tocmai vectorul $ v $. Cu alte cuvinte,
putem găsi cel puțin un triplet $ (a, b, c) $ care să facă $ \det(\overline{A}) \neq 0 $, adică $ \mathrm{rang}(\overline{A}) = 3 $,
ceea ce ar face sistemul incompatibil.

În particular, rezultă că acei vectori care fac sistemul incompatibil -- adică acele valori pentru tripletele
$ (a, b, c) $ pentru care $ \det(\overline{A}) \neq 0 $ -- sînt tocmai vectorii care *nu* se pot obține din $ S $,
i.e. care nu se găsesc în acoperirea sa liniară.

---

### Observație tehnică
Ca să nu mai lungim lucrurile și fiindcă avem deja experiența situației sistemului liniar
independent, facem următoarea observație privitoare la metode matriceale pentru sisteme
de generatori.

Putem observa, ca și în cazul sistemelor liniar independente, că matricea sistemului
de ecuații la care se ajunge se alcătuiește și de data aceasta din vectorii din mulțime,
puși pe coloane.

Cum scopul este să arătăm că sistemul la care ajungem are soluție -- adică există scalarii
căutați, cu ajutorul cărora se poate obține orice vector din spațiu -- rezultă că problema
se reduce la a demonstra compatibilitatea sistemului respectiv de ecuații. Aceasta, la rîndul
ei, este echivalentă cu a arăta că rangul matricei sistemului este egal cu rangul matricei
extinse. Dar:
- matricea sistemului conține vectorii din (posibilul) sistem de generatori, pe coloane;
- matricea extinsă adaugă coloana termenilor liberi, adică o *coloană arbitrară*, corespunzătoare
unui vector oarecare, de obținut din generatori.

De aceea, pentru a fi siguri că sistemul este compatibil, trebuie să impunem ca 
numărul de ecuații să fie *cel mult* egal cu numărul de necunoscute. Altfel spus, numărul
de componente ale vectorilor să fie mai mic sau egal cu numărul de vectori din mulțimea
(posibil) sistem de generatori.

Puteți vedea acest lucru ilustrat chiar în exemplele de mai sus. Dar pentru claritate,
reluăm simplu (și vă invităm să vă construiți exemple de lucru pentru a vă convinge):

- Dacă am avea, de pildă, în $ V = \mathbb{R}^3 $, o mulțime $ S $ care conține 2 vectori
(cu cîte 3 componente fiecare), am ajunge la un sistem de 2 ecuații cu 3 necunoscute.
Sistemul cu siguranță va fi compatibil, deoarece matricea sistemului va avea 2 linii
și 3 coloane. Rangul ei va fi cel mult 2, iar adăugarea unei coloane pentru a obține
matricea extinsă nu poate conduce la un rang al matricei extinse diferit de 2.
Rezultă că în acest caz, cu siguranță vom avea soluție, deci $ S $ va fi sistem de generatori.
- Dacă avem în $ V = \mathbb{R}^7 $ o mulțime $ S $ cu 5 vectori (cu cîte 7 componente
fiecare), am ajunge la un sistem de 7 ecuații cu 5 necunoscute. Matricea sistemului
va avea 7 linii și 5 coloane. Rangul maxim al matricei sistemului va fi 5. Dar, adăugînd
coloana termenilor liberi, obținem o matrice cu 7 linii și 6 coloane, al cărei rang maxim
poate fi 6. Și, de fapt, dat fiind arbitrarul coloanei termenilor liberi (provenind din
componentele unui vector oarecare $ v \in V $, cu siguranță găsim un astfel de vector
care să dea un rang mai mare pentru matricea extinsă. Concluzia este că, în acest caz,
sistemul *sigur* nu este compatibil, deci mulțimea nu poate fi sistem de generatori.
- Dacă în $ V = \mathbb{R}^4 $ avem o mulțime $ S $ cu 4 vectori (cu 4 componente fiecare),
ajungem la un sistem cu 4 ecuații și 4 necunoscute. Aici rangul matricei sistemului
(care va fi din $ M_4(\mathbb{R}) $) este cel mult 4. Pentru a ne asigura că sistemul
este compatibil, trebuie să cerem ca rangul să fie maxim -- adică 4. Altfel, dacă,
de exemplu, rangul ar fi 3, cu siguranță există un vector $ v = (a, b, c, d) \in V $
care să facă rangul matricei extinse 4, iar sistemul să devină incompatibil.

Astfel de observații și exemple vor simplifica demonstrațiile ulterioare.
Ne întoarcem și mai oferim cîteva exemple din afara spațiilor de tipul $ \mathbb{R}^n $.

---

### Alte exemple
Probabil intuiți cum vor funcționa lucrurile în cazul spațiilor de matrice
și de polinoame, astfel că exemplele de mai jos ar trebui să fie clare.

**Exemplu:** Fie spațiul $ V = M_2(\mathbb{R}) $ și mulțimea:
```{math}
S = \left\{ A = \begin{pmatrix} 1 & -1 & 0 & 0 \end{pmatrix}, %
            B = \begin{pmatrix} 2 & 0 & 0 & 2 \end{pmatrix}, %
            C = \begin{pmatrix} 1 & -1 & 2 & 1 \end{pmatrix}
    \right\}
```
Pentru a arăta că $ S $ este sistem de generatori, fie un vector
arbitrar $ M = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in V $.
Căutăm scalarii $ \alpha, \beta, \gamma \in \mathbb{R} $ astfel încît:
```{math}
M = \begin{pmatrix} a & b \\ c & d \end{pmatrix} - %
    \alpha A + \beta B + \gamma C = \dots = %
    \begin{pmatrix}
      \alpha + 2\beta + \gamma & -\alpha - \gamma \\
      2\gamma & 2\beta + \gamma
    \end{pmatrix}
```
Rezultă sistemul:
```{math}
\begin{cases}
  \alpha + 2\beta + \gamma &= a \\
  -\alpha - \gamma &= b \\
  2\gamma &= c \\
  2\beta + \gamma &= d
\end{cases}
```

Am putea și să încercăm să-l rezolvăm, însă vom face observația că are 4 ecuații și
3 necunoscute, deci o matrice a sistemului cu 3 coloane și 4 linii.
Rangul acesteia va fi cel mult 3. Dar matricea extinsă adaugă o coloană
(arbitrară $ (a, b, c, d) $), ceea ce face posibil ca rangul acesteia să fie 4.
Concluzia este că sistemul este incompatibil, deci $ S $ nu este sistem de generatori.

**Exemplu:** Fie spațiul $ V = \mathbb{R}_2[X] $ și mulțimea:
```{math}
S = \{ p_1 = X, p_2 = 1 - 3X, p_3 = 5X^2, p_4 = 2 + 7X^2 \}
```
Căutăm scalarii $ \alpha_{1,2,3,4} \in \mathbb{R} $ astfel încît pentru orice
vector (polinom) $ v = a + bX + cX^2 \in V $ să avem:
```{math}
v = a + bX + cX^2 = \alpha_1 p_1 + \alpha_2 p_2 + \alpha_3 p_3 + \alpha_4 p_4 = \dots = %
(\alpha_2 + 2\alpha_4) + (\alpha_1 - 3\alpha_2)X + (5\alpha_3 + 7\alpha_4) X^2.
```
Ajungem la sistemul:
```{math}
\begin{cases}
  \alpha_2 + 2\alpha_4 &= a \\
  \alpha_1 - 3\alpha_2 &= b \\
  5\alpha_3 + 7\alpha_4 &= c
\end{cases}.
```
Cum sistemul are 3 ecuații și 4 necunoscute, el va avea o matrice asociată cu 3 linii și 4 coloane.
Rangul maxim al acesteia va fi 3, care se și obține (verificați!). Rezultă că adăugarea coloanei
$ (a, b, c) $ nu poate face ca rangul matricei extinse să fie diferit, așadar sistemul
este compatibil, deci $ S $ este sistem de generatori.

## Definiții formale -- Bază și dimensiune
Am ajuns, în fine, la definiția principală.

```{prf:definition}
:label: def-baza-dim

Fie $ V $ un $ K $-spațiu vectorial și $ S = \{ x_1, x_2, \dots, x_n \} $
o mulțime de vectori din $ V $.

Spunem că $ S $ este *bază* a lui $ V $ dacă $ S $ este simultan sistem
liniar independent și sistem de generatori.

În acel caz, numărul de elemente ale lui $ S $ se numește *dimensiunea*
spațiului $ V $ și se notează $ \dim_K(V) = n $.
```

```{note}
În cazul în care vom lucra cu spații vectoriale reale -- ca în majoritatea
exemplelor -- sau cînd nu există riscul de confuzie, vom omite indicele
corespunzător corpului de scalari și vom scrie, de exemplu, $ \dim(V) = n $.
```

Așadar, o bază a unui spațiu vectorial este o mulțime de vectori care sînt 
simultan independenți și generatori pentru vectorii din spațiu.

Vedem acum formalizată intuiția din prezentarea de la început: o bază este alcătuită
din vectorii care sînt strict necesari pentru a preciza în mod unic orice vector
din spațiu:
- stricta necesitate este garantată de proprietatea de a fi sistem de generatori;
- unicitatea scrierii este obținută din independența liniară. Aceasta deoarece,
dacă am avea, de exemplu, pentru un vector $ v $, două scrieri diferite (adică folosind
aceiași vectori din mulțime, dar scalari diferiți):
```{math}
v = ax_1 + bx_2 + cx_3 = dx_1 + ex_2 + fx_3, \quad a \neq d \text{ sau } b \neq e \text{ sau } c \neq f,
```
am obține că vectorii $ \{ x_1, x_2, x_3 \} $ nu sînt independenți, deoarece:
```{math}
(a - d)x_1 + (b - e)x_2 + (c - f)x_3 = 0,
```
însă cel puțin una dintre paranteze este nenulă, din ipoteză. Deci am obținut o combinație
liniară nulă a vectorilor $ \{ x_1, x_2, x_3 \} $, dar cu scalari nenuli (cel puțin unul).

De aici rezultă imediat:
```{prf:theorem}
:label: thm-desc-baza

Dacă $ B $ este o bază a unui $ K $-spațiu vectorial $ V $, atunci orice vector $ v \in V $
are o descompunere unică sub forma unei combinații liniare de vectori din $ B $,
cu scalari din $ K $.

Scalarii care apar în descompunere se numesc *coordonatele* vectorului în baza $ B $.
```

Fără demonstrație, mai enunțăm un rezultat foarte important:
```{prf:theorem}
:label: thm-exista-baza

Orice spațiu vectorial are cel puțin o bază.

În plus, dimensiunea unui spațiu vectorial este bine definită, adică dacă un spațiu
admite cel puțin două baze, ele au același număr de elemente.
```

Acest rezultat ne asigură că, indiferent de spațiul cu care lucrăm, putem găsi cel puțin
o bază a acestuia. Unele spații pot avea chiar o infinitate de baze și între ele vor
exista legături pe care le detaliem ulterior. Cu siguranță, însă, toate bazele unui spațiu
vectorial au același număr de elemente, care este dimensiunea spațiului.

Cu această ocazie, putem face și o observație de terminologie foarte importantă:
```{important}
Deoarece, riguros, dimensiunea unui spațiu vectorial este un număr, nu sînt corecte
exprimări la plural precum „spațiu cu 3 *dimensiuni*“. Varianta corectă a acestei
expresii este „spațiu de dimensiune 3“ sau „spațiu tridimensional“.
```

(sec-baze-canonice)=
### Exemple: Baze canonice

În matematică, cel puțin, atributul „canonic“ înseamnă ceva foarte simplu,
evident. De exemplu, spunem că *forma canonică* a unei funcții de gradul întîi este
$ f(x) = ax + b $. Evident că același lucru s-ar putea scrie, de exemplu, și sub forma
$ g(x) = a(x^2 + 2)^2 - a(x^2 + 3)^2 + 3ax + (b + 5) $, dar cu greu putem numi această
formă „simplă“ sau „evidentă“.

De aceea, *baze canonice* înseamnă cele mai simple exemple, pentru care aproape că nu este
nevoie de demonstrație a independenței și generării.

**Baza canonică a spațiilor $ \mathbb{R}^n $** este:
```{math}
B = \{ e_1 = (1, 0, 0, \dots, 0), e_2 = (0, 1, 0, 0, \dots, 0), \dots, e_i = (0, 0, \dots, 0, 1, 0, \dots, 0), \dots (0, 0, \dots, 0, 1) \},
```
unde fiecare vector are cîte $ n $ componente, iar vectorul $ e_i $ are componenta de pe poziția $ i $ egală cu $ 1 $
și în rest, $ 0 $.

O consecință simplă este că $ \dim(\mathbb{R}^n) = n $.

**Baza canonică a spațiului $ M_2(\mathbb{R}) $** este:
```{math}
B = \left\{ E_1 = \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix}, %
       E_2 = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, %
       E_3 = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}, %
       E_4 = \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix}
    \right\}
```

Rezultă, în particular, că $ \dim(M_2(\mathbb{R}) = 4 $.

Acest exemplu se poate generaliza imediat la matrice pătratice și nu numai,
însă am preferat să scriem explicit pe acesta pentru simplitate.

Cazul general este acesta: pentru spațiul $ V = M_{m, n}(\mathbb{R}) $,
baza canonică va conține matrice cu $ m $ linii și $ n $ coloane care au elemente
nule, mai puțin un singur element egal cu $ 1 $, pe toate pozițiile posibile.
În total, vom avea $ m \cdot n $ matrice, deci $ \dim(M_{m,n}(\mathbb{R})) = m \cdot n $.

**Baza canonică a spațiului de polinoame** $ \mathbb{R}_n[X] $ este:
```{math}
B = \{ 1, X, X^2, X^3, \dots, X^n \}
```
Rezultă că $ \dim(\mathbb{R}_{n}[X]) = n + 1 $.

Iar dacă generalizăm și nu mai impunem un grad maxim pentru polinoame, obținem
primul exemplu de spațiu *infinit dimensional*, anume $ \mathbb{R}[X] $.
Baza sa canonică va fi:
```{math}
B = \{ 1, X, X^2, X^3, \dots, X^n, X^{n+1}, \dots \}
```

Intuitiv, ar trebui să fie clar: pentru a putea scrie *orice* polinom, de *orice* grad,
trebuie să avem la dispoziție *orice* putere a lui $ X $, adică, în principiu,
o infinitate de elemente în bază. Așadar, $ \dim(\mathbb{R}[X]) = \infty $.

### Cum găsim o bază?
Bazele canonice menționate mai sus vor fi utilizate foarte des, dar în unele exerciții,
putem avea o cerința explicită de a găsi o bază *diferită de baza canonică*.
Arătăm acum astfel de exemple, ilustrînd modul de utilizare a definiției și proprietăților.

**Exemplu:** Fie spațiul $ V = \mathbb{R}^3 $ și mulțimea:
```{math}
S = \{ v_1 = (-1, 0, 1), v_2 = (3, 1, -1), v_3 = (0, 0, 2) \}
```
Arătăm că $ S $ este o bază a lui $ V $.

În principiu, am putea proceda cu definiția, adică să demonstrăm separat că $ S $ este
sistem liniar independent și sistem de generatori. Dar dacă punem cap la cap metodele
și mai ales dacă acordăm atenție deosebită utilizării matricelor, ajungem la concluzia
că este suficient să arătăm că determinantul matricei care are vectorii din $ S $ drept
coloane este nenul. Acest lucru ne va asigura că:
- vectorii sînt independenți, deoarece nu există nicio legătură algebrică între coloanele
(sau liniile) matricei, care să facă determinantul nul;
- vectorii formează un sistem de generatori, deoarece dacă folosim definiția, am ajunge
la un sistem cu 3 ecuații și 3 necunoscute, care este compatibil cu siguranță dacă
rangul matricei sistemului este maxim, adică 3.

Așadar, calculăm simplu:
```{math}
A = \begin{pmatrix}
  -1 & 3 & 0 \\
  0 & 1 & 0 \\
  1 & -1 & 2
  \end{pmatrix} \Rightarrow \det(A) = -2 \neq 0,
```
deci $ S $ formează o bază.

Am obținut, astfel, o altă bază pentru spațiul $ \mathbb{R}^3 $, bază care are, bineînțeles,
tot 3 elemente, cît este $ \dim(\mathbb{R}^3) $.

**Exemplu:** Fie mulțimea:
```{math}
V = \{ (x, y, z) \in \mathbb{R}^3 \mid 2x - y = 0, x + y - z = 0 \}.
```
Evident, aceasta este o submulțime a lui $ \mathbb{R}^3 $ și este chiar subspațiu (demonstrați!).
În particular, este un spațiu vectorial de sine stătător, deci are sens să-i căutăm o bază.

Dar mai întîi, să aflăm cum arată elementele lui $ V $. Pentru aceasta, trebuie să rezolvăm
sistemul care-l definește:
```{math}
\begin{cases}
  2x - y &= 0 \\
  x + y - z &= 0
\end{cases}.
```
Sistemul este compatibil nedeterminat, deci putem lua $ x = \alpha \in \mathbb{R} $ parametru
(necunoscută secundară). Rezultă $ y = 2\alpha $ și $ z = 3\alpha $.

Așadar:
```{math}
V = \{ (\alpha, 2\alpha, 3\alpha) \in \mathbb{R}^3 \}.
```

În căutarea bazei, putem face din start observația că, apelînd la înțelegerea intuitivă
a conceptului, avem nevoie de o singură informație pentru a putea preciza în mod unic
un vector din $ V $, anume $ \alpha $. Dat $ \alpha $, obținem forma generală a unui
vector din $ V $. Așadar, *intuim* că $ \dim(V) = 1 $, deci ar trebui să găsim un singur
vector în bază.

Într-adevăr, folosind aceste observații, putem scrie:
```{math}
(\alpha, 2\alpha, 3\alpha) = \alpha \cdot (1, 2, 3),
```
deci dacă definim $ B = \{ (1, 2, 3) \} $, egalitatea de mai sus ne arată că $ B $
este sistem de generatori pentru $ V $. Cum este vorba despre un singur vector, nu avem
de demonstrat independența, deci $ B $ este bază.

Cu această ocazie, menționăm un rezultat foarte important, pe care îl formulăm fără demonstrație.

```{prf:theorem} Teorema alternativei
:label: thm-alt

Fie $ V $ un spațiu vectorial cu $ \dim(V) = n $ și $ S = \{ x_1, x_2, \dots, x_n \} $
o mulțime de $ n $ vectori din $ V $.

Atunci $ S $ este liniar independentă $ \Leftrightarrow S $ este sistem de generatori $ \Leftrightarrow S $ este bază.
```

Cu alte cuvinte, dacă avem o mulțime de vectori care conține exact atîtea elemente cît
este dimensiunea spațiului, nu mai este nevoie să demonstrăm ambele proprietăți ale bazei.
Ni se prezintă o alternativă: fie demonstrăm că este sistem liniar independent, fie că
este sistem de generatori. Oricare dintre aceste două proprietăți o va implica pe cealaltă
și va face ca mulțimea să fie bază.

De fapt, fiindcă tot am ajuns la legătura între sisteme liniar independente, sisteme de generatori
și baze, mai formulăm un rezultat foarte important.
```{prf:theorem}
:label: thm-extras-completat

- Orice sistem liniar independent poate fi completat pînă la o bază.
- Din orice sistem de generatori se poate extrage o bază.
```

Cu alte cuvinte, este posibil să avem într-un sistem liniar independent *mai puțini* vectori
decît dimensiunea spațiului, iar într-un sistem de generatori, *mai mulți* vectori decît
dimensiunea spațiului. Celelalte cazuri sînt excluse. În consecință, de exemplu:
- în spațiul $ \mathbb{R}^3 $, orice mulțime de 5 vectori nu poate fi liniar independentă,
dar ar putea fi sistem de generatori;
- în spațiul $ M_{3,5}(\mathbb{R}) $, orice mulțime de 12 vectori poate fi liniar independentă,
dar nu poate fi sistem de generatori.

Completarea, respectiv extragerea de elemente se face foarte simplu:
- putem adăuga vectori arbitrari la un sistem liniar independent pînă obținem o bază;
- din orice sistem de generatori, extragem doar vectorii care sînt independenți și obținem o bază.

De exemplu: Fie mulțimea de vectori din $ \mathbb{R}^3 $: $ S = \{ v_1 = (2, 1, 0), v_2 = (3, -1, 1) \} $.
- demonstrăm că ea este independentă: într-adevăr, rangul matricei obținute din vectorii $ v_1 $
și $ v_2 $ puși pe coloane este 2, adică maxim;
- mai avem nevoie de încă un vector pentru a obține o bază în $ \mathbb{R}^3 $. Putem alege
cum dorim, de exemplu, $ v_3 = (1, 0, 0) $;
- acum demonstrăm că mulțimea $ \{ v_1, v_2, v_3 \} $ este independentă, verificînd, de exemplu,
că *determinantul* matricei ce are vectorii $ v_1, v_2, v_3 $ drept coloane este nenul
și am terminat (din teorema alternativei).

Pentru sisteme liniar independente, fie $ S = \{ v_1 = (2, -1), v_2 = (3, 5), v_3 = (7, 2), v_4 = (1, 1) \} $
o mulțime de vectori din $ \mathbb{R}^2 $.
- demonstrăm imediat că $ S $ este sistem de generatori. Într-adevăr, sistemul de ecuații
la care am ajunge ar avea 4 ecuații și 2 necunoscute, deci rangul matricei sistemului
și rangul matricei extinse vor fi ambele 2;
- extragem din $ S $ vectori independenți. Avem nevoie de 2 dintre ei, conform
teoremei alternativei, deci putem alege pe oricare 2 care se potrivesc. În particular,
putem alege pe cei care au dat rangul 2 matricei sistemului de la pasul anterior.
De pildă, $ v_1 $ și $ v_2 $, pentru că 
```{math}
\begin{vmatrix} 2 & -1 \\ 3 & 5 \end{vmatrix} = 13 \neq 0
```
și am terminat.

**Exemplu:** Fie mulțimea:
```{math}
V = \{ p \in \mathbb{R}_2[X] \mid p(3) = 0 \}.
```
Evident, $ V $ este submulțime a spațiului real de polinoame de grad cel mult $ 2 $, cu coeficienți
reali. Puteți demonstra chiar că este subspațiu. În particular, este un spațiu vectorial
în sine. Să-i găsim o bază și dimensiunea.

Mai întîi, să înțelegem cum arată elementele sale. Fie $ p = a + bX + cX^2 $ un polinom din $ V $.
Conform condiției $ p(3) = 0 $, obținem:
```{math}
a + 3b + 9c = 0.
```
Putem privi aceasta ca pe „un sistem“ cu o ecuație și 3 necunoscute. Rezultă că se poate
rezolva cu 2 parametri (necunoscute secundare). Fie aceștia $ b = \alpha \in \mathbb{R} $ și 
$ c = \beta \in \mathbb{R} $. Atunci $ a = -3\alpha - 9\beta $, deci:
```{math}
V = \{ p = (-3\alpha -9\beta) + \alpha X + \beta X^2 \mid \alpha, \beta \in \mathbb{R} \}.
```
În general, $ \dim(V) < 3 $, deoarece $ V \leq \mathbb{R}_2[X] $ și $ \dim(\mathbb{R}_{2}[X]) = 3 $
(cu baza canonică $ \{ 1, X, X^2 \} $).

Intuim că $ \dim(V) = 2 $, deoarece orice polinom din $ V $ este determinat în mod unic de
cei doi parametri $ \alpha $ și $ \beta $. Într-adevăr, putem scrie pentru $ p \in V $ arbitrar:
```{math}
p = (-3\alpha - 9\beta) + \alpha X + \beta X^2 = \alpha(-3 + X) + \beta(-9 + X^2),
```
de unde rezultă că dacă știm $ \alpha $ și $ \beta $, trebuie să folosim vectorii din
$ B = \{ -3 + X, -9 + X^2 \} $ și obținem orice polinom din $ V $.

Așadar, $ B $ este sistem de generatori și, folosind teorema alternativei, rezultă că este bază
($\dim(V) = 2$).

```{note}
Am putea argumenta că am dedus $ \dim(V) = 2 $ din motive intuitive, empirice,
astfel că nu putem invoca teorema alternativei, ci ar trebui să demonstrăm că $ B $
este și liniar independentă.

Însă observația pe care am făcut-o poate fi completată și de una riguroasă: evident,
$ V $ nu poate conține polinoame constante de forma $ p = a $, deoarece acestea
nu satisfac $ p(3) = 0 $, cu excepția polinomului nul.

Așadar, de fapt, pornim cu $ V = \{ aX + bX^2 \mid a, b \in \mathbb{R} \} $
și de aceea, putem argumenta riguros că $ 1 $ nu poate face parte dintr-un
sistem de generatori pentru $ V $, de unde deducem că $ V $ „pierde“ o unitate
de dimensiune față de spațiul polinoamelor de grad cel mult 2.
```

```{important}
**Dacă nu se precizează altfel, vom lucra de acum încolo numai cu spații vectoriale**
**finit dimensionale**.
```

## Schimbarea de bază
Am văzut că orice spațiu vectorial are (cel puțin) o bază. De asemenea, în cazuri
simple precum $ \mathbb{R}^2 $ și $ \mathbb{R}^3 $, este ușor să construim baze
noi, alegînd pur și simplu 2, respectiv 3 vectori liniar independenți și apoi folosind
teorema alternativei.

În plus, cînd lucrăm cu bazele canonice, coordonatele unui vector din plan sau din
spațiu sînt pur și simplu „componentele“ sale.

Ce se întîmplă, însă, dacă folosim o altă bază? Evident, ne așteptăm să aibă loc
și o schimbare de coordonate. Acest lucru se întîmplă și are numeroase aplicații.
În grafica pe computer, există cel puțin 3 spații vectoriale (izomorfe) pe care
le folosim și care au baze diferite. Pentru grafica 3D, se folosesc 3 copii ale
spațiului $ \mathbb{R}^3 $, anume:
- spațiul corespunzător mediului înconjurător (eng. *world space*), care rămîne fix
și reprezintă peisajul, „lumea“, de obicei statică;
- spațiul corespunzător obiectului care traversează lumea (eng. *object space*).
De exemplu, într-un joc, acesta corespunde personajului-jucător;
- spațiul corespunzător camerei, i.e. punctului de vedere (eng. *camera space*).
De exemplu, în jocurile *first person*, camera coincide cu obiectul, pentru că
punctul de vedere este direct al jucătorului. În jocurile *third person*, camera
oferă o perspectivă de ansamblu și este externă jucătorului.

În multe cazuri, sistemele de referință (i.e. bazele corespunzătoare spațiilor respective)
coincid cu „centrul“ -- centrul de greutate al obiectului, punctul central care oferă
perspectiva camerei (cum ar fi poziția obiectivului unei camere foto-video) etc.
Trecerea între aceste sisteme de referință și, respectiv, bazele corespunzătoare
este justificată atunci cînd, de exemplu, se trece de la o perspectivă third person
la una first person sau invers. De asemenea, pentru realism, cele trei sistem de
referință nu sînt complet aleatorii, ci există legături între ele pe care programatorii
sau modelatorii le iau în considerare.

Cazul general este ușor de definit, dar laborios de utilizat.

Fie $ V $ un spațiu vectorial și $ B_1, B_2 $ două baze ale sale.

Presupunem că $ B_1 = \{ e_1, e_2, \dots, e_n \} $ și $ B_2 = \{ f_1, f_2, \dots, f_n \} $.

**Matricea de trecere** de la baza $ B_1 $ la baza $ B_2 $ se obține astfel:
- se consideră baza $ B_2 $, la care vrem să ajungem, drept „principală“, iar
baza $ B_1 $ devine o simplă mulțime de vectori;
- de aceea, orice vector din baza $ B_1 $ se poate scrie acum în funcție de
vectorii din baza $ B_2 $:
```{math}
\begin{align*}
  e_1 &= \alpha_{11}f_1 + \alpha_{12}f_2 + \alpha_{13}f_3 + \dots + \alpha_{1n}f_n \\
  e_2 &= \alpha_{21}f_1 + \alpha_{22}f_2 + \alpha_{23}f_3 + \dots + \alpha_{2n}f_n \\
      &\vdots \\
  e_n &= \alpha_{n1}f_1 + \alpha_{n2}f_2 + \alpha_{n3}f_3 + \dots + \alpha_{nn}f_n,
\end{align*}
```
cu scalarii $ \alpha_{ij} \in \mathbb{R}, 1 \leq i,j \leq n $.

Matricea menționată se definește prin $ M_{B_1 \to B_2} = (\alpha_{ij})_{1 \leq i, j \leq n} $.

---

Pentru baze arbitrare, cum spuneam, matricea este incomod de calculat. Dar în multe cazuri 
practice, precum vom vedea în {ref}`secțiunea despre diagonalizare<sec-diagonalizare>` 
se folosește trecerea de la baza canonică la o altă bază.

Pentru această situație, calculul este simplu. Să luăm un exemplu din $ \mathbb{R}^3 $.
Baza canonică este $ E = \{ e_1 = (1, 0, 0), e_2 = (0, 1, 0), e_3 = (0, 0, 1) \} $
și fie o altă bază, $ B = \{ f_1 = (2, -1, 1), f_2 = (3, 0, 2), f_3 = (-1, 1, 2) \} $.

Ne putem asigura mai întîi că $ B $ este într-adevăr bază:
```{math}
\begin{vmatrix}
2 & 3 & -1 \\
-1 & 0 & 1 \\
1 & 2 & 2
\end{vmatrix} = 7 \neq 0,
```
deci cei 3 vectori sînt independenți și, cu teorema alternativei, formează o bază.

Acum, pentru a obține matricea de trecere, trebuie să exprimăm „vechii“ vectori
$ e_{1,2,3} $ în funcție de cei „noi“, $ f_{1,2,3} $. Deci căutăm scalarii
$ \alpha_{ij}, 1 \leq i,j \leq 3 $, cu:
```{math}
\begin{align*}
  e_1 &= (1, 0, 0) = \alpha_{11}(2, -1, 1) + \alpha_{12}(3, 0, 2) + \alpha_{13}(-1, 1, 2) \\
  e_2 &= (0, 1, 0) = \alpha_{21}(2, -1, 1) + \alpha_{22}(3, 0, 2) + \alpha_{23}(-1, 1, 2) \\
  e_3 &= (0, 0, 1) = \alpha_{31}(2, -1, 1) + \alpha_{32}(3, 0, 2) + \alpha_{33}(-1, 1, 2)
\end{align*}
```
și ajungem 3 sisteme de ecuații, cîte unul pentru fiecare vector. Pentru $ e_1 $ obținem:
```{math}
\begin{cases}
  2\alpha_{11} + 3\alpha_{12} - \alpha_{12} &= 0 \\
  -\alpha_{11} + \alpha_{13} &= 0 \\
  \alpha_{11} + 2\alpha_{12} + 2\alpha_{13} &= 0
\end{cases}
```

Similar pentru ceilalți doi vectori $ e_2, e_3 $. Rezolvînd sistemele, obținem un rezultat
general, de fapt: soluțiile vor fi:
```{math}
\begin{align*}
  (\alpha_{11}, \alpha_{12}, \alpha_{13}) &= f_1 \\
  (\alpha_{12}, \alpha_{22}, \alpha_{23}) &= f_2 \\
  (\alpha_{13}, \alpha_{23}, \alpha_{33}) &= f_3
\end{align*}
```
Deci matricea $ M_{E \to B} $ conține direct „noii vectori“, pe coloane:
```{math}
M_{E \to B} = \begin{pmatrix}
2 & 3 & -1 \\
-1 & 0 & 1 \\
1 & 2 & 2
\end{pmatrix}
```

Avem, deci:
```{important}
Dacă se trece de la baza canonică $ E $ la o bază arbitrară $ B $, atunci
matricea de trecere $ M_{E \to B} $ va conține componentele noilor vectori
pe coloane.
```

De asemenea, cum probabil intuiți, $ M_{B_1 \to B_2} = M_{B_2 \to B_1}^{-1} $,
adică matricea care face trecerea inversă între două baze se obține ca inversa
matricei care făcea trecerea directă între baze.

Ce se întîmplă, însă, cu coordonatele vectorilor? Evident, odată cu schimbarea bazei,
și acestea se schimbă, deoarece se exprimă în funcție de alți vectori. Putem obține
pentru fiecare în parte noile coordonate, folosind definiția, dar avem și o scurtătură.

```{important}
Fie $ X_1 $ matricea-coloană a coordonatelor unui vector într-o bază $ B_1 $
și $ X_2 $ matricea-coloană corespunzătoare în baza $ B_2 $. Dacă $ M = M_{B_1 \to B_2} $
este matricea de trecere, atunci are loc relația:

$$
  X_2 = M^{-1} \cdot X_1 \Leftrightarrow X_1 = M \cdot X_2.
$$
```

Rezultă că, știind matricea de trecere între două baze, putem transforma direct
și coordonatele oricărui vector.


## Exerciții propuse
Pentru exercițiile de mai jos, vă încurajăm să vă gîndiți mai întîi la explicații intuitive,
eventual geometrice, pe care să le demonstrați riguros ulterior.

1. Fie mulțimea:
```{math}
V = \{ (x, y, z) \in \mathbb{R}^3 \mid 2x - y + z = 0 \}.
```
Arătați că $ V \leq \mathbb{R}^3 $ și găsiți o bază și dimensiunea lui $ V $.

2. Aceeași cerință pentru mulțimea:
```{math}
V = \langle (1, -1, 2), (3, 1, 0) \rangle.
```
Observați că, din definiție, cei doi vectori sînt deja sistem de generatori
pentru spațiul $ V $ (după ce demonstrați că este subspațiu al lui $ \mathbb{R}^3 $).

3. Aceeași cerință pentru mulțimea:
```{math}
V = \{ A \in M_2(\mathbb{R}) \mid A = A^t \},
```
ca subspațiu al lui $ M_2(\mathbb{R}) $.

4. Aceeași cerință pentru mulțimea:
```{math}
V = \{ (x, y, z, t) \in \mathbb{R}^4 \mid 3x - y + z = 0 \text{ și } 5y - 2t = 0 \},
```
ca subspațiu al lui $ \mathbb{R}^4 $.

5. Aceeași cerință pentru mulțimea:
```{math}
V = \{ p \in \mathbb{R}_3[X] \mid p'(1) = 0 \text{ și } p(2) = 0 \}
```
ca subspațiu al lui $ \mathbb{R}_3[X] $.
