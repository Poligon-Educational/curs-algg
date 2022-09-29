# Arii și volume

Pornind de la reprezentări și transformări, care reprezintă partea *calitativă*
a studiului spațiilor vectoriale, putem face și un studiu *cantitativ*. 
Astfel de probleme se referă la lungimi, arii, volume. Precum vom detalia într-o
altă secțiune, acestea sînt, de fapt, fațete ale aceluiași concept, cel de
*măsură*. Teoria măsurii este o ramură a matematicii care pornește de la
lungimi (în dimensiune 1), arii (în dimensiune 2) și volume (în dimensiune 3)
și le generalizează, le abstractizează către spații vectoriale și chiar obiecte
matematice de tipuri și dimensiuni arbitrare. De exemplu, vom vedea că în spațiile
vectoriale este suficient să lucrăm cu produse scalare și produse vectoriale pentru
a calcula aceste măsuri, însă pentru figuri *drepte*, cum sînt cuburi, paralelipipede,
prisme, piramide etc. Astfel de noțiuni se pot generaliza ușor în spații vectoriale
euclidiene, adică în care există un produs scalar, iar produsul vectorial se poate
generaliza către *produs exterior* fără mare dificultate.

Însă dacă avem nevoie de *curbe*, corpuri rotunde ș.a.m.d., este necesar să putem 
lucra cu instrumente de analiză matematică (limite, derivate, integrale), deci 
astfel de construcții sînt ceva mai restrictive.

Ne vom rezuma aici la a prezenta aplicații ale produsul vectorial pentru calculul
ariilor și volumelor.

Înainte de aceasta, facem observația că, în ce privește lungimile, cel puțin,
adică măsuri ale obiectelor 1-dimensionale. Aceasta se definește în spații euclidiene
așa cum am arătat {prf:ref}`aici<def-dist-eucl>`, unde am introdus *metrica* sau
*funcția distanță* dintre doi vectori ai unui spațiu euclidian. În particular,
aceasta se poate extinde la funcția *normă* imediat:
```{math}
||v|| = \sqrt{ \langle v, v \rangle}, \quad \forall v \in V,
```
unde $ V $ este un spațiu euclidian.

Mai departe, noțiunile anunțate de arie și volum.

Spațiile cu care vom lucra sînt în continuare $ \mathbb{R}^2 $ și $ \mathbb{R}^3 $,
ca spații reale.

## Produsul vectorial
Am văzut că doi vectori se pot „înmulți“ și pot produce un scalar cu ajutorul
produsului scalar. Acesta se poate defini pe orice spațiu vectorial dacă satisface
axiomele din definiția {prf:ref}`def-pr-scalar`.

Produsul vectorial, așa cum îl vom prezenta acum, este o altă variantă de a
înmulți doi vectori, dar se va aplica doar pentru vectori din $ \mathbb{R}^3 $.
Noțiunea poate fi generalizată către așa-numitul *produs exterior*, pe care îl
vom schița ceva mai încolo, însă pentru aplicațiile geometrice care ne interesează,
cazul standard din $ \mathbb{R}^3 $ este suficient.

Prin definiția, produsul vectorial al vectorilor din spațiu
$ \vec{a} = (a_1, a_2, a_3) = a_1 \vec{i} + a_2 \vec{j} + a_3 \vec{k} $
și $ \vec{b} = (b_1, b_2, b_3) = b_1 \vec{i} + b_2 \vec{j} + b_3 \vec{k} $
este un vector perpendicular pe planul determinat de $ \vec{a} $ și $ \vec{b} $.
De aceea avem nevoie să lucrăm în dimensiune 3, pentru că însăși operația de produs
vectorial „adaugă dimensiune“, ca să ne exprimăm informal: de la o figură bidimensională
(plan) se ajunge la una tridimensională (prismă).

Vectorul produs vectorial, notat $ \vec{a} \times \vec{b} $ se calculează cel mai ușor
printr-un determinant formal:
```{math}
\vec{a} \times \vec{b} = \begin{vmatrix} %
\vec{i} & \vec{j} & \vec{k} \\
a_1 & a_2 & a_3 \\
b_1 & b_2 & b_3
\end{vmatrix}
```
În unele cărți, determinantul este dezvoltat și se returnează direct componentele:
```{math}
\begin{align*}
  (\vec{a} \times \vec{b})_x &= a_2 b_3 - a_3 b_2 \\
  (\vec{a} \times \vec{b})_y &= -a_1 b_3 + a_3 b_1 \\
  (\vec{a} \times \vec{b})_z &= a_1 b_2 - a_2 b_1
\end{align*}
```

