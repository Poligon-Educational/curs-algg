# Descompuneri matriceale

Tema acestei secțiuni este să explorăm modalități de a descompune matrice.
Motivul pentru care sîntem interesați de acest subiect seamănă foarte mult
cu cel din cadrul discuției privitoare la 
{ref}`diagonalizare sau, mai general, la vectori și valori proprii<sec-vvp-motivatie>`:
din punct de vedere computațional, calculele sînt mai simple atunci cînd lucrăm
cu obiecte descompuse. Diagonalizarea este metoda cea mai eficientă de a simplifica
forma unei matrice și calculele ulterioare, dar nu orice matrice poate fi adusă la
forma diagonală. Apoi, forma canonică Jordan este dificil de calculat, în general
și există metode care nu doar simplifică matricea inițială, dar componentele pe care
le vom folosi au semnificații aparte, uneori utile chiar ca atare.

Mai trebuie să adăugăm că în majoritatea situațiilor practice, astăzi avem nevoie
foarte rar de a face aceste calcule manual și detaliat. Mai mult, pot exista
destule cazuri practice -- precum cele întîlnite în inteligența artificială -- unde
matricele cu care avem de lucrat sînt foarte mari, cu sute sau chiar mii de linii și 
coloane. Dar sîntem de părere că o înțelegere teoretică prealabilă, urmată de cîteva
exemple de calcul manual și chiar implementare de la zero într-un limbaj de programare
arată mai bine modul de funcționare al algoritmilor și în același timp, ne indică
și eventuale metode de optimizare.

## Descompunerea cu valori singulare (SVD)
Prezentarea noastră urmează §10.3 din {cite}`compgraph`.

Această descompunere matriceală are numeroase aplicații în grafică și
în prelucrarea imaginilor. Fiindcă detaliile tehnice pot părea contraintuitive
la prima vedere, începem cu explicația intuitivă.

Teorema de descompunere a valorilor singulare (eng. *singular value decomposition*, SVD)
afirmă că dacă avem o transformare geometrică (aplicație liniară, în general), atunci,
făcînd eventual schimbări de bază în spațiile-domeniu de definiție și codomeniu ale
aplicației, atunci aceasta se reduce la o rescalare, uniformă sau nu. Cu alte cuvinte,
făcînd această schimbare de baze, orice transformare aplicată unui vector devine
o înmulțire cu scalari -- uniformă, dacă se folosește același scalar pentru toate
componentele vectorului sau neuniformă, în caz contrar.

Definiția valorilor singulare este una destul de abstractă:
```{prf:definition}
:label: def-svd

Se numește *valoare singulară* a unei matrice $ M $ numărul $ \sqrt{\lambda} $,
unde $ \lambda \in \sigma(M^T \cdot M) $[^vp-mmt].
```
[^vp-mmt]: Se poate arăta că valorile proprii ale unei matrice obținute
sub forma $ M^t \cdot M $ sînt mereu nenegative, deci valorile singulare sînt
corect definite.

Vom vedea unde apare exact această noțiune în descompunerea noastră.

Să mai dăm și teorema principală, la fel de abstractă, după care vom vedea
cum se obține această descompunere și cum o putem înțelege cît mai ușor.

```{prf:theorem}
:label: thm-svd

Fie $ M \in M_{n,k}(\mathbb{R}) $ o matrice oarecare. Atunci există
3 matrice $ U, D, V $ astfel încît $ M = UDV^t $, unde:
- $ U \in M_{n,r}(\mathbb{R}) $, cu $ r = \min(n, k) $ este o matrice care
are *coloane ortonormale*;
- $ D \in M_r(\mathbb{R}) $ este o matrice diagonală;
- $ V \in M_{r,k}(\mathbb{R}) $ este o matrice care are *coloane ortonormale*.

Prin convenție, elementele nenule din $ D $ se scriu în ordine descrescătoare
și se poate arăta că sînt tocmai valorile singulare ale matricei $ M $.

Mai mult, în cazul particular cînd $ n = k $, deci matricele $ U, V $ sînt pătratice,
ele descriu o schimbare de coordonate în domeniu și respectiv codomeniu, iar
$ D $ reprezintă o rescalare, uniformă dacă valorile singulare sînt egale și
neuniformă în caz contrar.
```

