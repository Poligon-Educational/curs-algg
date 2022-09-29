# Operații cu subspații
**#TODO: De găsit aplicații -- preferabil în afară de suma directă**

**#TODO: De găsit legături cu Grassmann**

## Reuniunea, intersecția și suma
Date două sau mai multe (sub)spații vectoriale, ne întrebăm cum putem obține
unele noi din ele sau, dacă este cazul, cum putem să le „descompunem“, scopul
fiind, din nou, obținerea unor (sub)spații noi, cu efort minim.

În plus, este natural să ne gîndim la operații între (sub)spații pornind de la
operații între (sub)mulțimi. Sîntem familiarizați cu reuniunea și intersecția
a două mulțimi, de exemplu -- de ce nu ar funcționa aceeași construcție și în
cazul spațiilor vectoriale? Cum probabil intuiți, problema principală este
structura algebrică. Dacă între *mulțimile* subiacente spațiilor vectoriale
putem face operațiile cunoscute cu mulțimi, nu înseamnă neapărat că se va păstra
structura de spațiu vectorial pe mulțimea rezultată. Trebuie să impunem anume
condiții asupra unor operații, iar la alte operații să renunțăm cu totul.

Amintim definițiile reuniunii și intersecției dintre două mulțimi $ A $ și $ B $:
```{math}
\begin{align*}
  A \cap B &= \{ x \mid x \in A \text{ și } x \in B \} \\
  A \cup B &= \{ x \mid x \in A \text{ sau } x \in B \}
\end{align*}
```

Aceleași sînt și operațiile pe care le aplicăm între (sub)spații, însă dacă
ne uităm la rezultat, din punct de vedere algebric, vom constata următoarele:

```{prf:theorem}
:label: thm-op-subsp

- Reuniunea a două spații vectoriale *nu* are în general structură de spațiu vectorial.
- Intersecția a două spații vectoriale este spațiu vectorial.

În plus,
- Reuniunea a două subspații vectoriale ale unui spațiu *nu* este subspațiu.
- Intersecția a două subspații vectoriale ale unui spațiu este subspațiu al aceluiași spațiu.
```

Demonstrațiile sînt destul de tehnice și le omitem, însă putem ilustra situația
cu exemple.

Considerăm $ V = \mathbb{R}^3 $, pentru simplitate și pentru că putem să vizualizăm
grafic. Fie subspațiile date de cele două axe de coordonate:
```{math}
\begin{align*}
  W_1 &= \{ (x, 0) \mid x \in \mathbb{R} \} \\
  W_2 &= \{ (0, y) \mid y \in \mathbb{R} \}
\end{align*}
```

Reuniunea celor două subspații, $ W_1 \cup W_2 $, conține punctele care se găsesc
pe oricare dintre cele două axe, adică:
```{math}
W_1 \cap W_2 = \{ (x, y) \mid x = 0 \text{ sau } y = 0 \}
```

De exemplu, avem $ (1, 0), (0, -3) \in W_1 \cup W_2 $. Însă aproape orice combinație
liniară a acestora *nu* mai se găsește în reuniune. Într-adevăr, chiar suma celor
doi vectori este în afară:
```{math}
(1, 0) + (0, -3) = (1, -3) \notin W_1 \cup W_2,
```
deoarece nu are cel puțin o componentă nulă.

Vedem, așadar, că $ W_1 \cup W_2 $ nu este nici măcar (sub)grup aditiv, cu atît mai puțin
subspațiu vectorial al lui $ \mathbb{R}^3 $.

Pe de altă parte, intersecția celor două subspații este trivială:
```{math}
W_1 \cap W_2 = \{ (x, y) \mid x = 0 \text{ și } y = 0 \} = \{ (0, 0) \},
```
care este (sub)spațiu vectorial banal.

Dar putem avea și un exemplu netrivial de intersecție: Considerăm $ W_1 $ și $ W_2 $
două plane care conțin originea spațiului $ \mathbb{R}^3 $. Intersecția lor
va fi o dreaptă care trece prin origine, deci este subspațiu al lui $ \mathbb{R}^3 $.

Și pentru că o parte importantă a spațiilor vectoriale o constituie combinațiile
liniare, avem și o operație specială, numită *suma* (sub)spațiilor:

```{prf:definition}
:label: def-suma-sp

Fie $ U, V $ două spații vectoriale peste același corp.

Se definește *suma* spațiilor, notată $ U + V $, ca fiind mulțimea
alcătuită din vectorii care pot fi scriși ca sumă dintre un vector din $ U $
și unul din $ V $. În simboluri:

$$
  U + V = \{ x \mid \exists u \in U, v \in V, x = u + v \}.
$$
```

Se poate demonstra că *suma a două (sub)spații este (sub)spațiu*.

Dăm un exemplu ilustrativ: fie $ U = \{ (a, 3a) \mid a \in \mathbb{R} \} $
și $ V = \{ (2b, 0) \mid b \in \mathbb{R} \} $. Ambele sînt subspații ale
planului $ \mathbb{R}^2 $, iar suma lor este:
```{math}
U + V = \{ (a + 2b, 3a) \mid a, b \in \mathbb{R} \}.
```

