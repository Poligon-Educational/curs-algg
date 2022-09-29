# Morfisme de spații vectoriale

## Definiție formală
Ideea pe care am folosit-o încă de cînd am vorbit pentru prima dată despre
{ref}`(substructuri și) morfisme<sec-substructuri-morfisme>` se păstrează.
În esență, este vorba despre *funcții* care respectă structura algebrică.
Iar în ce privește spațiile vectoriale, am văzut de asemenea că principala
operație este *combinația liniară*. Astfel că definiția de mai jos ar trebui
să fie ușor de anticipat și de înțeles:

```{prf:definition}
:label: def-apl-lin

Fie $ V, W $ două spații vectoriale peste același corp $ K $ și $ f : V \to W $
o funcție.

$ f $ se numește *morfism de spații vectoriale* sau *aplicație liniară*
dacă:

$$
  f(\alpha x + \beta y) = \alpha f(x) + \beta f(y), \quad \forall x, y \in V, \alpha, \beta \in K.
$$
```

Ca să fim riguroși, trebuie să atragem atenția că, deși am notat la fel
(cu adunare și juxtapunere în loc de înmulțire), operațiile care apar în ecuația
din definiție sînt diferite:
- $ \alpha x $ și $ \beta y $ din membrul stîng reprezintă înmulțirea cu scalari a vectorilor din $ V $;
- adunarea din membrul stîng este operația pe grupul de vectori $ (V, +) $;
- $ \alpha f(x) $ și $ \beta f(y) $ din membrul drept reprezintă înmulțirea cu scalari a vectorilor din $ W $;
- adunarea din membrul drept este operația pe grupul de vectori $ (W, +) $.

În ansamblu, egalitatea respectivă transmite o proprietate similară cu cea din cazul celorlalte
structuri, anume: fie că facem mai întîi o combinație liniară de vectori din $ V $ cu scalari,
pe care o trimitem prin $ f $ într-un vector din $ W $ sau mai întîi trimitem vectorii
din combinația din $ V $ prin $ f $ și apoi facem o combinație cu aceiași scalari în $ W $,
trebuie să obținem același lucru.

În general, în exerciții, aplicațiile liniare sînt ușor de folosit, dar nu la fel de ușor
de demonstrat că respectă proprietatea definitorie. O observație se impune, totuși:

```{important}
Atributul *liniar* care apare atît în cazul combinațiilor de vectori cu scalari, cît și
al morfismelor de spații vectoriale[^sp-lin] se referă la faptul că nu pot apărea decît
expresii liniare, adică expresii de gradul întîi.

De aceea, nu vom întîlni niciodată în spații vectoriale operații de ridicare la putere,
exponențiere sau altele în afară de expresii de gradul întîi -- adică înmulțiri cu scalari
și adunări.
```

Iată și un (contra)exemplu care să justifice această afirmație. Vom defini o funcție
între două spații vectoriale, funcție care va conține o expresie neliniară.
Vom vedea că nu poate fi morfism, identificînd și motivul, din calcul.

**Exemplu:** Fie $ f : \mathbb{R}^2 \to \mathbb{R}^2, f(x,y) = (x^2, y) $.
Am luat un exemplu foarte simplu, care nu modifică deloc a doua componentă, iar primeia
îi aplică o transformare neliniară -- ridicarea la pătrat.

Fie acum doi vectori din plan, $ v_1 = (x_1, y_1) $ și $ v_2 = (x_2, y_2) $ și
doi scalari reali $ \alpha, \beta \in \mathbb{R} $. Ar trebui să obținem că
$ f(\alpha v_1 + \beta v_2) = \alpha f(v_1) + \beta f(v_2) $. Calculăm:
```{math}
\begin{align*}
  f(\alpha v_1 + \beta v_2) &= f(\alpha x_1 + \beta x_2, \alpha y_1 + \beta y_2) = %
								((\alpha x_1 + \beta x_2)^2, \alpha y_1 + \beta y_2) \\
  \alpha f(v_1) + \beta f(v_2) &= \alpha (x_1^2, y_1) + \beta (x_2^2, y_2) = %
								(\alpha x_1^2 + \beta x_2^2, \alpha y_1 + \beta y_2)
\end{align*}
```
Cele două expresii sînt evident diferite, tocmai din cauza primei componente.
Cum vectorii și scalarii sînt arbitrari, avem, desigur:
```{math}
(\alpha x_1 + \beta x_2)^2 \neq \alpha x_1^2 + \beta x_2^2,
```
așadar $ f $ nu poate fi aplicație liniară (morfism de spații vectoriale).

```{note}
În principiu, cum $ \mathbb{R} $ însuși este un spațiu vectorial real, puteam lua un
exemplu chiar și mai simplu, anume o funcție $ f : \mathbb{R} \to \mathbb{R} $,
de pildă $ f(x) = x^2 $. Proprietatea de aplicație liniară ar însemna în acest
caz că $ f(\alpha x + \beta y) = \alpha f(x) + \beta f(y) $, adică
$ (\alpha x + \beta y)^2 = \alpha x^2 + \beta y^2 $, evident fals.
```