Procedura de obținere a descompunerii este prezentată sumar și clar în
{cite}`cismas`, p. 4:
- se calculează valorile singulare $ \sigma_i $, ca fiind $ \sigma_i = \sqrt{\lambda_i} $,
cu $ \lambda_i \in \sigma(M^t M) $;
- vectorii $ v_i $, care reprezintă coloanele matricei $ V $, sînt vectori
proprii ortonormați, corespunzători valorilor proprii $ \lambda_i $ de mai sus:
	+ dacă sînt deja ortonormați, îi folosim direct pentru a alcătui matricea $ V $;
	+ altfel, se obțin vectorii și se aplică {ref}`procedura Gram-Schmidt<sec-gram-schmidt>` pentru a-i ortonorma;
- vectorii-coloană $ u_i $ din matricea $ U $ se obțin cu formula $ u_i = \dfrac{1}{\sigma_i} Av_i $.

---

În cazul particular cînd $ n = k $, adică atunci cînd toate matricele sînt
pătratice, putem înțelege această descompunere intuitiv astfel. Presupunem
că avem o aplicație liniară $ T : \mathbb{R}^n \to \mathbb{R}^n $, dată
prin matricea $ M $, adică $ T(x^t) = Mx^t, \forall x \in \mathbb{R}^n $.

Dacă descompunem $ M $ sub forma SVD, i.e. $ M = UDV^t $, rezultă
$ T(x^t) = U D V^t x^t $ și, succesiv, putem gîndi transformările astfel:
- înmulțirea la stînga cu $ V^t $ înseamnă o schimbare de coordonate;
- înmulțirea rezultatului cu $ D $, care este matrice diagonală, înseamnă
o rescalare (uniformă sau nu);
- înmulțirea rezultatului cu $ U $ la stînga înseamnă o nouă rescalare.

Rezultă că întreaga acțiune a lui $ T $ se reduce la transportul vectorului
într-un spațiu izomorf cu $ \mathbb{R}^n $, dar cu altă bază, prin matricea
de trecere $ V $, apoi în acel spațiu, vectorul se rescalează și în fine
rezultatul este transportat tot într-un spațiu izomorf cu $ \mathbb{R}^n $,
dar cu altă bază, prin matricea $ U $.

O astfel de înțelegere intuitivă justifică afirmația de la începutul secțiunii,
că folosind SVD, putem privi o transformare liniară ca pe o rescalare, împreună
cu transportul în spații izomorfe, dar de baze diferite.

### Exemplu de calcul
Fie matricea $ A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \\ 1 & 0 \end{pmatrix} $.

Determinăm descompunerea cu valori singulare. 

Mai întîi, determinăm valorile singulare ca fiind valorile proprii ale matricei:
```{math}
A^t \cdot A = %
\begin{pmatrix}
1 & 0 & 1 \\
1 & 1 & 0
\end{pmatrix} \cdot %
\begin{pmatrix}
1 & 1 \\
0 & 1 \\
1 & 0
\end{pmatrix} = %
\begin{pmatrix}
2 & 1 \\
1 & 2
\end{pmatrix} = M
```
Calculăm polinomul caracteristic:
```{math}
P_M(X) = \det(M - XI_2) = \begin{vmatrix} 2-X & 1 \\ 1 & 2-X \end{vmatrix} = X^2 - 4X + 3
```
Rezultă $ \lambda_1 = 3 $ și $ \lambda_2 = 1 $ (le-am scris în ordine descrescătoare, 
în pregătire pentru matricea $ D $). Așadar, valorile singulare sînt:
```{math}
\sigma_1 = \sqrt{\lambda_1} = \sqrt{3}, \quad \sigma_2 = \sqrt{\lambda_2} = 1.
```
Deci știm componenta diagonală, $ D = \mathrm{diag}(\sqrt{3}, 1) $.

Vectorii proprii asociați $ \lambda_1 $ sînt de forma $ \{ (\alpha, \alpha) \in \mathbb{R}^2 \} $,
deci o bază în subspațiul invariant $ V_{\lambda_1} $ este $ \{ v_1 = (1, 1) \} $.