Din punct de vedere geometric, lucrurile stau astfel:
- $ U $ este dreapta de ecuație $ y = \dfrac{1}{3} x $, care trece prin origine;
- $ V $ este axa $ OX $, pentru că a doua componentă (ordonata) este mereu nulă;
- suma $ U + V $ este, de fapt, *întreg planul*. Aceasta deoarece, cum $ a $ și $ b $
sînt numere reale, se poate vedea ușor că pentru *orice* pereche de numere reale $ (x, y) $
se pot găsi $ a, b $ astfel încît $ (x, y) = (a + 2b, 3a) $. Putem da și soluția:
$ a = \dfrac{1}{3}y $ și $ b = \dfrac{x - a}{2} = \dfrac{3x - y - a}{6} $. Așadar,
pentru $ (x, y) $ date, putem găsi $ a, b $ cu proprietatea cerută.

Similar stau lucrurile și dacă luăm $ W_1 $ și $ W_2 $ de mai sus, axele de coordonate.
Suma lor conține toți vectorii din plan (convingeți-vă!), deci se obține întreg planul.

De fapt, în acest caz, avem o situație particulară, probabil cea mai importantă
aplicație a sumei spațiilor vectoriale.

```{prf:definition}
:label: def-oplus

Spunem că două subspații vectoriale $ W_1 $ și $ W_2 $ ale unui spațiu $ V $
sînt în *sumă directă*, notat $ W_1 \oplus W_2 $, dacă $ W_1 \cap W_2 = \{ 0_V \} $, 
adică nu au în comun decît vectorul nul.
```

De exemplu, este cazul axelor de coordonate, ca subspații ale planului real:
ele nu au în comun decît originea, adică vectorul nul, așadar formează sumă directă.

Avem două proprietăți importante ale sumei directe, pe care le prezentăm pe scurt:

```{prf:theorem}
:label: thm-oplus

Presupunem că subspațiile $ W_1, W_2 $ ale spațiului $ V $ alcătuiesc sumă directă.

Atunci are loc:

$$
  W_1 \oplus W_2 = \{ x \in V \mid \exists! w_1 \in W_1, w_2 \in W_2, x = w_1 + w_2 \}
$$

În cuvinte, un vector din suma directă se scrie *unic* drept sumă a componentelor
din cele două subspații.
```

```{prf:proof}
Faptul că $ x \in V $ se descompune ca sumă de componente din $ W_1 $ și $ W_2 $
este garantat de definiția sumei de subspații.

Unicitatea descompunerii rezultă astfel. Presupunem că $ x $ ar avea două descompuneri
diferite:

$$
  x = a + b = c + d, \quad a, c \in W_1, b, d \in W_2.
$$

Atunci obținem:

$$
  a - c = d - b \in W_1 \cap W_2 = \{ 0_V \} \Rightarrow a = c, d = b,
$$

așadar descompunerile coincid.
```

A doua proprietate o prezentăm fără demonstrație:

```{prf:theorem} Hermann Grassmann
:label: thm-grassmann

Fie $ W_1, W_2 $ două subspații ale unui spațiu vectorial $ V $. Atunci:

$$
  \dim (W_1 + W_2) = \dim(W_1) + \dim(W_2) - \dim(W_1 \cap W_2).
$$

În particular, dacă $ W_1 \oplus W_2 $, avem:

$$
  \dim (W_1 \oplus W_2) = \dim(W_1) + \dim(W_2).
$$

```

Aici este cheia faptului că planul real $ \mathbb{R}^2 $ se poate scrie
ca suma directă a axelor de coordonate. Anticipăm un rezultat pe care îl vom
prezenta detaliat în secțiunea următoare:

```{prf:theorem}

Două spații vectoriale sînt izomorfe („la fel“ din punct de vedere algebric)
dacă și numai dacă au aceeași dimensiune.
```

În cazul nostru, dimensiunea spațiilor care descriu axele de coordonate este 1
(fiecare dintre ele este, de fapt, o copie a lui $ \mathbb{R} $). Cum ele formează
sumă directă, rezultă, din teorema lui Grassmann, că dimensiunea sumei este $ 1 + 1 = 2 $,
adică exact dimensiunea planului real. Concluzia este că suma directă a axelor de
coordonate alcătuiește planul real (pînă la un izomorfism, adică alcătuiește *o copie*
a planului real).

Putem generaliza această observație, de fapt. Dacă considerăm $ V_i $ ca fiind un spațiu
alcătuit din vectori cu $ n $ componente, dintre care doar una -- cea de pe poziția $ i $ --
este nenulă, adică:
```{math}
V_i = \{ (0, 0, 0, \dots, 0, 1, 0, \dots, n) \in \mathbb{R}^n \},
```
unde $ 1 $ apare pe poziția $ i $, atunci găsim, în general:
```{math}
\mathbb{R}^n = V_1 \oplus V_2 \oplus V_3 \oplus \dots \oplus V_n,
```
egalitate care are loc pînă la un izomorfism.

Vom explora mai multe astfel de descompuneri după ce detaliem noțiunile specifice
morfismelor și izomorfismelor de spații vectoriale.