[^sp-lin]: Chiar spațiile vectoriale înseși se mai numesc *spații liniare*, tocmai pentru a
evidenția această proprietate. Numele de „vectorial“ amintește de exemplele prototipice, acelea
ale vectorilor din plan, în timp ce atributul „liniar“ este mai precis, arătînd că putem face
doar operații de gradul întîi.

Această observație ne ajută să realizăm că, dacă vrem să construim un morfism de spații
vectoriale, neapărat trebuie să folosim doar expresii de gradul întîi. Ceea ce, în același timp,
este și natural: oricum nu avem definită o operație de *înmulțire între vectori*, astfel că nu
am ști ce înseamnă ridicarea la pătrat în cazul unui vector. Însă în ce privește scalarii, de exemplu,
are sens, cel puțin în principiu, o definiție de forma:
```{math}
f(v) = \alpha^2 v,
```
pentru un posibil morfism de spații vectoriale $ f : V \to W $ și $ \alpha $ un scalar fixat din $ K $.
Aceasta deoarece în corpul de scalari putem opera cu înmulțire. 

Sigur, numai faptul că avem de-a face cu o expresie de gradul întîi în cazul vectorilor
(adică nu apar înmulțiri de vectori sau puteri) nu garantează că o funcție este și morfism.
Iată un exemplu rezolvat pentru demonstrația completă.

**Exemplu:** Fie $ f : \mathbb{R}^3 \to \mathbb{R}^2, f(x, y, z) = (3x - y, x + 2z) $.
Arătăm că $ f $ este aplicație liniară, adică morfism de spații vectoriale (reale).

Definiția am scris-o în varianta explicită, pentru că avem nevoie să evidențiem componentele
(coordonatele) vectorilor. Astfel, ținînd cont de faptul că un vector $ v \in \mathbb{R}^3 $
înseamnă, de fapt, $ v = (x, y, z) $ și similar în cazul unui vector din $ \mathbb{R}^2 $,
care are două componente, am scris explicit definiția funcției.

Acum, ca să arătăm că $ f $ este morfism, folosim definiția. Luăm doi scalari arbitrari
din $ \mathbb{R} $, $ \alpha $ și $ \beta $ și doi vectori arbitrari din $ \mathbb{R}^3 $.
Fie aceștia $ v_1 = (x_1, y_1, z_1) $ și $ v_2 = (x_2, y_2, z_2) $.

Calculăm combinația liniară:
```{math}
\alpha v_1 + \beta v_2 = \dots = (\alpha x_1 + \beta x_2, \alpha y_1 + \beta y_2, \alpha z_1 + \beta z_2).
```

Acum trebuie să aplicăm $ f $ acestei expresii, iar acțiunea sa poate fi înțeleasă cel mai bine
interpretînd „în cuvinte“ definiția: se obține un vector cu 2 componente, în care prima
componentă este diferența între triplul primei componente și a doua componentă din vectorul inițial,
iar a doua componentă a rezultatului este suma între prima componentă și dublul celei de-a treia
componente din vectorul inițial.

Este mai util să înțelegem acțiunea astfel, pentru că acum, componentele au o altă formă.
Deci în combinația liniară de mai sus, avem un fel de corespondență de forma:
```{math}
\begin{align*}
  x &\mapsto \alpha x_1 + \beta x_2 \\
  y &\mapsto \alpha y_1 + \beta y_2 \\
  z &\mapsto \alpha z_1 + \beta z_2
\end{align*}.
```

Acestea fiind noile componente, găsim:
```{math}
\begin{align*}
  f(\alpha x_1 + \beta x_2, \alpha y_1 + \beta y_2, \alpha z_1 + \beta z_2) &= %
    (3(\alpha x_1 + \beta x_2) - (\alpha y_1 + \beta y_2), (\alpha x_1 + \beta x_2) + 2(\alpha z_1 + \beta z_2)) \\
    &= (3\alpha x_1 + 3\beta x_2 - \alpha y_1 - \beta y_2, \alpha x_1 + \beta x_2 + 2\alpha z_1 + 2\beta z_2).
\end{align*}
```

Această expresie alcătuiește membrul stîng al definiției aplicației liniare (termenul $ f(\alpha x + \beta y) $).

Pentru membrul drept, calculăm succesiv:
```{math}
\begin{align*}
  f(v_1) &= f(x_1, y_1, z_1) = (3x_1 - y_1, x_1 + 2z_1) \\
  f(v_2) &= f(x_2, y_2, z_2) = (3x_2 - y_2, x_2 + 2z_2) \Rightarrow \\
  \alpha f(v_1) + \beta f(v_2) &= \alpha(3x_1 - y_1, x_1 + 2z_1) + \beta(3x_2 - y_2, x_2 + 2z_2) \\
    &= (3\alpha x_1 - \alpha y_1 + 3\beta x_2 - \beta y_2, \alpha x_1 + 2\alpha z_1 + \beta x_2 + 2\beta z_2).
\end{align*}
```
Cu atenție, vom constata că cele două expresii coincid, așadar $ f $ este o aplicație liniară.

---

Am început chiar cu un exemplu de aplicație liniară între două spații vectoriale diferite
pentru a arăta cazul cel mai interesant, cînd se transformă vectori de un anumit tip în
vectori de alt tip. De pildă, putem avea și aplicații liniare $ M_2(\mathbb{R}) \to \mathbb{R}^3 $,
care transformă matrice în vectori din spațiul tridimensional sau aplicații liniare
$ \mathbb{R}_2[X] \to \mathbb{R}_{3}[X] $, care transformă polinoame de grad cel mult 2
în polinoame de grad cel mult 3.