Apoi, pentru $ \lambda_2 $ găsim vectorii proprii de forma $ \{ (\alpha, -\alpha) \in \mathbb{R}^2 \} $,
deci o bază în $ V_{\lambda_2} $ este $ \{ v_2 = (1, -1) \} $.

Observăm că $ v_1 \perp v_2 $, deci mai trebuie doar să-i normăm. Avem: $ || v_1 || = \sqrt{2} $,
deci schimbăm $ v_1 $ cu $ \dfrac{1}{\sqrt{2}} (1, 1) $ și similar, $ ||v_2|| = \sqrt{2} $,
deci schimbăm $ v_2 $ cu $ \dfrac{1}{\sqrt{2}} (1, -1) $.

Din formula de calcul pentru $ u_{1,2} $, avem:
```{math}
\begin{align*}
  u_1 &= \dfrac{1}{\sigma_1} Av_1 = \dfrac{1}{\sqrt{3}} \cdot \begin{pmatrix} 1 & 1 \\ 0 & 1 \\ 1 & 0 \end{pmatrix} \cdot %
		 \begin{pmatrix} 1/\sqrt{2} & 1/\sqrt{2} \end{pmatrix} = \begin{pmatrix} \sqrt{6}/3 \\ \sqrt{6}/6 \\ \sqrt{6}{6} \end{pmatrix} \\
  u_2 &= 1 \cdot \begin{pmatrix} 1 & 1 \\ 0 & 1 \\ 1 & 0 \end{pmatrix} \cdot \begin{pmatrix} 1/\sqrt{2} \\ -1/\sqrt{2} \end{pmatrix} = %
		 \begin{pmatrix} 0 \\ -\sqrt{2}/2 \\ -\sqrt{2}/2 \end{pmatrix}
\end{align*}
```
În fine, descompunerea finală este:
```{math}
A = \begin{pmatrix}
1 & 1 \\
0 & 1 \\
1 & 0
\end{pmatrix} \cdot %
\begin{pmatrix}
\sqrt{6}/3 & 0 \\
\sqrt{6}/6 & -\sqrt{2}/2 \\
\sqrt{6}/6 & \sqrt{2}/2
\end{pmatrix} \cdot %
\begin{pmatrix}
\sqrt{3} & 0 \\
0 & 1 
\end{pmatrix} \cdot %
\begin{pmatrix}
1/\sqrt{2} & 1/\sqrt{2} \\
1/\sqrt{2} & -1/\sqrt{2}
\end{pmatrix}
```

## Eliminare gaussiană
Metoda eliminării gaussiene este una care se dovedește foarte puternică
pentru calcule matriceale și aplicații în sisteme liniare. Avantajul ei este
că se bazează pe așa-numitele *transformări elementare* ale liniilor sau coloanelor
unei matrice, adică acele operații care nu schimbă determinantul sau rangul matricei.
Totodată, pașii pe care îi facem sînt ușor de implementat pe computer, dar procedura
este, în general, laborioasă.

Ideea de bază este aceasta:
- se pornește cu o matrice oarecare -- pătratică sau nu;
- se aplică transformări elementare, prin operații cu linii[^op-linii], pînă cînd matricea
se aduce la formă triunghiulară. În această formă, ea are elemente nule deasupra sau
dedesubtul diagonalei principale (după caz, adică dacă este *inferior*, respectiv *superior*
*triunghiulară*);
- pașii de mai sus se pot aplica pentru orice matrice, iar pentru unele dintre ele,
se poate merge mai departe pînă cînd se obține o *matrice diagonală*.

```{note}
Atunci cînd facem operații elementare cu linii într-o matrice, vom folosi
următoarele două convenții:
- notația $ \alpha L_a + \beta L_b $ înseamnă că linia $ a $ se modifică
prin înmulțirea cu un scalar $ \alpha $ și adunarea cu elementele liniei $ b $,
înmulțite cu $ \beta $. De exemplu, $ 2L_2 - L_3 $ înseamnă că linia a doua se 
modifică și i se dublează elementele, după care se scad elementele liniei 3
(linia 3 nu se modifică!). Putem avea chiar și notații precum $ \dfrac{1}{2} L_1 $,
ceea ce înseamnă că elementele liniei 1 se înjumătățesc;
- pentru claritate, vom scrie transformările explicite, însă matricele care se obțin
în procedura eliminării gaussiene *nu sînt egale* cu cea de pornire, ci doar au
același determinant (sau rang) cu ele. De aceea, nu vom folosi semnul de egalitate
și vom scrie, de pildă $ A \xrightarrow{2L_1} B $, pentru a înțelege că matricea $ A $
se modifică prin dublarea elementelor liniei 1 și se ajunge la matricea $ B $.
```

