# Vectori și valori proprii

(sec-vvp-motivatie)=
## Motivație
Vectorii și valorile proprii -- denumiți în engleză și germană, respectiv,
*eigenvectors* și *eigenvalues* -- alcătuiesc o temă fascinantă, cu numeroase
aplicații.

Înainte de definiția formală, să spunem că vectorii și valorile proprii se
asociază unei aplicații liniare. Deci, dat un morfism de spații vectoriale,
putem calcula vectorii și valorile proprii ale sale. Însă, așa cum știm,
o aplicație liniară se comportă ca o matrice, asociindu-i-se în mod canonic
matricea sa în bazele canonice ale spațiilor care alcătuiesc domeniul de 
definiție și, respectiv, codomeniul său. De aceea, putem vorbi și despre
vectorii și valorile proprii ale unei matrice. Iar prin această legătură
ajungem la aplicațiile esențiale.

Unele dintre cele mai spectaculoase aplicații sînt, de exemplu, cele de mai jos.

În **fizica cuantică**, starea unui sistem fizic se studiază în spații vectoriale
complexe și sofisticate. O evoluție a unui astfel de sistem se face printr-o
transformare dată de un morfism. Unul dintre postulatele mecanicii cuantice,
care datează de la începutul anilor 1900, afirmă (simplificînd, desigur) că dacă 
vrem să obținem cît mai multe informații privitoare la starea sistemului 
în cazul unei astfel de evoluții, nu vom putea obține decît vectorii și valorile
proprii asociate transformării. Un astfel de rezultat este ceea ce în unele
scrieri de popularizare a științei se formulează prin aceea că nu putem afla
niciodată starea unui sistem, pentru că atunci cînd aplicăm o anume măsurătoare,
sistemul își schimbă starea.

Din punct de vedere **computațional**, valorile proprii ale unei matrice se
comportă similar cu numerele prime din aritmetica elementară. Altfel spus,
dată o matrice oarecare, ea poate fi „simplificată“ într-o formă care îi
evidențiază valorile proprii. Dacă, de exemplu, în cazul numerelor naturale,
în loc să lucrăm cu $ n = 100 $, scriem $ n = 2^2 \cdot 5^2 $, obținem
informații suplimentare și, totodată, simplificăm numărul, prin expunerea
factorilor săi primi. În cazul matricelor, o formă simplificată se numește
*forma diagonală*, care are elemente nenule doar pe diagonala principală.
Nu toate matricele pot avea această formă, însă alternativa nu este cu mult
mai sofisticată și se numește *forma canonică Jordan*.

Metodele sus-menționate înlocuiesc o matrice dată cu o altă matrice, mai simplă,
din punct de vedere computațional. Dar în alte cazuri, poate fi util să înlocuim
o matrice cu două sau mai multe alte matrice, fiecare dintre ele mai simplă decît
matricea inițială și, eventual, separînd, într-un anume sens, informațiile din 
matricea inițială. De pildă, dacă aplicăm o transformare sofisticată precum o rotație
urmată de o rescalare orizontală, în loc să păstrăm ambele transformări într-o singură
matrice, este mai eficient, dar și mai clar să le separăm. Transformarea întreagă
se va compune, atunci, ca sumă sau produs al matricelor corespunzătoare celor două
transformări.

Faptul că matricele se pot „simplifica“, cu ajutorul valorilor proprii are
inclusiv aplicații moderne, în **inteligența artificială**. De exemplu, în procesarea
imaginilor se lucrează cu spații bidimensionale -- spațiul asociat imaginii, practic.
Multe transformări ale imaginilor (rotații, rescalări sau chiar procesări complicate
precum transformarea în alb-negru, extragerea contururilor, modificarea contrastului)
se pot caracteriza matriceal. Practic, transformarea este conținută într-o matrice
de dimensiune cel mult egală cu numărul de pixeli pe care se aplică, iar informațiile
relevante din pixelii individuali (poziția, informațiile de culoare, transparență etc.)
se înmulțesc cu matricea transformării. Astfel de operații implică adesea
lucrul cu milioane de numere, iar dacă luăm în considerare discipline precum
învățarea automată, modelele se antrenează prin aplicarea transformărilor respective
pe terrabiți de date. O metodă simplă de optimizare a calculelor este înlocuirea
matricelor corespunzătoare transformărilor respective cu forme diagonale sau Jordan
sau, în orice caz, cu unele care își concentrează informația în valorile proprii.