De asemenea, *modulul* (lungimea) vectorului calculat de produsul vectorial este dat de:
```{math}
|| \vec{a} \times \vec{b} || = ||\vec{a}|| \cdot ||\vec{b}|| \cdot \sin (\widehat{\vec{a}, \vec{b}}).
```

Mai adăugăm că, dacă produsul scalar se anulează atunci cînd vectorii sînt
ortogonali (perpendiculari), din cauza anulării funcției cosinus pentru
unghiuri de $ \dfrac{\pi}{2} $, în cazul produsului vectorial, nulitatea
lui asigură *paralelismul* vectorilor, întrucît sinusul se anulează
la unghiuri nule. Am obținut, deci:

```{important}
$$ \vec{a} || \vec{b} \Leftrightarrow \vec{a} \times \vec{b} = \vec{0}. $$
```

Rezultatul a fost notat ca fiind *vectorul* nul, pentru că produsul vectorial
returnează un vector. Evident că modulul vectorului nul este (*scalarul*) 0,
dar pentru rigoare, în egalitatea de mai sus apare vectorul nul.

### Orientare (Handedness)

Pînă acum, nu am vorbit deloc despre *orientarea* vectorului obținut ca produs 
vectorial. Aceasta deoarece în general, modul de determinare este ușor delicat.

În educația din România cel puțin, se folosește așa-numita *regulă a burghiului drept*,
sumarizată mai jos.

```{important}
Direcția produsului vectorial $ \vec{a} \times \vec{b} $ este perpendiculară pe planul
determinat de cei doi factori, iar sensul este acela în care s-ar deplasa un burghiu 
(șurub) cînd primul factor ($\vec{a}$) se rotește peste al doilea ($ \vec{b} $).
```

```{figure} ./img/burghiu.jpg
---
name: fig-burghiu
---
Regula burghiului drept
```

**#TODO: De găsit/făcut o poză mai bună**

Această regulă se mai numește și *regula mîinii drepte* (eng. *right hand rule*),
pentru că mai poate fi formulată astfel:
```{important}
Direcția produsului vectorial $ \vec{a} \times \vec{b} $ este perpendiculară pe planul
determinat de cei doi factori, iar sensul se obține astfel: se așează mîna dreaptă
astfel încît 

- arătătorul să fie paralel cu primul factor ($ \vec{a} $);
- degetul mijlociu să fie paralel cu al doilea factor ($ \vec{b} $).

Atunci degetul mare dă sensul produsului vectorial.
```

```{figure} ./img/right-hand-rule.png
---
name: fig-right-hand
---
Regula mîinii drepte (via [Wikipedia](https://en.wikipedia.org/wiki/Right-hand_rule))
```

Una dintre cele mai importante aplicații ale produsului vectorial este chiar în ce
privește orientarea versorilor bazei spațiului euclidian $ \mathbb{R}^3 $. Cu alte
cuvinte, versorii trebuie să respecte o regulă care seamănă cu cea de la 
{ref}`unitățile imaginare ale cuaternionilor<sec-multimea-h>`:
```{math}
\begin{align*}
  \vec{i} \times \vec{j} &= -\vec{j} \times \vec{i} = \vec{k}, \\
  \vec{j} \times \vec{k} &= -\vec{k} \times \vec{j} = \vec{i}, \\
  \vec{k} \times \vec{i} &= -\vec{i} \times \vec{k} = \vec{j}
\end{align*}
```
Aceste egalități ne arată, printre altele, că produsul vectorial este *anticomutativ*.

Se obține așa-numitul *sistem drept* (*right handed system*), ca în figura de mai jos.

```{figure} ./img/sistem-drept.png
---
name: fig-sistem-drept
---
Sistem drept de coordonate (*right handed*)
```