```{note}
Transformările pe care le facem *nu sînt unice*, nici neapărat optime.
Aici rezidă simplitatea metodei lui Gauss: este ușor de implementat și este destul
de evident care este pasul următor, însă nu neapărat eficient.
```

[^op-linii]: Conform proprietăților determinanților, putem face operații fie cu linii,
fie cu coloane, fără ca valoarea determinantului să se schimbe. Însă, dacă vrem să
aplicăm eliminarea gaussiană pentru rezolvarea sistemelor liniare, de exemplu, operațiile
cu linii ar corespunde operațiilor între ecuații, în timp ce operațiile cu coloane ar
corespunde operațiilor între variabile. A doua variantă nu este permisă, evident (nu are sens).

În această formă, determinantul, rangul sau diverse aplicații, precum cele din studiul
sistemelor liniare, sînt ușor de calculat.

---

Să luăm cazul cel mai des întîlnit, cel puțin în problemele de geometrie.
Pornim cu o matrice pătratică $ A = \begin{pmatrix} 1 & -1 & 2 \\ 3 & 1 & 2 \\ 2 & -1 & 1 \end{pmatrix} $.
Scopul este să aducem această matrice la formă superior triunghiulară și, eventual, diagonală,
folosind doar operații elementare cu linii.

Se alege cîte un element din matrice pe care vrem să-l prelucrăm la pasul curent.
În termeni de specialitate, acesta se numește *pivot*. De obicei, pivoții se aleg
succesiv, pe coloane. În acest caz, se începe cu pivotul 1, care este primul element
de pe prima coloană a matricei. Acesta face parte din diagonală, deci este permis să
fie nenul, așa că mergem mai departe. Alegem acum pivotul 3, care este al doilea element
al primei coloane. Fiind sub diagonală, vrem să-l anulăm, făcînd operații cu linii.
De exemplu, putem aplica transformarea $ L_2 - 3L_1 $ și obținem:
```{math}
\begin{pmatrix} 
1 & -1 & 2 \\ 
3 & 1 & 2 \\ 
2 & -1 & 1 
\end{pmatrix} \xrightarrow{L_2 - 3L_1} %
\begin{pmatrix}
1 & -1 & 2 \\
0 & 4 & -4 \\
2 & -1 & 1
\end{pmatrix}
```
Următorul pivot este ultimul element al primei coloane, 2. Îl putem anula cu transformarea
$ L_3 - 2L_1 $ și obținem:
```{math}
\begin{pmatrix}
1 & -1 & 2 \\
0 & 4 & -4 \\
2 & -1 & 1
\end{pmatrix} \xrightarrow{L_3 - 2L_1} %
\begin{pmatrix}
1 & -1 & 2 \\
0 & 4 & -4 \\
0 & 1 & -3
\end{pmatrix}
```
Am terminat cu prima coloană, așa că alegem acum pivoții de pe coloana a doua.
Mai adăugăm că, pentru simplificare, putem alege la orice moment și să împărțim
sau să înmulțim elementele unei linii cu o constantă. În cazul de față, ar fi binevenit
să aplicăm transformarea $ \dfrac{1}{4} L_2 $.
Continuăm, deci:
```{math}
\begin{align*}
  \begin{pmatrix}
    1 & -1 & 2 \\
	0 & 4 & -4 \\
	0 & 1 & -3
  \end{pmatrix} &\xrightarrow{\dfrac{1}{4} L_2} %
  \begin{pmatrix}
  1 & -1 & 2 \\
  0 & 1 & -1 \\
  0 & 1 & -3
  \end{pmatrix} \xrightarrow{L_1 + L_2} %
  \begin{pmatrix}
  1 & 0 & 1 \\
  0 & 1 & -1 \\
  0 & 1 & -3
  \end{pmatrix} \\
  &\xrightarrow{L_3 - L_2} %
  \begin{pmatrix}
  1 & 0 & 1 \\
  0 & 1 & -1 \\
  0 & 0 & -2
  \end{pmatrix} \xrightarrow{L_1 + \dfrac{1}{2} L_3} %
  \begin{pmatrix}
  1 & 0 & 0 \\
  0 & 1 & -1 \\
  0 & 0 & -2
  \end{pmatrix} \\
  &\xrightarrow{\dfrac{1}{2}L_3 \text{ și } L_2 - L_3} %
  \begin{pmatrix}
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & 0 & -1
  \end{pmatrix} = B
\end{align*}
```
și am terminat. Remarcăm că $ B $ este o matrice diagonală și
$ \det B = -1 $, ceea ce înseamnă că și $ \det A = -1 $.