În afara exemplului din fizică -- pentru care ar fi nevoie de discuții lungi și tehnice
privitoare la contextul matematic, la modul în care fizica „traduce“ în matematică
noțiuni privitoare la starea unui sistem --, vom detalia o bună parte a celorlalte
două aplicații. 

Începem cu partea matematică, urmînd ca aplicațiile în programare și inteligență
artificială să le prezentăm în partea a treia a lucrării.

## Definiții și metode de calcul
După definițiile formale, accentul în această secțiune va cădea pe metode 
concrete de calcul, algoritmice aproape. Considerăm nu doar că o astfel
de prezentare face lucrurile mai clare, dar în același timp, ne oferă și
indicii pentru implementarea programatică din partea a treia.

```{prf:definition}
:label: dev-vvp

Fie $ V, W $ două spații vectoriale și $ f : V \to W $ o aplicație liniară.

Se numește *vector propriu* al lui $ f $, asociat valorii proprii $ \lambda \in \mathbb{R} $
un vector $ v \in V $ astfel încît $ f(v) = \lambda v $.
```

Altfel spus, un vector propriu este unul asupra căruia aplicația liniară are
o acțiune foarte simplă: îl rescalează cu scalarul $ \lambda $.

Întrucît acțiunea unei aplicații liniare corespunde canonic înmulțirii cu
matricea aplicației, o definiție alternativă și mai practică din punct de
vedere computațional este următoarea:

```{prf:definition}
:label: def-vvp-matrice

Fie $ V, W $ două spații vectoriale finit dimensionale, cu $ \dim V = m, \dim W = n $.

Fie $ f : V \to W $ o aplicație liniară și $ A = M_f^{BC} \in M_{n,m}(\mathbb{R}) $,
matricea aplicației $ f $ în bazele canonice.

Vectorul-linie $ v \in V $ se numește *vector propriu* al lui $ A $, asociat
valorii proprii $ \lambda \in \mathbb{R} $ dacă $ A \cdot v^t = \lambda v^t $,
unde $ v^t $ notează vectorul-coloană obținut prin transpunerea lui $ v $.
```

```{note}
Prin definiție, se presupune că un vector propriu nu poate fi vectorul nul.
Dar valori proprii nule sînt permise.
```

În această definiție pare că vectorii și valorile proprii se aleg special din acțiunea
aplicației liniare (sau a matricei), dar așa cum vom vedea, de fapt ei (și ele)
*determină* matricea, într-un anume sens, conțin informația esențială pe care o
transmite matricea.

---

Pentru calculul efectiv, vom lucra doar cu cazul matriceal și pornim de la
definiție. Vom folosi notațiile și contextul din definiția de mai sus.
De asemenea, pentru simplitate, vom presupune $ m = n $, adică $ V $ și $ W $
au aceeași dimensiune. Acest lucru va face ca matricea $ A $ să fie pătratică
și va ușura calculele și considerațiile teoretice.
```{math}
A v^t = \lambda v^t \Rightarrow Av^t - \lambda v^t = 0 \Rightarrow (A - \lambda I_n)v^t = 0.
```
De remarcat că pentru ultima egalitate am folosit factorul comun, dar ținem seama
de *necomutativitatea* înmulțirii matricelor, astfel că factorul comun este la dreapta.
Matricea $ I_n $ este matricea identitate, care are 1 pe diagonala principală și 0 în rest.

De aici, putem continua în mai multe moduri. De exemplu, dacă definim matricea
$ B = A - \lambda I_n $, egalitatea de mai sus implică faptul că
$ v^t \in \mathrm{Ker}(B) $. Acum, orice matrice are un nucleu, care conține
cel puțin vectorul nul. Însă știm că un vector propriu nu poate să fie nul,
deci dacă vrem ca $ v^t $ să fie vector propriu nenul, rezultă că nucleul lui $ B $
trebuie să conțină și alți vectori în afară de $ 0 $. Cu alte cuvinte, transformarea
dată de $ B $ *nu* trebuie să fie injectivă și atunci nu mai poate să fie inversabilă.
Revenind la matrice, rezultă că matricea $ B $ nu este inversabilă, așadar
$ \det B =  \det(A - \lambda I_n) = 0 $.