Vom explora astfel de exemple ceva mai tîrziu, după ce mai introducem cîteva noțiuni importante
privitoare la aplicații liniare.

---

Mai adăugăm că, asemenea cazului morfismelor de grupuri sau inele, avem:

```{prf:definition}
:label: def-izomorfism

- Un morfism bijectiv se numește *izomorfism*. Dacă spațiile $ V $ și $ W $ sînt izomorfe, notăm
acest lucru cu $ V \simeq W $;
- Un morfism bijectiv în care domeniul de definiție și codomeniul coincid se numește *automorfism*.
```

## Nucleu, imagine
Tot ca în cazul general al morfismelor, avem noțiunile de *nucleu* și *imagine*, cu definițiile
și proprietățile așteptate.

```{prf:definition}
:label: def-ker-apl-lin

Fie $ f : V \to W $ un morfism de $ K $-spații vectoriale.

Se definește *nucleul* lui $ f $ ca fiind:

$$
  \mathrm{Ker}(f) = \{ v \in V \mid f(v) = 0_W \},
$$

adică mulțimea vectorilor din $ V $ a căror imagine este vectorul nul din $ W $.

Se definește *imaginea* lui $ f $ ca fiind:

$$
  \mathrm{Im}(f) = f(V) = \{ w \in W \mid \exists v \in V, f(v) = w \}
$$

adică mulțimea valorilor efectiv luate de $ f $.
```

```{prf:theorem}
:label: thm-ker-inj-apl-lin

Fie $ f : V \to W $ un morfism de $ K $-spații vectoriale. Atunci:
- $ f $ este injectiv dacă și numai dacă $ \mathrm{Ker}(f) = \{ 0_V \} $;
- $ f $ este surjectiv dacă și numai dacă $ \mathrm{Im}(f) = W $.
```

Și, un rezultat foarte util, a cărui demonstrație vă invităm să o schițați:

```{prf:theorem}
:label: thm-ker-subsp

Fie $ f : V \to W $ un morfism de $ K $-spații vectoriale. Atunci:
- $ \mathrm{Ker}f $ este subspațiu vectorial al lui $ V $;
- $ \mathrm{Im}f $ este subspațiu vectorial al lui $ W $.
```

Lucrul cu aplicații liniare, nucleu și imagine, împreună cu proprietățile lor oferă
rezultate mai spectaculoase decît în cazul grupurilor sau inelelor, deoarece structura
de spațiu vectorial este mai bogată.

Una dintre cele mai importante aplicații este aceasta:
```{prf:theorem}
:label: thm-apl-lin-indep

Fie $ f : V \to W $ o aplicație liniară de $ K $-spații vectoriale
și $ L $ un sistem liniar independent în $ V $, iar $ G $ un sistem de
generatori în $ V $.

- Dacă $ f $ este injectivă, atunci $ f(L) $ este sistem liniar independent în $ W $;
- Dacă $ f $ este surjectivă, atunci $ f(G) $ este sistem de generatori în $ W $;
- Dacă $ f $ este bijectivă și $ B $ este o bază a lui $ V $, atunci $ f(B) $ este o bază
a lui $ W $. Rezultă, în particular, în acest caz, că $ \dim V = \dim W $.
```

Demonstrația este utilă, deoarece ilustrează lucrul cu proprietăți importante:

```{prf:proof}
Presupunem că $ f $ este injectivă și:

$$
  L = \{ x_1, x_2, \dots, x_n \}, \quad %
  f(L) = \{ f(x_1), f(x_2), \dots, f(x_n) \}
$$

Pentru a arăta că $ f(L) $ este liniar independentă, prespunem că avem o combinație
liniară nulă în $ W $ de forma:

$$
  \alpha_1 f(x_1) + \alpha_2 f(x_2) + \dots + \alpha_n f(x_n) = 0_W
$$

Dar, folosind proprietățile aplicațiilor liniare, putem rescrie aceasta sub forma:

$$
  f(\alpha_1 x_1 + \alpha_2 x_2 + \dots + \alpha_n x_n) = 0_W \Rightarrow %
  \alpha_1 x_1 + \alpha_2 x_2 + \dots + \alpha_n x_n \in \mathrm{Ker}f.
$$

Cum $ f $ este, însă, injectivă, rezultă $ \mathrm{Ker}f = \{ 0_V \} $,
deci combinația lniiară respectivă -- care este acum de vectori din $ V $ --
trebuie să fie vectorul nul. Însă combinația folosește numai vectori din $ L $,
care este mulțime liniar independentă, ceea ce face ca toți scalarii $ \alpha_i $
să fie nuli $ 1 \leq i \leq n $, de unde rezultă că și $ f(L) $ este liniar
independentă.

Pentru sistemul de generatori, mai întîi notațiile:

$$
  G = \{ g_1, g_2, \dots, g_t \}, \quad f(G) = \{ f(g_1), f(g_2), \dots, f(g_t) \}.
$$

Fie acum $ w \in W $. Căutăm scalari $ \alpha_i, 1 \leq i \leq n $ astfel încît $ w $ 
se poate scrie ca o combinație liniară:

$$
  w = \alpha_1 f(g_1) + \alpha_2 f(g_2) + \dots + \alpha_t f(g_t).
$$

Dar cum $ f $ este surjectivă, rezultă că $ w \in \mathrm{Im}f $, deci $ w $ se poate
scrie ca $ f(v) = w $, pentru un anume $ v \in V $. În $ V $ avem sistemul de generatori
$ G $, rezultă că $ v $ se poate scrie ca o combinație liniară:

$$
  v = \beta_1 g_1 + \beta_2 g_2 + \dots + \beta_t g_t, \quad \beta_i \in K, 1 \leq i \leq t.
$$

Atunci nu avem decît să aplicăm morfismul $ f $ acestei egalități și să găsim:

$$
  \begin{align*}
    f(v) &= f(\beta_1 g_1 + \beta_2 g_2 + \dots + \beta_t g_t) \\
       w &= \beta_1 f(g_1) + \beta_2 f(g_2) + \dots + \beta_t f(g_t)
  \end{align*}
$$

și avem exact ceea ce căutam: scalarii $ \alpha_i, 1 \leq i \leq t $ sînt tocmai scalarii
$ \beta_i, 1 \leq i \leq t $.

A treia afirmație este o consecință directă a primelor două.
```