O altă aplicație concretă ar fi să considerăm $ A $ ca matricea unui sistem liniar,
de exemplu:
```{math}
\begin{cases}
  x - y + 2z &= 1 \\
  3x + y + 2z &= 4 \\
  2x - y + z &= 1
\end{cases}
```
În acest caz, se parcurg pașii de mai sus folosind *matricea extinsă*, $ \overline{A} $
și obținem succesiv:
```{math}
\begin{align*}
  \overline{A} &= \begin{pmatrix} 1 & -1 & 2 & 1 \\ 3 & 1 & 2 & 4 \\ 2 & -1 & 1 & 1 \end{pmatrix} \\
			   &\xrightarrow{L_2 - 3L_1} %
			     \begin{pmatrix}
				   1 & -1 & 2 & 1 \\
				   0 & 4 & -4 & 1 \\
				   2 & -1 & 1 & 1 
			     \end{pmatrix} \xrightarrow{L_3 - 2L_1} %
				 \begin{pmatrix}
				 1 & -1 & 2 & 1 \\
				 0 & 4 & -4 & 1 \\
				 0 & 1 & -3 & -1
				 \end{pmatrix} \\
			 &\xrightarrow{\dfrac{1}{4} L_2} %
			   \begin{pmatrix}
			     1 & -1 & 2 & 1 \\
				 0 & 1 & -1 & 1/4 \\
				 0 & 1 & -3 & -1
			   \end{pmatrix} \xrightarrow{L_1 + L_2} %
			   \begin{pmatrix}
			     1 & 0 & 1 & 5/4 \\
				 0 & 1 & -1 & 1/4\\
				 0 & 1 & -3 & -1
			   \end{pmatrix} \\
		     &\xrightarrow{L_3 - L_2} %
			   \begin{pmatrix}
			     1 & 0 & 1 & 5/4 \\
				 0 & 1 & -1 & 1/4 \\
				 0 & 0 & -2 & -5/4
			   \end{pmatrix} \xrightarrow{L_1 + \dfrac{1}{2} L_3} %
			   \begin{pmatrix}
			     1 & 0 & 0 & 11/8 \\
				 0 & 1 & -1 & 1/4 \\
				 0 & 0 & -2 & -5/4
			   \end{pmatrix} \\
		     &\xrightarrow{\dfrac{1}{2}L_3 \text{ și } L_2 - L_3} %
			   \begin{pmatrix}
			     1 & 0 & 0 & 11/8 \\
				 0 & 1 & 0 & 7/8 \\
				 0 & 0 & -1 & -5/8
			   \end{pmatrix}
\end{align*}
```
Dacă ne uităm acum la ce sistem ar corespunde această ultimă matrice -- sistem care
va fi echivalent cu cel de pornire, întrucît operațiile cu linii corespund operațiilor
cu ecuații, care sînt permise, ajungem direct la soluția lui:
```{math}
\begin{cases}
  x &= 11/8 \\
  y &= 7/8 \\
  -z &= -5/8 \Rightarrow z = 5/8
\end{cases}
```

---

Conform {cite}`matalg`, procedura se poate formaliza și folosind înmulțirea cu matrice.
Preluăm exemplul de la p. 151.