Astfel ajungem la următoarea noțiune teoretică importantă:

```{prf:definition}
:label: def-pol-car

Fie $ A \in M_n(\mathbb{R}) $. Se numește *polinomul caracteristic* al matricei
$ A $ polinomul $ P_A(X) = \det(A - XI_n) $.

Rădăcinile acestui polinom sînt chiar valorile proprii ale matricei.

Mulțimea valorilor proprii se numește *spectrul* matrice, notat $ \sigma(A) $.
```

Rezultă că vom rezolva ecuația polinomială atașată $ P_A(x) = 0 $, numită
*ecuația caracteristică*, ale cărei soluții vor fi chiar valorile proprii ale lui $ A $.

Odată determinat spectrul matricei, vectorii proprii asociați se determină direct.

Iată un exemplu.


### Exemplu numeric rezolvat
Vom porni direct cu o matrice pătratică, de exemplu:
```{math}
A = \begin{pmatrix}
1 & -1 & 2 \\
1 & 0 & 1 \\
2 & 1 & 1
\end{pmatrix}
```
Am fi putut începe problema cu o aplicație liniară, pentru care $ A $ să
fie matricea în bazele canonice:
```{math}
f : \mathbb{R}^3 \to \mathbb{R}^3, \quad f(a, b, c) = (a - b + 2c, a + c, 2a + b + c).
```
Se vede că $ A = M_f^{BC} $, așa că vom lucra direct cu matricea.

Scriem polinomul său caracteristic:
```{math}
P_A(X) = \det(A - XI_3) = %
	\begin{vmatrix}
	1 - X & -1 & 2 \\
	1 & -X & 1 \\
	2 & 1 & 1 - X
	\end{vmatrix} = -X^3 + 2X^2 + 3X.
```
Acum rezolvăm ecuația caracteristică:
```{math}
-x^3 + 2x^2 + 3x = 0 \Rightarrow x(x + 1)(x - 3) = 0 \Rightarrow \sigma(A) = \{ 0, -1, 3 \}.
```
Așadar, avem 3 valori proprii distincte: $ \lambda_1 = 0, \lambda_2 = -1, \lambda_3 = 3 $.

Pentru vectorii proprii asociați, continuăm pe rînd.

Fie $ \lambda_1 = 0 $ și $ v = (a, b, c) \in \mathbb{R}^3 $ un vector propriu asociat.
Din definiție, rezultă:
```{math}
A v^t = \lambda_1 v^t = 0 \Rightarrow %
\begin{pmatrix}
1 & -1 & 2 \\
1 & 0 & 1 \\
2 & 1 & 1 
\end{pmatrix} \cdot
\begin{pmatrix}
a \\ b \\ c
\end{pmatrix} = %
\begin{pmatrix}
a - b + 2c \\
a + c \\
2a + b + c
\end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}
```
Ajungem la sistemul de ecuații:
```{math}
\begin{cases}
	a - b + 2c &= 0 \\
	a + c &= 0 \\
	2a + b + c &= 0
\end{cases}
```
Sistemul este compatibil simplu nedeterminat și se obține soluția
$ (a, b, c) \in \{ (-\alpha, \alpha, \alpha) \mid \alpha \in \mathbb{R} \} $.

Așadar, vectorii proprii asociați valorii proprii $ \lambda_1 = 0 $ au forma de mai sus.

Mai departe, pentru $ \lambda_2 = -1 $, fie $ v = (a, b, c) \in \mathbb{R}^3 $ un vector
propriu asociat. Procedînd exact ca mai sus, ajungem la același sistem de ecuații, doar
cu rezultate diferite:
```{math}
\begin{cases}
	a - b + 2c &= -a \\
	a + c &= -b \\
	2a + b + c &= -c
\end{cases}
```
Sistemul este tot compatibil simplu nedeterminat, cu soluția
$ (a, b, c) \in \{ (-\alpha, 0, \alpha) \mid \alpha \in \mathbb{R} \} $, deci vectorii
proprii asociați valorii proprii $ \lambda_2 = -1 $ au această formă.