Toate afirmațiile teoremei anterioare pot fi făcute și reciproc și vă invităm să le formulați
și să le demonstrați.

Cu acestea, avem, în particular:

```{prf:corollary}
:label: cor-izom-dim

Două spații vectoriale sînt izomorfe dacă și numai dacă au aceeași dimensiune.
```

---

Acest ultim rezultat, deși este formulat ca un corolar, are o importanță deosebită.
El ne arată că, *pînă la un izomorfism*, este suficient să studiem un singur spațiu
vectorial de o dimensiune fixată.

În același timp, obținem imediat izomorfisme de forma:
```{math}
\mathbb{R}^4 \simeq M_2(\mathbb{R}) \simeq \mathbb{R}_3[X]
```
și putem trage o concluzie precum:

```{important}
Este suficient să studiem spațiile de forma $ \mathbb{R}^n $ pentru a înțelege
„toate“ spațiile vectoriale finit dimensionale.
```

Aceasta deoarece, de pildă, în loc de o matrice cu 2 linii și 2 coloane sau polinoame
de grad cel mult 3, putem lucra cu cvadrupluri de numere reale. Sau în loc de matrice
cu 3 linii și 3 coloane ori de polinoame de grad cel mult 8, putem lucra cu șiruri de
9 numere reale ș.a.m.d.

În continuare, încă o construcție unificatoare, care ne va arăta motivul pentru care
apar un fel de „coincidențe“ cînd lucrăm cu matrice în cazul spațiilor vectoriale.

## Matricea unei aplicații liniare
Legătura între spații vectoriale și calcul matriceal este una foarte strînsă.
Nu doar că orice spațiu vectorial finit dimensional poate fi gîndit ca un spațiu
de matrice[^sp-mat], dar și din punct de vedere computațional, există multe corespondențe
utile. De exemplu, produsul a două matrice (să le presupunem pătratice, de aceeași
mărime, pentru simplitate) se poate interpreta ca o combinație liniară a unor
scalari care alcătuiesc liniile primei matrice cu vectorii 1-dimensionali (scalarii)
care alcătuiesc coloanele celei de-a doua matrice.

O astfel de explicație este ușor forțată, însă legătura între *aplicarea unui morfism*
și *înmulțirea cu o matrice* este una foarte strînsă și riguroasă. Asupra acestui
concept ne vom concentra acum.

[^sp-mat]: Am spus deja că un spațiu vectorial de dimensiune $ n $ este, de fapt, izomorf
cu $ \mathbb{R}^n $. Dar putem face legătura și cu spații de matrice. De pildă,
un spațiu vectorial de dimensiune 6 este același lucru (pînă la un izomorfism) cu spațiul
$ M_{2,3}(\mathbb{R}) $ sau cu spațiul $ M_{3,2}(\mathbb{R}) $. De fapt, aici este vorba
despre niște subtilități aritmetice simple: dacă luăm $ n = 12 $, un număr cu mulți
divizori, atunci $ \mathbb{R}^{12} $ poate fi gîndit (pînă la un izomorfism) fie ca
$ M_{2,6}(\mathbb{R}) $, fie ca $ M_{6,2}(\mathbb{R}) $, fie ca $ M_{3,4}(\mathbb{R}) $,
fie ca $ M_{4,3}(\mathbb{R}) $ sau chiar drept cazurile extreme, $ M_{12,1}(\mathbb{R}) $
ori $ M_{1,12}(\mathbb{R}) $. Dacă $ n $ ar fi fost un număr prim, de exemplu $ n = 5 $
sau $ n = 7 $, atunci am fi putut obține doar cazurile degenerate de matrice: matrice-linie
sau matrice-coloană. Chiar și așa, însă, rămîne adevărat că un spațiu vectorial finit
dimensional poate fi privit (pînă la un izomorfism) ca un spațiu de matrice.