Presupunem că avem o matrice $ A = (a_{ij})_{1 \leq i,j \leq 4} \in M_4(\mathbb{R}) $
și definim numerele $ \ell_{i1} = \dfrac{a_{i1}}{a_{11}}, \forall 1 \leq i \leq 4 $, 
numite *multiplicatori*. Apoi definim matricea:
```{math}
L_1 = \begin{pmatrix}
1 & 0 & 0 & 0 \\
-\ell_{21} & 1 & 0 & 0 \\
-\ell_{31} & 0 & 1 & 0 \\
-\ell_{41} & 0 & 0 & 1
\end{pmatrix}
```
Se poate vedea că dacă înmulțim matricea $ A $ la stînga cu $ L_1 $, obținem prima
coloană în forma cautată:
```{math}
L_1 A = 
\begin{pmatrix}
a_{11} & a_{12} & a_{13} & a_{14} \\
0 & a'_{22} & a'_{23} & a'_{24} \\
0 & a'_{32} & a'_{33} & a'_{34} \\
0 & a'_{42} & a'_{43} & a'_{44}
\end{pmatrix}
```
Putem continua apoi, definind alți multiplicatori, corespunzători coloanei
a doua: $ \ell_{i2} = \dfrac{a'_{i2}}{a'_{22}}, 3 \leq i \leq 4 $, apoi
definim matricea:
```{math}
L_2 = \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & -\ell_{32} & 1 & 0 \\
0 & -\ell_{42} & 0 & 1 
\end{pmatrix}
```
și înmulțim la stînga cu $ L_2 $:
```{math}
L_2L_1A =
\begin{pmatrix}
a_{11} & a_{12} & a_{13} & a_{14} \\
0 & a'_{22} & a'_{23} & a'_{24} \\
0 & 0 & a^{''}_{33} & a^{''}_{34} \\
0 & 0 & a^{''}_{43} & a^{''}_{44} 
\end{pmatrix}
```
În fine, definim $ \ell_{43} = \dfrac{a^{''}_{43}}{a^{''}_{33}} $ și matricea:
```{math}
L_3 = \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & -\ell_{43} & 1
\end{pmatrix}
```
și ajungem la rezultatul căutat prin înmulțire cu $ L_3 $ la stînga:
```{math}
L_3L_2L_1A = \begin{pmatrix}
a_{11} & a_{12} & a_{13} & a_{14} \\
0 & a'_{22} & a'_{23} & a'_{24} \\
0 & 0 & a^{''}_{33} & a^{''}_{34} \\
0 & 0 & 0 & a^{'''}_{44}
\end{pmatrix}
```

Evident, procedura poate fi generalizată și formalizată, dar ne vom opri aici,
considerînd că exemplele oferite sînt destul de clare.

## Descompunere LU
Direct din eliminarea gaussiană putem obține și forma LU a unei matrice,
care este alcătuită din:
- o matrice inferior (eng. *lower*) triunghiulară, $ L $;
- o matrice superior (eng. *upper*) triunghiulară, $ U $.
Descompunerea LU afirmă că există două matrice cu aceste proprietăți astfel
încît dată o matrice $ A $, ea se poate scrie $ A = L \cdot U $.

Să remarcăm din exemplul anterior că rezultatul obținut este o matrice superior
triunghiulară, fie ea $ U $, deci $ L_3 L_2 L_1 A = U $. Dar aceasta poate
fi scris și sub forma $ A = L_1^{-1} \cdot L_2^{-1} \cdot L_3^{-1} \cdot U $.
Calculînd concret membrul stîng, găsim că $ L = L_1^{-1} \cdot L_2^{-1} L_3^{-1} $
este de fapt o matrice inferior triunghiulară, alcătuită din multiplicatorii
$ \ell_{ij} $, adică:
```{math}
L = \begin{pmatrix}
1 & 0 & 0 & 0 \\
\ell_{21} & 1 & 0 & 0 \\
\ell_{31} & \ell_{32} & 1 & 0 \\
\ell_{41} & \ell_{42} & \ell_{43} & 1
\end{pmatrix},
```
ceea ce ne oferă forma finală.

E drept că, din punct de vedere practic, această descompunere este foarte greu
de găsit. Matricea $ L $ se compune ușor, cu ajutorul multiplicatorilor $ \ell_{ij} $,
care se definesc numai în funcție de elementele matricei de pornire $ A $.
Dar matricea superior triunghiulară $ U $ are o formă greu de ghicit de la început.