În fine, pentru $ \lambda_3 = 3 $, procedăm la fel și ajungem la:
```{math}
\begin{cases}
	a - b + 2c &= 3a \\
	a + c &= 3b \\
	2a + b + c &= 3c
\end{cases}
```
sistem care are soluția $ (a, b, c) \in \{ (5\alpha, 4 \alpha, 7\alpha) \mid \alpha \in \mathbb{R} \} $,
deci vectorii proprii asociați valorii proprii $ \lambda_3 = 3 $ au această formă.

---

Un rezultat teoretic general, care ne ava ajuta în cele ce urmează, este:

```{prf:theorem}
:label: thm-subsp-inv

Mulțimea vectorilor proprii asociați unei valori proprii $ \lambda $ ale unei aplicații
liniare $ f : V \to W $ formează un subspațiu al lui $ V $, notat $ V_\lambda $ și numit
*subspațiu propriu* sau *invariant*.
```

Așadar, putem scrie rezultatul exemplului de mai sus simbolic, sub forma:
```{math}
\begin{align*}
	\sigma(A) &= \{ \lambda_1, \lambda_2, \lambda_3 \} = \{ 0, -1, 3 \} \\
	V_{\lambda_1} &= \{ (-\alpha, \alpha, \alpha) \mid \alpha \in \mathbb{R}^3 \} \\
	V_{\lambda_2} &= \{ (-\alpha, 0, \alpha) \mid \alpha \in \mathbb{R} \} \\
	V_{\lambda_3} &= \{ (5\alpha, 4\alpha, 7\alpha) \mid \alpha \in \mathbb{R} \}.
\end{align*}
```

(sec-diagonalizare)=
## Diagonalizare
Calculele de mai sus conduc la aplicații deosebite. Începem cu cea mai spectaculoasă,
dar în același timp, rară: diagonalizarea.

Prin definiție, spunem că o matrice este *diagonală* dacă ea conține elemente
nenule doar pe diagonala principală. De exemplu, pentru o matrice din $ M_3(\mathbb{R}) $,
forma diagonală este:
```{math}
A = \begin{pmatrix}
a & 0 & 0 \\
0 & b & 0 \\
0 & c & 0
\end{pmatrix},
```
pentru niște numere reale $ a, b, c $, formă care se mai notează $ A = \mathrm{diag}(a, b, c) $.

Unele matrice au proprietatea că pot fi „înlocuite“ cu matrice diagonale și, pentru majoritatea
aplicațiilor, dau aceleași rezultate ca în forma nediagonală. Nu toate au această proprietate,
dar pentru cele care o au, e clar că permit simplificări considerabile din punct de vedere computațional.

Pînă la enunțarea *criteriului de diagonalizare*, mai avem nevoie de două noțiuni teoretice.

**Vom presupune, în continuare, că lucrăm cu matrice pătratice.**


```{prf:definition}
:label: def-multiplicitate

Fie $ \{ \lambda_1, \lambda_2, \dots, \lambda_n \} $ valorile proprii ale unei matrice
și $ V_{\lambda_1}, \dots, V_{\lambda_n} $ subspațiile invariante asociate.

- Se numește *multiplicitatea algebrică* a valorii proprii $ \lambda_i, 1 \leq i \leq n $,
notată $ m_a(\lambda_i) $ sau chiar $ a(\lambda_i) $, multiplicitatea rădăcinii
$ x = \lambda_i $ în polinomul caracteristic. Altfel spus, este puterea maximă $ m $
astfel încît polinomul $ X - \lambda_i $ divide polinomul caracteristic.
- Se numește *multiplicitatea geometrică* a valorii proprii $ \lambda_i, 1 \leq i \leq n $,
notată $ m_g(\lambda_i) $ sau mai simplu $ g(\lambda_i) $, dimensiunea subspațiului
invariant asociat. În formulă, $ m_g(\lambda_i) = \dim V_{\lambda_i} $.
```