Alte sistem educaționale și chiar unele produse software, precum Unity,
Unreal Engine, DirectX, OpenGL folosesc și alte orientări, precum
*sistemele stîngi*. Pentru acestea, se folosește același raționament,
doar că mîna dreaptă este înlocuită cu mîna stîngă. În esență, aceasta
se reduce la inversarea axelor $ OX $ și $ OY $, plus, eventual, rotații
după axa $ OZ $ (în funcție de poziția particulară a mîinii. Imaginea
de mai jos, preluată din articolul {cite}`handedness`, arată o comparație
între sistemul stîng (subfigura (a)) și sistemul drept (subfigura (b)):
```{figure} ./img/right-left-handed-systems.png
---
name: fig-handedness
---
Sistemul stîng (a) și sistemul drept (b) de coordonate (via {cite}`handedness`)
```

```{important}
Dacă nu se precizează altfel, vom presupune că lucrăm cu un sistem drept
de coordonate.
```

Vizualizarea vectorului produs vectorial, împreună cu modulul și orientarea
sa atunci cînd este înmulțit cu vectorul unitate este reprezentată foarte
clar și simplu în animația de mai jos (via pagina de Twitter a Freya Holmér (`@FreyaHolmer`)):

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">cross product - visualized ⚔<br><br>the cross product A × B is a super useful way to take two 3D vectors, and get a third vector *perpendicular to both*, shown in blue (with its length shown in gray)! <a href="https://t.co/d3NZoLEUtq">pic.twitter.com/d3NZoLEUtq</a></p>&mdash; Freya Holmér (@FreyaHolmer) <a href="https://twitter.com/FreyaHolmer/status/1203059678705602562?ref_src=twsrc%5Etfw">December 6, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

![Produs vectorial vizualizat](https://twitter.com/i/status/120305967870560256)2

### Aplicații și generalizări
Produsul vectorial are 2 aplicații relevante în discuția de față: una pentru
calculul ariilor și una pentru calculul volumelor.

Să amintim o formulă elementară de liceu: Dat un triunghiu $ \Delta ABC $, aria
sa poate fi calculată ca $ \mathrm{A}(ABC) = \dfrac{1}{2} AB \cdot AC \cdot \sin \widehat{A} $.

```{figure} ./img/aria-triunghiului.png
---
name: fig-aria-triunghiului
---
Aria triunghiului $ \Delta ABC $
```

Acum, dacă considerăm un paralelogram $ ABCD $, el poate fi gîndit ca fiind alcătuit din
două triunghiuri, $ \Delta ABC $ și $ \Delta BCD $. Se poate arăta foarte ușor că cele două
triunghiuri sînt, de fapt, congruente, astfel că au arii egale și deci aria paralelogramului
este dublul ariei unuia dintre triunghiuri.

```{figure} ./img/aria-plg.png
---
name: fig-aria-plg
---
Aria paralelogramului $ ABCD $
```

Formula ar trebui să vă pară familiară. Dacă $ \vec{AB} $ și $ \vec{AD} $ sînt gîndiți
ca doi vectori din plan și dacă notăm $ AB = ||\vec{AB}|| $ și respectiv $ AD $ pentru
$ || \vec{AD} || $, atunci aria paralelogramului este egală cu norma (lungimea)
produsului vectorial $ \vec{AB} \times \vec{AD} $. Chiar dacă acest vector nu este
în planul paralelogramului, modulul său este de folos în acest context.

Am obținut, deci;

```{important}
Aria paralelogramului cu laturile neparalele $ a $ și $ b $ este egală cu modulul
produsului vectorial $ \vec{a} \times \vec{b} $.
```

O aplicație pentru calculul volumelor se obține introducînd **produsul mixt**
al trei vectori.

```{prf:definition}
:label: def-prod-mixt
Fie vectorii $ \vec{a}, \vec{b}, \vec{c} \in \mathbb{R}^3 $. Fie componentele lor
$ \{ a_i, b_i, c_i \}_{1 \leq i \leq 3} $.

Se definește *produsul lor mixt* ca fiind *scalarul* notat $ (\vec{a},\vec{b},\vec{c}) $,
definit prin:

$$
  (\vec{a}, \vec{b}, \vec{c}) = \vec{a} \cdot (\vec{b} \times \vec{c}) = %
  \begin{pmatrix}
    a_1 & a_2 & a_3 \\
	b_1 & b_2 & b_3 \\
	c_1 & c_2 & c_3
  \end{pmatrix}.
$$
```
    
Acum, ca să înțelegem produsul mixt din punct de vedere geometric, remarcăm că
produsul vectorial $ \vec{b} \times \vec{c} $, care trebuie calculat primul, 
returnează un vector perpendicular pe planul determinat de cei doi factori.
Să-l notăm cu $ \vec{v} $. În particular, cum perpendicularitatea pe plan înseamnă
perpendicularitate pe orice dreaptă (vector) din plan, rezultă că $ \vec{v} \perp \vec{b} $
și $ \vec{v} \perp \vec{c} $ (pînă la o eventuală translație). Apoi, anularea acestui 
produs mixt înseamnă că al treilea factor care apare, vectorul $ \vec{a} $, ar trebui 
să fie perpendicular pe acest rezultat provizoriu $ \vec{v} $[^pr-mixt-nul]. Dar cum $ \vec{v} $ 
era deja perpendicular pe planul $ (\vec{b}, \vec{c}) $ și chiar pe cei doi factori, 
dubla perpendicularitate înseamnă paralelism, deci $ \vec{a} || \vec{b} $ și 
$ \vec{a} || \vec{c} $. Concluzia este că vectorii $ \vec{a}, \vec{b} $ și $ \vec{c} $
sînt *coplanari* (se găsesc în același plan).

[^pr-mixt-nul]: Evident, produsul mixt se anulează și dacă produsul vectorial este
deja nul, adică dacă $ \vec{b} || \vec{c} $. În acest caz degenerat, concluzia se păstrează,
totuși. Dacă $ \vec{b} || \vec{c} $, înseamnă că cei doi vectori coincid (pînă la o translație
paralelă). Atunci vectorul $ \vec{a} $ este un al doilea vector (posibi) diferit de aceștia
și cum doi vectori determină un plan, înseamnă că vectorii $ (\vec{a}, \vec{b} = \vec{c}) $ 
sînt coplanari.

Una dintre aplicațiile imediate ale produsului mixt -- care se poate justifica folosind
geometrie elementară în spațiu, este aceasta:

```{important}
Volumul tetraedrului generat de vectorii neparaleli și necoplanari $ \vec{a}, \vec{b}, \vec{c} $
se calculează prin:

$$
  V = \dfrac{1}{6} \left( \vec{a}, \vec{b}, \vec{c} \right).
$$
```

```{figure} ./img/volum-piramida.png
---
name: fig-vol-piramida
---
Volumul piramidei generate de vectorii neparaleli și necoplanari $ \vec{a}, \vec{b}, \vec{c} $
```

Putem ajunge și la o formulă de calcul al volumului unei *prisme triunghiulare*. Știm deja
că aria triunghiului este jumătate din modulul produsului vectorial al două laturi.
Volumul unui corp drept se calculează ca aria bazei înmulțită cu înălțimea, deci în prisma
de mai jos, volumul este aria triunghiului $ \Delta ABC $ înmulțită cu înălțimea $ BE $,
de exemplu. Dar această înălțime este perpendiculara pe planul determinat de vectorii $ \vec{AB} $
și $ \vec{AC} $, adică este paralelă cu produsul vectorial $ \vec{AB} \times \vec{AC} $.
Este suficient să rescalăm acest produs vectorial și obținem înălțimea sub forma
```{math}
  \vec{BE} \cdot (\vec{AB} \times \vec{AC}) \cdot \dfrac{1}{||\vec{AB} \times \vec{AC}||}.
```
Produsul scalar al doi vectori coliniari este pur și simplu egal cu produsul modulelor lor,
de aceea a trebuit să înmulțim cu modulul (norma) produsului vectorial, pentru a rămîne
doar cu înălțimea $ BE $.

Punînd informațiile cap la cap, obținem:
```{math}
\begin{align*}
  V(ABCDEF) &= \dfrac{1}{2} || \vec{AB} \times \vec{AC}|| \cdot \vec{BE} \cdot (\vec{AB} \times \vec{AC}) \cdot \dfrac{1}{||\vec{AB} \times \vec{AC}||} \\
	        &=\dfrac{1}{2} \vec{BE} \cdot (\vec{AB} \times \vec{AC}).
\end{align*}
```

Ajungem la concluzia:
```{important}
Volumul unei prisme triunghiulare drepte $ ABCDEF $, cu bazele paralele
triunghiurile $ \Delta ABC $ și $ \Delta DEF $, este egal cu:

$$
  V(ABCDEF) = \dfrac{1}{2} \vec{BE} \cdot (\vec{AB} \times \vec{AC}).
$$
```
```{figure} ./img/volum-prisma.png
---
name: fig-vol-prisma
---
Volumul prismei triunghiulare drepte $ ABCDEF $
```