```{prf:definition}
:label: def-mat-apl

Fie $ f : V \to W $ o aplicație liniară și $ B_V $, respectiv $ B_W $ cîte o bază în $ V, W $.

Se numește *matricea aplicației $ f $ relativ la bazele $ B_V, B_W $*, notată
$ M_f^{B_V, B_W} $, matricea care are drept coloane coordonatele imaginilor
vectorilor din baza $ B_V $ în baza $ B_W $.
```

Exprimarea anterioară este destul de complicată și reprezintă un caz pe care o să-l întîlnim
destul de rar. Să îl ilustrăm, totuși.

**Exemplu:** Fie $ V = \mathbb{R}^2 $ și $ W = \mathbb{R}^3 $. Definim aplicația:
```{math}
f : V \to W, \quad f(a, b) = (2a - b, 2b - a, 3b), \forall (a, b) \in V.
```
Presupunem că am demonstrat că $ f $ este aplicație liniară (exercițiu!).

Tot pentru a ilustra cazul general, să luăm două baze, diferite de bazele canonice:
```{math}
B_V = \{ (1, -1), (0, 2) \}, \quad B_W = \{ (0, 1, 1), (-1, 2, 0), (1, 1, 1) \}.
```
Exercițiu: Demonstrați că $ B_V $ este bază în $ V $ și $ B_W $ este bază în $ W $.

Acum, conform definiției, trebuie să calculăm imaginile vectorilor din $ B_V $ prin $ f $,
iar vectorii rezultați să-i exprimăm în baza $ B_W $. Avem:
```{math}
\begin{align*}
  f(1, -1) &= (3, -4, -3) = w_1 \\
  f(0, 2) &= (-2, 4, 6) = w_2
\end{align*}
```
Trebuie, mai departe, să găsim coordonatele vectorilor $ w_1, w_2 $ în baza $ B_W $,
coordonate care devin coloanele matricei căutate. Calculul este simplu, dar laborios.
Trebuie să găsim, deci, scalarii $ \alpha_1, \beta_1, \gamma_1 $, respectiv
$ \alpha_2, \beta_2, \gamma_2 $ astfel încît:
```{math}
\begin{align*}
  w_1 &= (3, -4, -3) = \alpha_1 (0, 1, 1) + \beta_1 (-1, 2, 0) + \gamma_1 (1, 1, 1) = \dots = %
                      (-\beta_1 + \gamma_1, \alpha_1 + 2\beta_1 + \gamma_1, \alpha_1 + \gamma_1) \\
  w_2 &= (-2, 4, 6) = \alpha_2 (0, 1, 1) + \beta_2 (-1, 2, 0) + \gamma_2 (1, 1, 1) = \dots = %
                      (-\beta_2 + \gamma_2, \alpha_2 + 2\beta_2 + \gamma_2, \alpha_2 + \gamma_2) \\
\end{align*}
```
Vedem că, în esență, avem de rezolvat același sistem de ecuații, cu rezultate diferite:
```{math}
\begin{cases}
  -\beta_1 + \gamma_1 &= 3 \\
  \alpha_1 + 2\beta_1 + \gamma_1 &= -4 \\
  \alpha_1 + \gamma_1 &= -3
\end{cases} \quad \text{și} \quad
\begin{cases}
  -\beta_2 + \gamma_2 &= -2 \\
  \alpha_2 + 2\beta_2 + \gamma_2 &= 4 \\
  \alpha_2 + \gamma_2 &= 6
\end{cases}
```
Matricea ambelor sisteme este:
```{math}
A = \begin{pmatrix}
0 & -1 & 1 \\
1 & 2 & 1 \\
1 & 0 & 1
\end{pmatrix},
```
care este inversabilă, deci ambele sisteme sînt Cramer. *Acesta este și cazul general,*
*pentru că matricea unei aplicații liniare este unic definită.*

Soluțiile sînt:
```{math}
(\alpha_1, \beta_1, \gamma_1) = \left( -\dfrac{11}{2}, -\dfrac{1}{2}, \dfrac{5}{2} \right) \quad %
(\alpha_2, \beta_2, \gamma_2) = (9, -1, -3).
```

Așadar:
```{math}
M_f^{B_V, B_W} = \begin{pmatrix}
-11/2 & 9 \\
-1/2 & -1 \\
5/2 & -3
\end{pmatrix}
```

Cazul ilustrat este cel mai general, în care se folosesc baze oarecare, diferite
de bazele canonice. Însă în majoritatea cazurilor, se lucrează mult mai simplu.
Este, de aceea, potrivit să facem chiar aici o observație.

```{important}
Dacă nu se precizează altfel, vom lucra numai cu bazele canonice
în spațiile vectoriale studiate.

În plus, în acest caz, vom simplifica și notația pentru matricea unei
aplicații $ f $ în bazele canonice, scriind simplu $ M_f $.
```

Pentru cazul bazelor canonice, calculele se simplifică mult:

**Exemplu:** Fie aplicația:
```{math}
f : M_2(\mathbb{R}) \to \mathbb{R}_2[X], \quad %
f \begin{pmatrix} a & b \\ c & d \end{pmatrix} = (a - d) + bX + (2c - d)X^2.
```
Ca un exercițiu simplu, arătați că $ f $ este aplicație liniară.