În exemplul anterior, toate rădăcinile polinomului caracteristic sînt simple,
deci $ a(0) = a(-1) = a(3) = 1 $. De asemenea, se vede imediat că fiecare subspațiu
invariant este 1-dimensional, deci $ g(0) = g(-1) = g(3) = 1 $.

Un rezultat simplu de enunțat, dar netrivial de demonstrat, pe care îl vom folosi de
multe ori în exemple și exerciții este acesta:

```{prf:theorem}
:label: thm-mg-ma

$$ a(\lambda) \geq g(\lambda), \forall \lambda \in \sigma(A). $$
```

Cu alte cuvinte, pentru orice valoare proprie, multiplicitatea algebrică este
cel mult egală cu cea geometrică. De exemplu, putem folosi acest rezultat în
exemplul anterior: văzînd că $ a(\lambda_{1,2,3}) = 1 $, rezultă automat că
$ g(\lambda_{1,2,3}) = 1 $, pentru că o multiplicitate geometrică egală cu 0 este
imposibilă (ar trebui ca un subspațiu invariant să fie spațiul nul, ceea ce este
imposibil, deoarece vectori proprii nuli nu sînt permiși).

Criteriul de diagonalizare pentru o matrice conține condiții echivalente pentru ca o matrice
să poată fi adusă la forma diagonală. Teorema generală conține mai multe condiții,
însă le vom prezenta doar pe cele ușor de verificat și de implementat.

```{prf:theorem} Criteriul de diagonalizare pentru o matrice pătratică
:label: thm-diag

Fie $ A \in M_n(\mathbb{R}) $ o matrice pătratică.

Următoarele afirmații sînt echivalente:

1. $ A $ este diagonalizabilă;
2. $ a(\lambda_i) = g(\lambda_i), \forall \lambda_i \in \sigma(A) $;
3. Există o bază a lui $ \mathbb{R}^n $ formată doar din vectori proprii ai lui $ A $. Rezultă, în particular, că 

$$ 
  \mathbb{R}^n \simeq V_{\lambda_1} \oplus V_{\lambda_2} \oplus \dots \oplus V_{\lambda_n}, \forall \lambda_i \in \sigma(A), 1 \leq i \leq n.
$$

4. Există o matrice diagonală $ D $ și o matrice inversabilă $ T $ astfel încît
$ A = TDT^{-1} $. Mai mult, $ D = \mathrm{diag}(\lambda_i), \lambda_i \in \sigma(A) $.
```

Ultima condiție poate părea stranie: $ A = TDT^{-1} $, pe care o mai putem scrie și
sub forma $ AT = TD $. Însă ea stă la baza unei noțiuni importante în calculul
vectorial:

```{prf:definition}
:label: mat-asem

Două matrice $ A $ și $ B $ se numesc *asemenea*, notat $ A \sim B $,
dacă există o matrice inversabilă $ T $ astfel încît $ A = TDT^{-1} $.
```
Două consecințe imediate ale relației de asemănare sînt:
- $ A \sim B \Rightarrow \det(A) = \det(B) $ (justificați!);
- relația de asemănare este una de echivalență: este **reflexivă** ($ A \sim A $),
**simetrică** ($ A \sim B \Rightarrow B \sim A $) și **tranzitivă** ($ A \sim B $
și $ B \sim C $ implică $ A \sim C $).

Aceste proprietăți -- deși nu conțin justificarea completă -- sînt o indicație
pentru faptul că două matrice asemenea se comportă „la fel“ în multe situații
algebrice. De aceea, o matrice diagonalizabilă -- pe care acum o înțelegem ca fiind
*asemenea cu o matrice diagonală* -- poate fi substituită de aceasta din urmă
în „majoritatea“ calculelor algebrice. În plus, știm exact cum arată forma diagonală
pe care o căutăm, cînd ea există: conține valorile proprii ale matricei inițiale.
Imprecizia acestei exprimări va fi clarificată în cazul în care vom lucra cu exemple 
cînd afirmația nu este adevărată.

---