Putem, totuși, să aflăm matricea $ U $ folosindu-ne de următorul rezultat:

```{prf:theorem}
:label: thm-lu

Dacă matricea $ A $ este inversabilă (deci și pătratică) și dacă are o descompunere
$ LU $, atunci aceasta este unică.
```

Rezultă de aici că putem trata relația $ A = LU $ ca pe o ecuație din care să
aflăm matricea $ U = L^{-1} \cdot A $.

Totuși, trebuie să fim atenți, întrucît teorema afirmă că acest lucru este posibil
numai cînd:
- există o descompunere LU a matricei date;
- matricea de pornire este inversabilă.

Mai adăugăm că, în ipoteza că descompunerea LU există, faptul că $ A $ este
inversabilă este echivalent cu $ L $ și $ U $ să fie inversabile.

## Descompunere QR
O altă descompunere particulară a unei matrice $ A $ se numește *descompunerea QR*,
care are forma generală $ A = QR $, unde:
- $ Q $ este o *matrice ortogonală*, i.e. una în care coloanele și liniile, gîndite
ca vectori în spațiul euclidian corespunzător, sînt ortonormale. Echivalent, acest
lucru se poate scrie sub forma $ Q^t = Q^{-1} $, folosind produsul scalar euclidian
pe un spațiu de forma $ \mathbb{R}^n $;
- $ R $ este o matrice superior triunghiulară.

Descompunerea QR pentru o matrice pătratică se poate obține foarte ușor ca o consecință
a {ref}`algoritmului Gram-Schmidt<sec-gram-schmidt>`. Fie $ A \in M_n(\mathbb{R}) $
și fie coloanele matricei $ a_1, \dots, a_n $, ca vectori din $ \mathbb{R}^n $.

Aplicăm algoritmul Gram-Schmidt pentru acești vectori, ca să obținem un sistem ortonormat
$ \{ u_1, \dots, u_n \} $. Definim:
```{math}
\begin{align*}
  u_1 &= a_1 \\
  u_2 &= a_2 - \mathrm{proj}_{u_1} a_2 \\
  u_3 &= a_3 - \mathrm{proj}_{u_1} a_3 - \mathrm{proj}_{u_2} a_3 \\
      &\vdots \\
  u_n &= a_n - \sum_{k=1}^{n-1} \mathrm{proj}_{u_k} a_n,
\end{align*}
```
procedură în urma căreia obținem un sistem ortogonal. Pentru normare, definim
$ e_i = \dfrac{1}{||u_i||} u_i, \forall 1 \leq i \leq n $.

Vedem, însă, că putem gîndi problema și invers, adică să definim $ a_i $ în funcție
de $ e_i $ (implicit, $ u_i $), astfel:
```{math}
\begin{align*}
  a_1 &= \langle e_1, a_1 \rangle e_1 \\
  a_2 &= \langle e_1, a_2 \rangle + \langle e_2, a_2 \rangle e_2 \\
      &\vdots \\
  a_n &= \sum_{k=1}^n \langle e_k, a_n \rangle e_k,
\end{align*}
```
deoarece $ \langle e_i, a_i \rangle = || u_i || $.

Aceste relații pot fi puse sub forma matriceală $ A = QR $, unde $ Q $ este matricea
ce are drept coloane vectorii $ \{ e_1, e_2, \dots, e_n \} $, care sînt ortonormați,
iar $ R $ este următoarea matrice superior triunghiulară:
```{math}
R = \begin{pmatrix}
\langle e_1, a_1 \rangle & \langle e_1, a_2 \rangle & \langle e_1, a_3 \rangle & \dots & \langle e_1, a_n \rangle \\
0 & \langle e_2, a_2 \rangle & \langle e_2, a_3 \rangle & \dots & \langle e_2, a_n \rangle \\
0 & 0 & \langle e_3, a_3 \rangle & \dots & \langle e_3, a_n \rangle \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
0 & 0 & 0 & \dots & \langle e_n, a_n \rangle
\end{pmatrix},
```
care este exact forma căutată.