Presupunem acum că lucrăm cu {ref}`bazele canonice<sec-baze-canonice>`. Calculăm:
```{math}
\begin{align*}
  f \begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} &= 1 - X^2 \\
  f \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} &= X \\
  f \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} &= 2X^2 \\
  f \begin{pmatrix} 0 & 0 \\ 0 & 1 \end{pmatrix} &= -X^2
\end{align*}
```
Dar, cum lucrăm cu bazele canonice, coordonatele vectorilor sînt foarte simplu de găsi:
```{math}
\begin{align*}
  1 - X^2 &= 1 \cdot 1 + 0 \cdot X + (-1) \cdot X^2 \\
  X &= 0 \cdot 1 + 1 \cdot X + 0 \cdot X^2 \\
  2X^2 &= 0 \cdot 1 + 0 \cdot X + 2 \cdot X^2 \\
  -X^2 &= 0 \cdot 1 + 0 \cdot X + (-1) \cdot X^2
\end{align*}
```
Deci obținem imediat:
```{math}
M_f = \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
-1 & 0 & 2 & -1
\end{pmatrix}
```

O observație importantă, care va ușura unele legături între aplicații liniare și calcule
matriceale, este următoarea:

```{important}
Dacă $ f : V \to W $ este o aplicație liniară, iar $ A = M_f $ este matricea sa în
bazele canonice, atunci pentru orice vector $ v \in V $, a calcula $ f(v) $ este
același lucru cu a înmulți matricea $ A $ cu vectorul-coloană dat de coordonatele
lui $ v $ în baza canonică a lui $ V $.
```

Iată un exemplu:
```{math}
f : \mathbb{R}^3 \to \mathbb{R}^2, \quad f(a, b, c) = (2a - 2c, b + c)
```
Matricea aplicației $ f $ în bazele canonice se obține imediat din:
```{math}
\begin{align*}
  f(1, 0, 0) &= (2, 0) \\
  f(0, 1, 0) &= (0, 1) \\
  f(0, 0, 1) &= (-2, 1)
\end{align*} \Rightarrow %
M_f = \begin{pmatrix}
  2 & 0 & -2 \\
  0 & 1 & 1
  \end{pmatrix}
```
Să luăm un vector oarecare, de exemplu $ v = (-2, 3, 4) \in \mathbb{R}^3 $.
Am afirmat că acalcula $ f(v) $ este același lucru cu a înmulți vectorul-coloană
$ v $ (care coincide cu vectorul coordonatelor sale, dat fiind că lucrăm cu bazele
canonice) cu matricea $ M_f $. Verificăm:
```{math}
f(v) = f(-2, 3, 4) = (-12, 7)
```
Apoi:
```{math}
\begin{pmatrix}
  2 & 0 & -2 \\
  0 & 1 & 1
\end{pmatrix} \cdot %
\begin{pmatrix}
-2 \\ 3 \\ 4
\end{pmatrix} = %
\begin{pmatrix}
-12 \\ 7
\end{pmatrix}
```

O astfel de legătură se va folosi atunci cînd vom calcula explicit nucleul și
imaginea unei aplicații liniare, de pildă, putînd lucra mai simplu, cu matricea
asociată aplicației în bazele canonice. O primă astfel de aplicație urmează.

## Teorema rang-defect
Înainte să putem prezenta aplicații mai sofisticate ale noțiunilor de pînă acum,
avem nevoie de un rezultat tehnic, ce se va dovedi foarte util în lucrul cu nucleul
și imaginea unei aplicații liniare. Mai întîi, o definiție de terminologie:

```{prf:definition}
:label: def-rang-def

Fie $ f : V \to W $ o aplicație liniară.
- Se numește *rangul* aplicației, notat $ \mathrm{rang}(f) $, dimensiunea (sub)spațiului
$ \mathrm{Im{f \leq W $.
- Se numește *defectul* aplicației, notat $ \mathrm{def}(f) $, dimensiunea (sub)spațiului
$ \mathrm{Ker}f \leq V $.
```

Denumirea nu este întîmplătoare și avem:
```{prf:theorem} Teorema rang-defect
:label: thm-rang-def

Fie $ f : V \to W $ o aplicație liniară. Atunci:
- $ \mathrm{rang}(f) = \mathrm{rang}M_f $;
- $ \mathrm{rang}(f) + \mathrm{def}(f) = \dim V $.
```

Imediat vom vedea aplicații și moduri de utilizare ale acestor noțiuni.

## Exercițiu rezolvat
În continuare, un exercițiu ceva mai sofisticat, cu rezolvare (aproape) completă.
Scopul acestei secțiuni este să punem cap la cap cît mai multe dintre noțiunile
întîlnite, împreună cu aplicațiile lor.

**Exemplu:** Fie aplicația liniară:
```{math}
f : \mathbb{R}^2 \to \mathbb{R}^3, \quad f(x, y) = (3x - 2y, 2x, y - x).
```