Să revenim la exemplul pe care l-am dat și să-l continuăm pînă la diagonalizare.
Cum valorile proprii ale matricei $ A $ au multiplicitățile egale cu 1, rezultă
că matricea se poate diagonaliza. Știm chiar și care este forma ei diagonală:
```{math}
A \sim \mathrm{diag}(0, -1, 3) = %
\begin{pmatrix}
0 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & 3
\end{pmatrix}
```

Dar să explorăm puțin și celelalte afirmații din criteriul de diagonalizare.
Putem obține o bază a lui $ \mathbb{R}^3 $ chiar din bazele subspațiilor proprii.
Cum $ V_{\lambda_1} = \{ (-\alpha, \alpha, \alpha) \mid \alpha \in \mathbb{R} \} $,
rezultă că $ v_1 = (-1, 1, 1) $ este o bază în $ V_{\lambda_1} $.

Similar, $ v_2 = (-1, 0, 1) $ este o bază în $ V_{\lambda_2} $ și
$ v_3 = (5, 4, 7) $ este o bază în $ V_{\lambda_3} $.

Folosind criteriul de diagonalizare și din teorema alternativei, rezultă că
$ B_\lambda = \{ v_1, v_2, v_3 \} $ este o bază a lui $ \mathbb{R}^3 $,
formată doar din vectori proprii ai lui $ A $.

Matricea $ T $ care apare în relația de asemănare $ A \sim D $ este o matrice
specială, numită *matricea de trecere* de la baza canonică a lui $ \mathbb{R}^3 $
la baza $ B_\lambda $ de mai sus. Ea se obține din vectorii $ v_1, v_2, v_3 $,
puși pe coloane, deci:
```{math}
T = \begin{pmatrix}
-1 & -1 & 5 \\
1 & 0 & 4 \\
1 & 1 & 7
\end{pmatrix}
```
Putem verifica acum că, într-adevăr, $ A = TDT^{-1} $, egalitate care poate fi scrisă
și sub forma $ D = T^{-1}AT = \mathrm{diag}(0, -1, 3) $.

### Contraexemplu de diagonalizare
Să vedem acum un exemplu de matrice care *nu* se diagonalizează, din cauza condițiilor
din criteriu.

Fie $ A = \begin{pmatrix} 1 & 2 & 1 \\ 0 & -1 & 0 \\ -1 & -2 & -1 \end{pmatrix} $.

Procedăm ca în cazul anterior. Calculăm valorile proprii, ca rădăcini ale polinomului
caracteristic:
```{math}
P_A(X) = \det(A - XI_3) = %
\begin{vmatrix}
1 - X & 2 & 1 \\
0 & -1-X & 0 \\
-1 & -2 & -1-X
\end{vmatrix} = X^3 + X^2
```
rezultă că ecuația caracteristică este $ x^3 + x^2 = x^2(x + 1) = 0 $, cu rădăcinile
$ x = 0 $ *rădăcină dublă* și $ x = -1 $ rădăcină simplă. Obținem
$ \sigma(A) = \{ 0, -1 \} $, cu $ a(\lambda_1 = 0) = 2 $ și $ a(\lambda_2 = -1) = 1 $.

Mai departe, vectorii proprii asociați.

Pentru $ \lambda_1 = 0 $, se obține subspațiul propriu 
$ V_{\lambda_1} = \{ (-\alpha, 0, \alpha) \mid \alpha \in \mathbb{R} \} $,
care are $ \dim V_{\lambda_1} = 1 $, deci $ g(\lambda_1) = 1 $. Putem vedea deja
că matricea nu este diagonalizabilă, deoarece $ a(\lambda_1) \neq g(\lambda_1) $.

Totuși, să calculăm și vectorii proprii pentru cea de-a doua valoare proprie.
Se obține $ V_{\lambda_1} = \{ (-2\alpha, \alpha, 2\alpha) \mid \alpha \in \mathbb{R} \} $,
deci $ g(\lambda_2) = 1 $ -- ceea ce era oricum de așteptat, fiindcă $ a(\lambda_2) = 1 $.

Concluzia este că matricea nu se poate diagonaliza.