Calculăm matricea aplicației în bazele canonice:
```{math}
\begin{align*}
  f(1, 0) &= (3, 2, -1) \\
  f(0, 1) &= (-2, 0, 1)
\end{align*}
```
Acum, descompunerea celor doi vectori în baza canonică a lui $ \mathbb{R}^3 $ este
ca și făcută, întrucît componentele vectorilor sînt chiar coordonatele lor:
```{math}
\begin{align*}
  (3, 2, -1) &= 3 \cdot (1, 0, 0) + 2 \cdot (0, 1, 0) + (-1) \cdot (0, 0, 1) \\
  (-2, 0, 1) &= (-2) \cdot (1, 0, 0) + 0 \cdot (0, 1, 0) + 1 \cdot (0, 0, 1).
\end{align*}
```
Așadar, $ M_f = \begin{pmatrix} 3 & 2 \\ 2 & 0 \\ -1 & 1 \end{pmatrix} $.

Mai departe, să determinăm nucleul și imaginea aplicației. Prin definiție, avem:
```{math}
\mathrm{Ker}f = \{ (x, y) \in \mathbb{R}^2 \mid f(x, y) = (0, 0, 0) \}
```
Dacă aplicăm definiția lui $ f $, obținem succesiv:
```{math}
(3x - 2y, 2x, y - x) = (0, 0, 0) \Rightarrow %
\begin{cases}
  3x - 2y &= 0 \\
  2x &= 0 \\
  y - x &= 0
\end{cases}
```
și se vede imediat că sistemul are doar soluția trivială, deci $ \mathrm{Ker}f = \{ (0, 0) \} $.
O consecință este că $ f $ *este injectivă*.

Acum să determinăm și imaginea aplicației, $ \mathrm{Im}f $. Din definiție, avem:
```{math}
\mathrm{Im}f = \{ (x, y, z) \in \mathbb{R}^3 \mid \exists (a, b) \in \mathbb{R}^2, f(a, b) = (x, y, z) \}
```
Dar, conform teoremei rang-defect (teorema {prf:ref}`thm-rang-def`), putem calcula $ \dim \mathrm{Im}f $
ca $ \mathrm{rang}f = \mathrm{rang}M_f $. Se vede imediat că $ \mathrm{rang}M_f = 2 $, deoarece
avem un minor nenul, de exemplu $ \begin{vmatrix} 3 & 2 \\ 2 & 0 \end{vmatrix} = -4 $.

Așadar, $ \dim \mathrm{Im}f = 2 $, ceea ce poate rezulta și din teorema rang-defect,
întrucît cum $ \mathrm{Ker}f = \{ (0, 0, 0) \} $, rezultă $ \mathrm{def}f = \dim\mathrm{Ker}f = 0 $,
așadar $ \dim\mathrm{Im}f = \dim \mathbb{R}^2 = 2 $.

Dacă vrem să găsim și o bază în spațiul $ \mathrm{Im}f $, ne putem folosi de calculele deja făcute.
Știm deja că a calcula $ \mathrm{Im}f $ este același lucru cu a vedea mulțimea
de valori care se obțin prin înmulțirea vectorilor din $ \mathbb{R}^2 $ cu matricea $ M_f $.
Dar din calculul rangului, am văzut deja că cele două coloane ale matricei, pe care le putem înțelege ca
elemente ale $ \mathrm{Im}f $, deoarece:
```{math}
\begin{align*}
  f(1, 0) &= (3, 2, -1) \\
  f(0, 1) &= (-2, 0, 1)
\end{align*}
```
dau rangul, deci definesc vectori liniar independenți. În plus, cum $ \dim\mathrm{Im}f = 2 $,
rezultă din teorema alternativei că acești doi vectori formează chiar o bază. În concluzie:
```{math}
\mathrm{Im}f = \langle f(1, 0), f(0, 1) \rangle = \langle (3, 2, -1), (-2, 0, 1) \rangle
```
și avem o bază în $ \mathrm{Im}f $.

Remarcăm la acest punct că $ f $ *nu este surjectivă*, deoarece dimensiunea imaginii
nu coincide cu dimensiunea codomeniului. Acest lucru era de așteptat, deoarece cum $ f $
este injectivă, dacă ar fi și surjectivă, ar rezulta că este bijectivă, ceea ce ar face
ca $ \mathbb{R}^2 \simeq \mathbb{R}^3 $, care este evident fals (de exemplu, din motive
de dimensiune).

Suplimentar, deoarece $ \mathrm{Im}f \leq \mathbb{R}^3 $, dar este un subspațiu
strict (de dimensiune mai mică), să presupunem că vrem să găsim un alt subspațiu
$ T \leq \mathbb{R}^3 $ astfel încît $ \mathrm{Im}f \oplus T \simeq \mathbb{R}^3 $.
Un astfel de subspațiu $ T $ se numește **complement** al lui $ \mathrm{Im}f $ în
$ \mathbb{R}^3 $.

Din motive de dimensiune (e.g. teorema lui Grassmann, {prf:ref}`thm-grassmann`),
trebuie să avem $ \dim T = \dim \mathbb{R}^3 - \dim \mathrm{Im}f = 3 - 2 = 1 $.
Rezultă că $ T $ va avea în bază un singur vector din $ \mathbb{R}^3 $.
Fie acesta $ \{ (a, b, c) \} $. În plus, deoarece $ T $ alcătuiește sumă directă
cu $ \mathrm{Im}f $, rezultă:
```{math}
T \cap \mathrm{Im}f = \{ (0, 0, 0) \} \Rightarrow (a, b, c) \notin \mathrm{Im}f.
```
Nu este greu de văzut că există chiar o infinitate de posibilități pentru $ (a, b, c) $,
astfel că putem alege una oarecare. Fie, de exemplu, $ (a, b, c) = (1, 2, 3) $.

Ne validăm alegerea dacă:
- $ (1, 2, 3) \notin \mathrm{Im}f $;
- $ (1, 2, 3) $ împreună cu baza lui $ \mathrm{Im}f $ formează o bază pentru $ \mathbb{R}^3 $.

Să le luăm pe rînd: presupunem că $ (1, 2, 3) \in \mathrm{Im}f $. Ar însemna
că $ (1, 2, 3) $ se poate scrie ca un $ f(x, y) $, pentru un anume vector $ (x, y) \in \mathbb{R}^2 $.
Avem:
```{math}
f(x, y) = (3x - 2y, 2x, y - x) = (1, 2, 3) \Rightarrow %
\begin{cases}
  3x - 2y &= 1 \\
  2x &= 2 \\
  y - x &= 3
\end{cases}
```
Se vede imediat că sistemul nu este compatibil, deoarece din a doua ecuație am obține
$ x = 1 $, din a treia, $ y = 4 $, dar atunci prima nu este verificată: $ 3 - 8 \neq 1 $.

Așadar, nu se poate ca vectorul $ (1, 2, 3) $ să fie obținut ca imagine a unui vector
din $ \mathbb{R}^2 $ prin morfismul $ f $, deci $ (1, 2, 3) \notin \mathrm{Im}f $.

În fine, pentru a arăta că $ (1, 2, 3) $ completează baza imaginii lui $ f $ la o bază
a lui $ \mathbb{R}^3 $, nu avem decît să alcătuim matricea cu cei trei vectori și să
verificăm că are un determinant nenul:
```{math}
B = \begin{pmatrix}
3 & -2 & 1 \\
2 & 0 & 2 \\
-1 & 1 & 3
\end{pmatrix} \Rightarrow \det B = 12 \neq 0,
```
ceea ce trebuia demonstrat.

### Observații tehnice
Exercițiul exemplificat mai sus poate fi înțeles parțial și intuitiv,
cel puțin în ce privește proprietățile de injectivitate și surjectivitate ale
aplicației liniare.

În general, dacă $ f : V \to W $ este o aplicație liniară, putem fi în una dintre
următoarele situații:
- dacă $ \dim V < \dim W $, atunci $ f $ nu poate fi surjectivă. Aceasta deoarece
ar trebui ca $ f(V) = \mathrm{Im}f \simeq W $. Dar $ \dim \mathrm{Im}f $ se obține
din rangul $ M_f $,care, la rîndul ei, are coloanele obținute din imaginile bazei
canonice a lui $ V $, care are un număr strict mai mic de elemente decît baza lui $ W $.
- dacă $ \dim V > \dim W $, atunci $ f $ nu poate fi injectivă. Aceasta rezultă imediat
din teorema rang-defect: $ \dim \mathrm{Ker}f = \dim V - \dim \mathrm{Im}f $.
Dacă $ f $ ar fi injectivă, atunci $ \dim \mathrm{Ker}f = 0 $, deci $ \dim V = \dim \mathrm{Im}f $,
ceea ce este imposibil, pentru că $ \mathrm{Im}f \leq W $, deci 
$ \dim \mathrm{Im}f \leq \dim W < \dim V $.

Evident, acest lucru *nu* garantează că:
- dacă $ \dim V < \dim W $, atunci $ f $ este injectivă;
- dacă $ \dim V > \dim W $, atunci $ f $ este surjectivă;
- dacă $ \dim V = \dim W $, atunci $ f $ este bijectivă.

Aceste proprietăți depind de definiția explicită a funcției $ f $. Dar cel puțin în
primă fază, putem face observațiile menționate.

## Exerciții propuse
Pentru fiecare dintre funcțiile următoare, $ f : V \to W $:
- demonstrați că $ f $ este aplicație liniară;
- găsiți $ M_f $;
- găsiți $ \mathrm{Ker}f $ și $ \mathrm{Im}f $, precizîndu-le dimensiunea și găsiți-le cîte o bază;
- dacă $ f $ nu este bijectivă, găsiți complementul lui $ \mathrm{Ker} f $ în $ V $ sau, după caz,
complementul lui $ \mathrm{Im}f $ în $ W $.

1. $ V = W = \mathbb{R}^3, f(x, y, z) = (3x - y, 0, 2z - x) $.
2. $ V = \mathbb{R}^3, W = \mathbb{R}^2, f(x, y, z) = (x + y + z, 0) $.
3. $ V = \mathbb{R}^3, W = M_2(\mathbb{R}), f(x, y, z) = \begin{pmatrix} x & y \\ z & 0 \end{pmatrix} $.
4. $ V = M_2(\mathbb{R}), W = \mathbb{R}^3, f \begin{pmatrix} a & b \\ c & d \end{pmatrix} = (a + b + c + d, a, b) $.
5. $ V = \mathbb{R}_2[X], W = \mathbb{R}^3, f(a + bX + cX^2) = (2a - b, b + 3c, a - 3c) $.
6. $ V = M_2(\mathbb{R}), W = \mathbb{R}_{2}[X], f \begin{pmatrix} a & b \\ c & d \end{pmatrix} = (a + d) + (b + c)X $.