Există o alternativă, care aduce, totuși, matricea la o formă care este 
ceva mai ușor de folosit -- forma canonică Jordan.

### Aplicație: Puterile unei matrice
De obicei, dată o matrice $ A $, puterile ei $ A^n $, pentru $ n $ arbitrar
se calculează destul de dificil. În majoritatea cazurilor, fie se caută
o descompunere a lui $ A $ de forma $ A = M + N $, astfel încît $ M $
și $ N $ să comute (adică $ MN = NM $) și se aplică o formulă de tipul binomului
lui Newton, fie se caută o astfel de descompunere în care $ M $ sau $ N $ să
fie nilpotente -- de la o putere încolo să devină matricea nulă.

O altă metodă presupune ridicarea la cîteva puteri a lui $ A $ în speranța că
se obține o formulă generală, care se poate enunța și demonstra apoi inductiv.

Dar dacă matricea $ A $ se diagonalizează, avem încă o metodă la dispoziție,
ceva mai simplă decît anterioarele. Să presupunem, deci, că $ A $ este diagonalizabilă,
adică există o matrice inversabilă $ T $ și una diagonală $ D $, cu 
$ A = TDT^{-1} $, iar $ D = \mathrm{diag}(\lambda_1, \dots, \lambda_n) $, unde
$ \lambda_i \in \sigma(A), \forall 1 \leq i \leq n $. 

Un calcul simplu de ridicare la putere arată, de pildă:
```{math}
A^2 = \left( TDT^{-1} \right)^2 = TDT^{-1} \cdot TDT^{-1} = TD(TT^{-1})DT^{-1} = T D^2 T^{-1},
```
unde am folosit metoda generală de a înmulți două matrice, deoarece nu știm dacă $ T $
și $ D $ comută, în general. Similar, se poate arăta că are loc rezultatul general:
```{math}
A^n = T D^n T^{-1}, \forall n \geq 1
```
și marele avantaj este că puterile lui $ D $ se calculează foarte ușor, anume:
```{math}
D^n = \mathrm{diag}(\lambda_i^n), \forall n \geq 1.
```
Așadar, ajungem la următoarea concluzie:
```{important}
În contextul și cu notațiile de mai sus, dacă $ A $ este diagonalizabilă, atunci
$ \sigma(A^n) = \{ \lambda_i^n \} $, pentru orice putere $ n $, unde
$ \sigma(A) = \{ \lambda_i \} $.

Mai mult, $ A^n = T D^n T^{-1} $, unde $ D^n = \mathrm{diag}(\lambda_i^n) $.
```

## Forma canonică Jordan
Dacă o matrice nu poate fi diagonalizată, ea poate, totuși, să fie adusă la
o formă mai simplă, numită *forma canonică Jordan*. Această formă este alcătuită din
*blocuri Jordan*, care o aduc la o formă „aproape diagonală“, în sensul că, în afara
elementelor de pe diagonala principală, mai găsim și elemente egale cu 1 deasupra
diagonalei. De exemplu, o matrice de forma:
```{math}
A = \begin{pmatrix}
3 & 1 & 0 & 0 \\
0 & 3 & 0 & 0 \\
0 & 0 & 5 & 1 \\
0 & 0 & 0 & 5
\end{pmatrix}
```
este un exemplu de formă canonică Jordan, care conține două blocuri Jordan de 
dimensiune 2: cei doi minori $ \begin{pmatrix} 3 & 1 \\ 0 & 3 \end{pmatrix} $
și $ \begin{pmatrix} 5 & 1 \\ 0 & 5 \end{pmatrix} $.

Pentru o matrice de dimensiune arbitrară, putem avea mai multe blocuri Jordan,
eventual de dimensiuni diferite. Pe diagonala principală a matricei găsim
tot valorile sale proprii, însă dimensiunea și numărul blocurilor sînt determinate
de alți factori, pe care îi vom întîlni pe parcursul calculului din această
secțiune.

Există mai multe moduri de a aduce o matrice la această formă, mai mult sau mai
puțin eficiente sau dificile din punct de vedere tehnic. Prezentarea noastră
se va baza pe Appendix B din {cite}`strang`.

**#TODO**
