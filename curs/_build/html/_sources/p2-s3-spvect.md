# Spații vectoriale

Spațiile vectoriale sînt următoarele structuri algebrice pe care le prezentăm.
Formal, ele sînt cele mai complicate de pînă acum, deoarece folosesc simultan
*două* structuri anterioare: sînt perechi alcătuite dintr-un grup și un corp.
Dar o astfel de introducere este complet contraintuitivă și nu evidențiază deloc
apariția „naturală“ a spațiilor vectoriale, pornind de la cazuri particulare
la îndemînă. Astfel că vom începe tocmai prin evidențierea acestei „genealogii“,
bazată pe noțiuni elementare de geometrie plană.

(sec-intuitie-spvect)=
## Intuiție
Cel mai bun punct de pornire este acela al vectorilor din plan, studiați
riguros la matematica și fizica de clasa a IX-a.

Remarcăm, totuși, că, deși avem la îndemînă informații geometrice, care țin
de reprezentarea grafică a vectorilor și a operațiilor dintre ei, vom insista
în special pe abordarea algebrică, dată fiind ținta pe care ne-o propunem.
În orice caz, intuiția geometrică și reprezentarea plană pot servi drept
îndrumători.

Așadar, din punct de vedere geometric, un vector în plan $ \vec{v} $ este
un segment orientat. El are 
- o *dreaptă suport*, care-i dă *direcția*;
- un *punct de aplicație*, cum se numește de obicei la fizică, în cazul forțelor,
sau o *origine*, în matematică;
- un *sens*;
- un *modul* sau o *lungime*, care ne arată, în fizică, mărimea forței reprezentată
de vectorul respectiv, iar în matematică, lungimea segmentului determinat de
originea și vîrful vectorului.

```{figure} ./img/vector-plan.png
---
name: fig-vec-plan
---
Un vector în plan $ \vec{v} $ și elementele sale definitorii
```

Chiar dacă o astfel de prezentare este intuitivă și ușor de vizualizat, pentru
scopuri algebrice este mai potrivit să prezentăm vectorii într-un sistem de coordonate.
Așadar, amintim că un vector din plan se poate descompune în funcție de *versorii*
$ \vec{i} $ și $ \vec{j} $, care sînt vectorii-unitate ai celor două axe de coordonate.
Așadar, un vector în plan se scrie generic:

```{math}
\vec{v} = a \vec{i} + b \vec{j}, \quad a, b \in \mathbb{R}.
```

Uneori, această scriere este prescurtată sub forma $ \vec{v} = (a, b) $, întrucît
versorii sînt subînțeleși. O astfel de scriere are avantajul că ne conduce
către analogia cu punctele din plan. Pînă la urmă, un astfel de vector se prezintă
identic cu un punct din plan, vorbind strict din punct de vedere algebric,
deci abstract. Deci nu am greși dacă am scrie $ \vec{v} = (a, b) \in \mathbb{R}^2 $.

Mai departe, ne întrebăm ce operații putem face cu vectorii și găsim imediat:
- *adunarea*, care acționează pe componente, adică:
```{math}
(a \vec{i} + b \vec{j}) + (c \vec{i} + d \vec{j}) = (a + c)\vec{i} + (b + d)\vec{j}.
```
În forma similară punctelor din plan, acest lucru se scrie și mai clar:
```{math}
(a, b) + (c, d) = (a + c, b + d).
```
- *înmulțirea vectorilor cu scalari*, care produce modificări ale modulului vectorului și,
eventual, ale sensului acestuia, dacă scalarul este negativ. Pentru un scalar real $ \alpha \in \mathbb{R} $,
avem:
```{math}
\alpha \cdot (a \vec{i} + b \vec{j}) = (\alpha a)\vec{i} + (\alpha b)\vec{j}
```
sau, în forma din $ \mathbb{R}^2 $:
```{math}
\alpha \cdot (a, b) = (\alpha a, \alpha b).
```

Produsele dintre vectori sînt un subiect mai complicat, deoarece avem două tipuri de produse
(scalar și vectorial), care conduc la rezultate complet diferite -- unul dintre ele transformă
doi vectori într-un scalar, iar cel de-al doilea conduce la un vector în afara planului dat
de cei doi factori. Astfel că omitem, pentru moment, discuția privitoare la produse între vectori
și lucrăm doar cu cele două operații de mai sus.

Continuăm analiza și ne întrebăm acum ce proprietăți au cele două operații, în funcție
de mulțimile pe care se introduc:
- *adunarea vectorilor*, definită între vectori din plan și care, în definitiv, este *adunarea pe componente*,
definită pe perechi de numere reale, este:
  + *internă*, deoarece suma a doi vectori din plan este un vector din același plan;
  + *comutativă*, ca orice adunare;
  + *asociativă*, din nou, ca orice adunare;
  + admite un *element neutru*, anume vectorul nul, $ (0, 0) $, întrucît $ (a, b) + (0, 0) = (a, b) $,
  pentru orice vector $ (a, b) $;
  + orice vector $ (a, b) $ este *simetrizabil*, adică are un opus, $ (-a, -b) $, pentru că
  $ (a, b) + (-a, -b) = (0, 0) $.

Din toate acestea, rezultă imediat că adunarea vectorilor definește o *structură de grup* pe mulțimea
vectorilor din plan. Și chiar este un grup binecunoscut[^r2], anume $ (\mathbb{R}^2, +) $.

[^r2]: Riguros, ceea ce am obținut aici este un grup *izomorf* cu $ (\mathbb{R}^2, +) $,
deoarece vectorii din plan nu *sînt efectiv* puncte din planul real $ \mathbb{R}^2 $ sau perechi
de numere reale. Ca obiecte geometrice, vectorii au o definiție diferită.
Însă asemănarea este atît de clară, încît putem chiar să nu facem nicio distincție între ele.

- *înmulțirea vectorilor cu scalari*, definită între numere reale și vectori din plan, are proprietățile:
  + este *lege externă*, deoarece combină obiecte de două tipuri: dintr-un scalar și un vector se obține un vector,
  așadar este o operație de forma $ \mathbb{R} \times \mathbb{R}^2 \to \mathbb{R}^2 $;
  + este *comutativă*, pentru că putem înmulți cu scalari și la stînga, și la dreapta, obținînd același vector;
  + are un *element neutru*, scalarul $ 1 $, cu care, înmulțind orice vector, obținem vectorul inițial;
  + are un *element distructiv*, scalarul $ 0 $, cu care, înmulțind orice vector, obținem *vectorul nul*.
  + are un fel de proprietate de *distributivitate*, pentru că putem înmulți cu un scalar și o sumă de vectori,
  rezultatul fiind cel așteptat.

În plus, dacă ne gîndim la mulțimea de scalari în sine -- care este $ \mathbb{R} $ -- știm deja că
aceasta are o structură de corp comutativ, față de adunarea și înmulțirea numerelor reale.

Observațiile de mai sus schițează, practic, tocmai definiția unui spațiu vectorial. Înainte
de a o face riguroasă, recapitulăm: Pentru a defini un spațiu vectorial, avem nevoie de:
- o mulțime de vectori, care să aibă o structură de grup comutativ;
- o mulțime de scalari, care să aibă o structură de corp (preferabil comutativ);
- o operație externă, care să poată combina scalarii cu vectori, obținînd vectori, și care să aibă
cîteva proprietăți „bune“, bazate pe doi scalari speciali (unitate și nul) și un fel de proprietate
de desfacere a parantezelor, adică distributivitate.

Cu aceste observații, putem acum să dăm definițiile riguroase.

## Definiție formală
```{prf:definition}
:label: def-sp-vect

Fie $ (V, +) $ un grup comutativ și $ (K, +, \cdot) $ un corp, pe care,
pentru simplitate, îl vom presupune comutativ[^operatii].

De obicei, elementele grupului $ V $, numit *grup de vectori*, se notează
cu litere latine, iar elementele corpului $ K $, numit *corp de scalari*,
se notează cu litere grecești.

Perechea $ (K, V) $ definește un *spațiu vectorial* sau, echivalent,
spunem că $ V $ devine un $ K $-spațiu vectorial sau un spațiu vectorial peste $ K $
dacă există o operație externă $ K \times V \to V $, numită *înmulțire a vectorilor cu scalari*,
cu proprietățile:
1. $ \alpha \cdot (v + w) = \alpha \cdot v + \alpha \cdot w, \forall \alpha \in K, v, w \in V $;
2. $ \alpha \cdot (\beta \cdot w) = (\alpha \cdot \beta) \cdot w, \forall w \in V $;
3. $ 1_K \cdot v = v, \forall v \in V $;
4. $ 0_K \cdot v = 0_V, \forall v \in V $.
```

[^operatii]: Cu riscul de ambiguitate, am notat toate operațiile aditiv și multiplicativ.
Atenția la context ne va arăta despre care operație este vorba.

```{note}
Spațiile vectoriale au definiții foarte asemănătoare și pentru corpuri care nu sînt comutative,
caz în care trebuie să facem distincția între înmulțirea cu scalari la stînga și la dreapta.

**În toate exemplele care urmează, dacă nu precizăm altfel, presupunem că lucrăm cu corpuri comutative.**
```

Acum, definiția de mai sus pare naturală, dar conține cîteva subtilități pe care este bine să le observați:
- în cazul proprietății 1, în membrul stîng avem operația $ \cdot $ de înmulțire a scalarului $ \alpha $
cu vectorul sumă $ v + w $, iar în membrul drept, între $ \alpha $ și $ v $, respectiv $ w $, este tot operația
de înmulțire a scalarilor cu vectori, în timp ce operația $ + $ este cea de adunare a vectorilor;
- în cazul proprietății 2, cele două operații $ \cdot $ din membrul stîng sînt de înmulțire a scalarilor
cu vectori, însă operația $ \cdot $ din paranteză din membrul drept este de înmulțire a scalarilor
(operația din $ K $), în timp ce a doua operație $ \cdot $ este înmulțirea scalarilor cu vectori;
- $ 1_K $ este elementul unitate al corpului $ K $;
- $ 0_K $ este elementul nul al corpului $ K $;
- $ 0_V $ este elementul nul (vectorul nul) al grupului $ V $.

## Exemple
În toate cazurile pe care le vom întîlni, nu este necesar un efort susținut de abstractizare
pentru a identifica structura de grup pentru vectori, structura de corp pentru scalari și
operația externă. Aceasta deoarece spațiile vectoriale cu aplicații în geometrie -- care constituie
ținta pe care ne vom concentra -- au structuri destul de transparente. În esență, exemplele pe care
le vom lista aici sînt cele pe care le vom întîlni în majoritatea cazurilor.

**Exemplu:** Cazul intuitiv al vectorilor din plan poate fi privit acum formal:
- grupul de vectori este $ (\mathbb{R}^2, +) $, adunarea fiind definită pe componente;
- corpul de scalari este $ \mathbb{R} $, cu adunarea și înmulțirea obișnuite;
- operația externă de înmulțire a vectorilor cu scalari este, de fapt, înmulțirea unei
perechi de numere reale cu un alt număr real, înmulțire care se face pe componente.

Așadar, $ \mathbb{R}^2 $ este un $ \mathbb{R} $-spațiu vectorial (numit și spațiu vectorial real).

**Exemplu:** Cazul vectorilor din plan poate fi generalizat. Putem defini:
```{math}
\mathbb{R}^n = \{ (a_1, a_2, \dots, a_n) \mid a_i \in \mathbb{R}, i \in \mathbb{N}^\ast \},
```
iar pe această mulțime a $ n $-tuplurilor de numere reale definim o structură de grup
bazată pe adunarea pe componente:
```{math}
(a_1, a_2, \dots, a_n) + (b_1, b_2, \dots, b_n) = (a_1 + b_1, a_2 + b_2, \dots, a_n + b_n), %
\quad \forall a_i, b_i \in \mathbb{R}, i \in \mathbb{N}^\ast.
```

Evident, $ (\mathbb{R}^n, +) $ devine un grup comutativ, vectorul nul fiind $ (0, 0, \dots, 0) $,
șirul cu $ n $ componente nule.

Considerînd tot corpul numerelor reale drept corp de scalari, avem o definiție naturală
și pentru operația externă:
```{math}
\alpha \cdot (a_1, a_2, \dots, a_n) = (\alpha a_1, \alpha a_2, \dots, \alpha a_n), \quad %
\forall \alpha, a_i \in \mathbb{R}, i \in \mathbb{N}^\ast.
```

Se verifică imediat că $ \mathbb{R}^n $ devine astfel un spațiu vectorial real,
fiind unul dintre cele mai importante exemple pe care le vom întîlni.

**Exemplu:** Considerăm grupul aditiv al matricelor $ M_2(\mathbb{R}) $.
Știm deja structura de grup (cf. [secțiunii corespunzătoare](./p2-s1-grupuri.md))
și, dacă luăm din nou corpul de scalari ca fiind corpul real, nu avem decît să
definim înmulțirea vectorilor cu scalari, în maniera așteptată:
```{math}
\alpha \cdot \begin{pmatrix} a & b \\ c & d \end{pmatrix} = %
\begin{pmatrix} \alpha a & \alpha b \\ \alpha c & \alpha d \end{pmatrix}, \quad %
\forall \alpha, a, b, c, d \in \mathbb{R}.
```

Cu această definiție, se verifică imediat faptul că $ M_2(\mathbb{R}) $ devine
un spațiu vectorial real.

**Exemplu:** Nu numai matricele pătratice constituie spații vectoriale și nu neapărat
peste corpul numerelor reale. Dacă luăm $ V = M_{2, 5}(\mathbb{C}) $ și $ K = \mathbb{Q} $,
cu operațiile obișnuite, obținem tot un spațiu vectorial, de data aceasta rațional.
Convingeți-vă de acest lucru înțelegînd structura de grup pe $ V $ și operația externă.

**Exemplu:** Păstrînd doar structura aditivă, grupul $ (\mathbb{R}, +) $ poate fi gîndit
ca un $ \mathbb{Q} $-spațiu vectorial. Înmulțirea vectorilor cu scalari înseamnă pur și simplu
înmulțirea unui număr real cu unul rațional, rezultatul fiind un număr real.

```{important}
Tocmai acest exemplu ne arată o situație deosebită: Deoarece $ \mathbb{Q} \subseteq \mathbb{R} $,
putem considera $ \mathbb{R} $ ca un $ \mathbb{Q} $-spațiu vectorial, deoarece înmulțind
un număr real (vector) cu unul rațional (scalar), rezultatul este un număr real (vector).

Invers, însă, $ \mathbb{Q} $ nu poate fi un spațiu vectorial real! Puteți vedea acest lucru
foarte simplu: fie vectorul $ v = 3 \in \mathbb{Q} $ și scalarul $ \alpha = \sqrt{2} \in \mathbb{R} $.

Atunci înmulțirea vectorilor cu scalari produce $ 3 \sqrt{2} $, care ar trebui să fie *vector*,
deci un număr rațional, ceea ce este fals!
```

**Exemplu:** Un caz ceva mai tehnic, dar destul de util, este acela al *polinoamelor*.
Fără a intra în detalii sofisticate, *inelul polinoamelor într-o nedeterminată*,
cu coeficienți într-un corp $ K $ se notează cu $ K[X] $ și conține expresii de forma:
```{math}
p = a_0 + a_1 X + a_2 X^2 + \dots + a_n X^n, \quad a_i \in K, i, n \in \mathbb{N}.
```

Ați întîlnit astfel de expresii de obicei în *ecuații polinomiale*. De pildă o simplă
ecuație de gradul al doilea, precum:
```{math}
3x^2 - 5x + 2 = 0
```
este ecuația asociată *polinomului de gradul al doilea* $ q = 3X^2 - 5X + 2 $, iar rezolvarea
ecuației înseamnă *găsirea rădăcinilor (zerourilor) polinomului*.

Puterea cea mai mare la care apare nedeterminata se numește *gradul* polinomului,
deci $ \grad(q) = 2 $ în exemplul anterior și $ \grad(p) = n $ în forma generală
de mai sus.

În majoritatea cazurilor, vom lucra cu inelul de polinoame cu coeficienți reali, adică
$ \mathbb{R}[X] $. Structura de inel ar trebui să fie clară, dar, de fapt, pentru spații
vectoriale, ne este suficient să înțelegem structura de grup comutativ, deci cea aditivă:

- suma a două polinoame se face pe componente:
```{math}
(a_0 + a_1 X + a_2 X^2 + \dots + a_n X^n) + (b_0 + b_1 X + b_2 X^2 + \dots + b_n X^n) = %
(a_0 + b_0) + (a_1 + b_1) X + (a_2 + b_2) X^2 + \dots + (a_n + b_n) X^n, \forall a_i, b_i \in \mathbb{R}, 0 \leq i \leq n.
```

Pentru simplitate, am presupus că cele două polinoame adunate mai sus au același grad.
Dar și dacă au grade diferite, adunarea se definește similar. Gîndiți-vă, de exemplu, cum
ați aduna un polinom de gradul 1 cu un polinom de gradul 2:
```{math}
(2 + X) + (5 - 3X + X^2) = (2 + 5) + (1 - 3) X + X^2
```

În fapt, orice polinom poate fi făcut de orice grad, dacă i se adaugă termeni cu coeficient nul.
În exemplul de mai sus, polinomul de gradul 1 $ 2 + X $ poate fi gîndit ca polinomul de gradul 2
$ 2 + X + 0 \cdot X^2 $.

- elementul neutru al adunării polinoamelor este polinomul nul, $ p = 0 = 0 + 0 \cdot X + 0 \cdot X^2 + \dots $;
- opusul unui polinom este cel care are coeficienții opuși polinomului dat;

Așadar, $ (\mathbb{R}[X], +) $ este un grup comutativ.

Considerînd din nou corpul numerelor reale, obținem imediat că $ \mathbb{R}[X] $ devine un
spațiu vectorial real, înmulțirea vectorilor cu scalari făcîndu-se în modul natural:
```{math}
\alpha \cdot (a_0 + a_1 X + a_2 X^2 + \dots + a_n X^n) = %
(\alpha a_0) + (\alpha a_1) X + (\alpha a_2) X^2 + \dots + (\alpha a_n) X^n,
\forall \alpha, a_i \in \mathbb{R}, 0 \leq i \leq n.
```

```{note}
Putem considera și cazuri particulare de inele (sau spații vectoriale) de polinoame,
care să limiteze gradul maxim. De aceea, se notează cu $ \mathbb{R}_n[X] $, de exemplu,
mulțimea polinoamelor de grad *cel mult* $ n $. De exemplu, mulțimea $ \mathbb{R}_2[X] $
conține polinoame de grad 0 (constante, adică numere reale), polinoame de grad 1
și polinoame de grad 2.
```

---

### Un detaliu tehnic
Această secțiune poate fi omisă la o primă lectură, însă ea oferă detalii tehnice
care pot fi interesante pentru cei care apreciază structurile abstracte și mai ales
legăturile dintre ele.

Inelele de polinoame au o structură mult mai simplă decît pare, cel puțin în ce privește
structura aditivă. În unele cărți de matematică de liceu, chiar se introduc polinoamele
sub forma șirurilor de numere (reale, în cazul nostru). Altfel spus, se definește o
generalizare a produsului cartezian al mulțimii de numere reale:

```{math}
\mathbb{R}^{(\mathbb{N})} = \mathbb{R} \times \mathbb{R} \times \dots,
```

produsul cartezian avînd atîția factori cîte numere naturale există.

Un element din această mulțime este pur și simplu o generalizare a unui
$ n $-tuplu, adică un șir de numere reale care conține atîtea elemente
cîte numere naturale există:

```{math}
(a_0, a_1, a_2, \dots, a_n, \dots) \in \mathbb{R}^{(\mathbb{N})}, \quad a_i \in \mathbb{R}, i \in \mathbb{N}.
```

Suma a două astfel de elemente se face pe componente, ca în orice produs cartezian.
Elementul nul este cel care are $ 0 $ pe toate pozițiile. În plus, se constată că dacă 
avem un element nenul pe prima componentă și în rest $ 0 $, găsim o structură
care este chiar (izomorfă) cu mulțimea numerelor reale. Altfel spus:

```{math}
\mathbb{R}^{(\mathbb{N})} \ni (a, 0, 0, 0, \dots) \mapsto a \in \mathbb{R}.
```

Apoi, se definește un element special:

```{math}
X = (0, 1, 0, 0, \dots)
```

și un produs[^produs] astfel încît:
```{math}
X^2 = X \cdot X = (0, 0, 1, 0, \dots), X^3 = (0, 0, 0, 1, 0, 0, \dots), \dots,
```
adică în general, $ X^n $ are $ 1 $ pe poziția $ n + 1 $ și $ 0 $ în rest.

[^produs]: Definiția concretă este ceva mai complicată. Gîndiți-vă cum se înmulțesc
două polinoame, unde trebuie să ținem cont de grad. În plus, un produs de polinoame
va avea gradul egal cu suma gradelor celor doi factori.

Cu acestea, se poate *defini* un polinom în nedeterminata $ X $ ca fiind o expresie
de forma:
```{math}
(a_0, a_1, a_2, a_3, \dots) = a_0 + a_1 X + a_2 X^2 + a_3 X^3 + \dots
```

O astfel de prezentare, pe lîngă faptul că ne arată o nouă modalitate de a privi polinoamele,
va fi foarte utilă atunci cînd vom studia izomorfismele de spații vectoriale.
Anticipînd, vom vedea că spațiile de polinoame $ \mathbb{R}[X] $ „seamănă“ (din punct de vedere algebric)
cu cele de forma $ \mathbb{R}^n $.

---

Revenind la definiții și exemple pentru spații vectoriale, putem găsi
multe altele, mai mult sau mai puțin naturale sau relevante în ce privește
aplicațiile. Pentru scopurile acestui material, ne rezumăm, totuși, la:
- spații de forma $ \mathbb{R}^n $;
- spații de matrice pătratice, de forma $ M_n(\mathbb{R}) $;
- spații de polinoame, de forma $ \mathbb{R}_n[X] $.

```{note}
Dacă nu se precizează altfel, vom presupune că lucrăm cu *spații vectoriale reale*.
Așadar, corpul de scalari va fi mereu $ \mathbb{R} $, iar spațiul
vectorial va fi identificat doar prin grupul de vectori:
$ \mathbb{R}^n, M_n(\mathbb{R}) $ sau $ \mathbb{R}_{n}[X] $.
```

## Subspații
Echivalentul substructurilor din cazul monoizilor, grupurilor, inelelor,
corpurilor este acela al *subspațiilor vectoriale*. Ca și pînă acum,
putem formula o definiție abstractă simplă, dar, pentru motive practice, (aproape) inutilă:

```{prf:definition}
:label: def-subspatiu

Fie $ V $ un $ K $-spațiu vectorial și $ W \subseteq V $ o submulțime.

Spunem că $ W $ este *subspațiu al lui $ V $*, notat cu $ W \leq_K V $,
dacă $ W $ însuși este un $ K $-spațiu vectorial.
```

Observăm, totodată, în definiția de mai sus, notația care face uz explicit
de corpul de scalari. Cum vom lucra în majoritatea cazurilor cu spații vectoriale
reale, vom simplifica notația de la $ W \leq_\mathbb{R} V $ la $ W \leq V $,
pentru $ W $ un subspațiu al lui $ V $, atunci cînd nu există riscul de confuzie.

Cum spuneam, însă, nu este suficient de ușor să lucrăm cu definiția. Practic,
ar trebui să demonstrăm din nou toate axiomele pentru $ W $, deși le știm deja
pentru mulțimea în care este conținut, $ V $. Așa că avem nevoie de o metodă
mai simplă. 

Totodată, dăm și o formulare simplificată a structurii algebrice de
spațiu vectorial. Am văzut că o astfel de structură conține un grup și un corp,
împreună cu 4 operații în total (adunarea vectorilor, adunarea și înmulțirea
scalarilor și înmulțirea vectorilor cu scalari). Toate aceste operații pot fi concentrate
într-una singură, numită *combinație liniară*.

```{prf:definition}
:label: def-comb-lin

Fie $ V $ un $ K $-spațiu vectorial și $ v, w \in V $ doi vectori, iar $ \alpha, \beta \in K $
doi scalari.

Se numește *combinație liniară* de vectori cu scalari o expresie de forma:

$$ \alpha v \pm \beta w. $$
```

Într-o astfel de expresie, avem concentrate majoritatea proprietăților
și elementelor speciale dintr-un spațiu vectorial, ca de exemplu:
- luînd $ \alpha = \beta = 1_K $, găsim adunarea vectorilor $ v + w $;
- luînd $ \alpha = \beta = 0_K $, găsim vectorul nul $ 0_V $;
- pentru $ \beta = 0_K $, găsim înmulțirea unui vector cu scalar, $ \alpha v $;

De asemenea, mai observăm că semnul $ \pm $ este, de fapt, inutil.
Aceasta deoarece, cum $ \alpha $ și $ \beta $ sînt elemente arbitrare ale
unui corp, ele sînt inversabile și au opuse. Deci putem considera oricînd
în loc de $ \beta $ elementul $ -\beta $, adică opusul său.

În esență, pentru majoritatea scopurilor practice, este suficient să reținem „operația“
de combinație liniară ca fiind fundamentală pentru un spațiu vectorial.

Cu acestea, avem și criteriul căutat:

```{prf:theorem}
:label: thm-subspatiu

Fie $ V $ un $ K $-spațiu vectorial și $ W \subseteq V $ o submulțime.

Atunci $ W \leq_K V $ dacă și numai dacă:

$$ \forall \alpha, \beta \in K, x, y \in W, \quad \alpha x + \beta y \in W. $$

Altfel spus, $ W $ este *închis la combinații liniare*.
```

Ca o consecință importantă a acestei teoreme, avem că un subspațiu vectorial
trebuie să preia vectorul nul. Aceasta este o condiție necesară, nu și suficientă.
Ca în cazul monoizilor, grupurilor, inelelor și corpurilor, o submulțime care
nu preia elementul neutru nu poate fi substructură.

### Exemple
Putem deja să formulăm cîteva exemple importante, printre care și unele de inspirație
geometrică.

**Exemplu:** Considerînd spațiul vectorial $ V = \mathbb{R}^2 $, putem defini
$ W = \mathbb{R} \times \{ 0 \} $, adică mulțimea de perechi de numere reale care
au a doua componentă nulă: $ W = \{ (a, 0) \mid a \in \mathbb{R} \} $.

Observăm că $ W $ preia vectorul nul, $ (0, 0) \in W $, deci condiția necesară este
satisfăcută.

Demonstrația formală procedează cam așa: Fie $ \alpha, \beta \in \mathbb{R} $ doi scalari
și $ v = (a, 0), w = (b, 0) $ doi vectori din $ W $. Trebuie să arătăm că dacă
facem combinația liniară $ \alpha v + \beta w $, găsim tot un element din $ W $.

Calculăm:

```{math}
\alpha \cdot (a, 0) + \beta \cdot (b, 0) = (\alpha a, 0) + (\beta b, 0) = (\alpha a + \beta b, 0).
```

Un element din $ W $ se caracterizează prin faptul că are prima componentă un număr real,
iar a doua componentă nulă. Cum exact aceasta este forma obținută, rezultă că am încheiat demonstrația.

**Din punct de vedere geometric,** putem vizualiza situația astfel: Spațiul $ \mathbb{R}^2 $
este planul real. Subspațiul $ \mathbb{R} \times \{ 0 \} $ conține punctele care au a doua
componentă (ordonata) nulă, ceea ce caracterizează exact punctele de pe axa absciselor, $ OX $.
Rezultă că $ W = OX $ și am arătat, deci, că axa absciselor este un subspațiu al planului real.

Evident, putem demonstra cu modificări minore că și axa ordonatelor, $ OY = \{ 0 \} \times \mathbb{R} $
este tot subspațiu.

**Exemplu:** Să luăm acum tot $ V = \mathbb{R}^2 $ și
```{math}
W = \{ (x, y) \in \mathbb{R}^2 \mid x = 5y \} = \{ (5y, y) \mid y \in \mathbb{R} \}.
```

Lăsăm demonstrația algebrică a faptului că $ W \leq V $ ca un exercițiu simplu.
Porniți cu scalarii arbitrari $ \alpha, \beta \in \mathbb{R} $ și vectorii
arbitrari $ v = (5a, a), w = (5b, b) \in W $ și arătați că, dacă le scrieți combinația
liniară, se obține un vector din $ W $, adică unul care are prima componentă de 5 ori mai
mare decît a doua, ambele fiind numere reale.

Trecem la interpretarea geometrică. Am văzut că $ \mathbb{R}^2 $ este planul real.
Punctele de forma $ (5y, y) $ au abscisa de 5 ori mai mare decît ordonata.
De pildă, punctele $ (0, 0), (5, 1), (1, 1/5), (-2, -2/5) $ etc. se găsesc în $ W $.
O caracterizare geometrică poate fi dată reinterpretînd definiția lui $ W $:
```{math}
W = \left\{ (x, y) \in \mathbb{R}^2 \mid x = 5y \Leftrightarrow y = \dfrac{x}{5} \right\}.
```

```{margin}
Amintim, pentru ecuația unei drepte plane scrisă sub forma $ y = mx + n, m, n \in \mathbb{R} $,
$ m $ se numește *panta* dreptei, iar $ n $, *ordonata la origine*. 

Din punctul de vedere al interpretării geometrice, $ m = \tan \alpha $, unde $ \alpha $
este unghiul de înclinare a dreptei, iar punctul de coordonate $ (0, n) $ este intersecția
cu axa ordonatelor -- de unde numele, de *ordonată* la origine.
```

În forma aceasta, $ y = \dfrac{x}{5} $, recunoaștem *ecuația unei drepte*. Ea trece
prin origine, deoarece conține punctul $ (0, 0) $ și are panta (înclinarea) egală cu
$ \dfrac{1}{5} $.

```{figure} ./img/dreapta-prin-origine.png
---
name: fig-dreapta-origine
---
Dreapta de ecuație $ y = \dfrac{x}{5} $
```

**Exemplu:** Considerăm acum același plan real, $ V = \mathbb{R}^2 $ și mulțimea:
```{math}
W = \{ (x, y) \in \mathbb{R}^2 \mid y = x + 1 \}.
```

Putem rescrie un element generic din $ W $ sub forma $ v = (x, x + 1) $ și, luînd
un altul, $ w = (y, y + 1) $, împreună cu doi scalari, $ \alpha, \beta \in \mathbb{R} $,
calculăm:

```{math}
\alpha v + \beta w = \dots = (\alpha x + \beta y, \alpha x + \beta y + \alpha + \beta).
```

Acum, acest element aparține lui $ W $ dacă și numai dacă a doua componentă este
cu 1 mai mare decît prima, adică dacă am avea:
```{math}
\alpha x + \beta y + \alpha + \beta = \alpha x + \beta y + 1 \Leftrightarrow \alpha + \beta = 1.
```

Dar, conform teoremei {prf:ref}`thm-subspatiu`, atît vectorii, cît și scalarii sînt arbitrari.
Or nu este adevărat că $ \alpha + \beta = 1 $ *pentru orice scalari* $ \alpha, \beta $.

Rezultă, de aceea, că $ W $ nu poate fi subspațiu al lui $ V $.

De fapt, acest lucru putea fi observat foarte simplu din condiția necesară: $ W $ nu conține
vectorul nul! Într-adevăr, $ (0, 0) $ nu se poate scrie sub forma $ (x, x + 1) $,
pentru niciun număr real $ x $.

Geometric, $ W $ este tot o dreaptă, de ecuație $ y = x + 1 $, *dar care nu mai trece prin origine*, 
deoarece, așa cum am observat, nu conține punctul $ (0, 0) $.

Din aceste exemple, putem trage o concluzie (empirică, dar adevărată) a cărei justificare
generală o omitem:

```{important}
Subspațiile planului real $ \mathbb{R}^2 $ sînt dreptele care trec prin origine.
```

```{figure} ./img/drepte-prin-origine.png
---
name: fig-subsp-r2
---
Subspațiile planului real $ \mathbb{R}^2 $ sînt dreptele care trec prin origine $ y = mx, m \in \mathbb{R} $
```


**Exemplu:** Dacă considerăm spațiul $ \mathbb{R}^3 $ (pe care îl numim deocamdată intuitiv
*spațiu tridimensional*, cunoscut și ca *reperul* $Oxyz$), atunci putem observa cu o procedură
similară celei anterioare că:

```{important}
Subspațiile cubului $ Oxyz = \mathbb{R}^3 $ sînt dreptele și planele care trec prin origine.
```

```{figure} ./img/plane-prin-origine.png
---
name: fig-plane-origine-r3
---
Planele care trec prin origine sînt subspații ale cubului $ \mathbb{R}^3 $ (vedere din lungul axei $ Oz $)
```

De exemplu, dacă definim:
```{math}
\begin{align*}
  W_1 &= \{ (x, y, z) \in \mathbb{R}^3 \mid x = 2y = 3z \} \\
  W_2 &= \{ (x, y, z) \in \mathbb{R}^3 \mid x = 2y + z - 1 \},
\end{align*}
```
putem demonstra ușor că $ W_1 $ este subspațiu al lui $ \mathbb{R}^3 $, în timp ce
$ W_2 $ *nu* este subspațiu. Putem rescrie:

```{math}
W_1 = \{ (2y, y, 2y/3) \in \mathbb{R}^3 \mid y \in \mathbb{R} \}
```
și dacă luăm doi vectori, $ v = (2y, y, 2y/3), w = (2t, t, 2t/3) \in W_1 $,
împreună cu doi scalari $ \alpha, \beta \in \mathbb{R} $, calcule simple ne arată
că o combinație liniară de forma $ \alpha v + \beta w $ produce tot un element din $ W_1 $
(exercițiu: completați detaliile).

De cealaltă parte, $ W_2 $ nu conține vectorul nul $ (0, 0, 0) $, deoarece pentru
$ x = y = z = 0 $ nu este adevărat că $ x = 2y + z - 1 $.

```{figure} ./img/subsp-r3.png
---
name: fig-ex-subsp-r3
---
Reprezentarea grafică pentru mulțimile $ W_1 $ și $ W_2 $ din exercițiu
```

**Exemplu:** Cazurile anterioare pot fi generalizate în direcția *spațiilor de soluții ale sistemelor liniare, omogene*.
Iată două exemple:
```{math}
\begin{align*}
  W_1 &= \{ (x, y, z) \in \mathbb{R}^3 \mid x + y - 2z = 0 \text{ și } 3x - y - z = 0 \} \\
  W_2 &= \{ (x, y, z, t) \in \mathbb{R}^4 \mid x - z = 0 \text{ și } 2x + z - t = 0 \text{ și } y - 3z + 2t = 0 \}
\end{align*}
```

Rescriind elementele mulțimii $ W_1 $, găsim imediat că sînt soluțiile sistemului de ecuații:
```{math}
\begin{cases}
  x + y - 2z &= 0 \\
  3x - y - z &= 0
\end{cases}
```

Din cunoștințe elementare din liceu, știm că sistemul este:
- liniar: conține doar ecuații de gradul întîi;
- omogen: termenii liberi sînt nuli, i.e. sistemul nu conține constante;
- compatibil simplu nedeterminat: are o infinitate de soluții, exprimate în funcție de un parametru.

Într-adevăr, pentru a rezolva sistemul, alegem, de pildă $ y = \alpha \in \mathbb{R} $ parametru
(necunoscută secundară) și rescriem sistemul:
```{math}
\begin{cases}
  x - 2z &= -\alpha \\
  3x - z &= \alpha
\end{cases}
```
După calcule simple, rezultă soluția:
```{math}
x = \dfrac{3}{5} \alpha, y = \alpha, z = \dfrac{4}{5} \alpha,
```
ceea ce ne permite acum să rescriem prezentarea întregii mulțimi:
```{math}
W_1 = \left\{ \left( \dfrac{3}{5} \alpha, \alpha, \dfrac{4}{5} \alpha \right) \mid \alpha \in \mathbb{R} \right\}.
```
Acum, doi vectori oarecare din $ W_1 $ pot avea forma:
```{math}
v = \left( \dfrac{3}{5} a, a, \dfrac{4}{5} a \right), w = \left( \dfrac{3}{5} b, b, \dfrac{4}{5} b \right)
```
și mai avem de luat doi scalari reali $ \alpha, \beta \in \mathbb{R} $ și să arătăm că realizînd
combinația liniară $ \alpha v + \beta w $ obținem un vector de aceeași formă cu cei din $ W_1 $.
Lăsăm aceste calcule ca exercițiu simplu.

Concluzia este că $ W_1 \leq \mathbb{R}^3 $ și calcule similare ne permit să arătăm și că
$ W_2 \leq \mathbb{R}^4 $.

Însă considerați mulțimea:
```{math}
W_3 = \{ (x, y, z) \in \mathbb{R}^3 \mid x + y = 1 \text{ și } x - 2z = 0 \}
```
Aceasta corespunde sistemului de ecuații:
```{math}
\begin{cases}
  x + y &= 1 \\
  x - 2z &= 0
\end{cases}
```
care este liniar, însă *nu este omogen*, deoarece prima ecuație are o constantă nenulă, $ 1 $.

Vă lăsăm ca exercițiu simplu să rezolvați sistemul și să vă convingeți că $ W_3 $ *nu* este un subspațiu
vectorial al lui $ \mathbb{R}^3 $.

Concluzia -- pe care o formulăm general, însă fără demonstrație -- este:

```{important}
Soluțiile sistemelor liniare și omogene alcătuiesc (sub)spații vectoriale.

Mai precis, soluțiile unui sistem liniar și omogen cu $ n $ necunoscute alcătuiesc
un subspațiu al lui $ \mathbb{R}^n $.
```

---

### Observație tehnică
Aceste exemple -- ale soluțiilor sistemelor omogene -- nu sînt, de fapt, diferite
de cele de mai sus, ale subspațiilor $ \mathbb{R}^2 $ sau $ \mathbb{R}^3 $.
Motivul este oarecum subtil, de aceea îl includem în această observație suplimentară.

Să ne amintim cîteva generalități de bază în teoria sistemelor de ecuații liniare.
Mai întîi, dacă un sistem are același număr de ecuații și necunoscute, atunci
dacă este compatibil (dacă are soluție), cu siguranță are soluție unică, adică
este sistem Cramer. Mai mult, dacă sistemul este și omogen, cu siguranță soluția
unică este cea nulă. De pildă, sistemul:
```{math}
\begin{cases}
  x - y + 3z &= 0 \\
  2x + y - z &= 0 \\
  x + y + z &= 0
\end{cases}
```
are matricea sistemului $ A = \begin{pmatrix} 1 & -1 & 3 \\ 2 & 1 & -1 \\ 1 & 1 & 1 \end{pmatrix} $,
al cărei determinant este $ 8 $, deci sistemul este Cramer. Cum $ (0, 0, 0) $ este evident soluție,
ea trebuie să fie *unica* soluție.

Pe de altă parte, dacă avem un număr de ecuații strict mai mic decît cel al necunoscutelor,
cu siguranță vom avea un sistem compatibil nedeterminat. De exemplu, sistemul:
```{math}
\begin{cases}
  x + 3y - z + t - u &= 0 \\
  2x + y + z - 3t + 2u &= 0
\end{cases}
```
are 2 ecuații și 5 necunoscute. Cum rangul matricei sistemului este evident 2, rezultă
că ambele ecuații sînt principale, așadar sistemul va fi *triplu nedeterminat*.
Cu alte cuvinte, soluția se va prezenta în funcție de 3 parametri, pe care îi putem
alege ca fiind necunoscutele secundare.

Așadar, soluția sistemului va fi un subspațiu al lui $ \mathbb{R}^5 $.

Prezentăm acum legătura cu exemplele geometrice anterioare, pe cazuri simple.
Un punct poate fi determinat ca intersecția a două drepte. Cum dreptele din plan
au ecuații de gradul întîi, rezultă că un sistem de ecuații de forma:
```{math}
\begin{cases}
  ax + by &= 0 \\
  cx + dy &= 0
\end{cases}, \quad a, b, c, d \in \mathbb{R}, ad - bc \neq 0
```
caracterizează un punct, ca intersecția celor două drepte reprezentate de cele două
ecuații. Condiția $ ad - bc \neq 0 $ spune că determinantul acestui sistem este
nenul, deci sistemul este Cramer, de unde rezultă că soluția sistemului va fi
soluția nulă, adică cele două drepte se intersectează în origine.

Mai departe, în spațiu, o dreaptă poate fi determinată ca intersecția a două plane.
Ecuația generală a unui plan este de forma $ ax + by + cz + d = 0, a, b, c, d \in \mathbb{R} $, 
iar dacă vrem ca planul să treacă prin origine, trebuie să avem $ d = 0 $.

Rezultă că un sistem de ecuații de forma:
```{math}
\begin{cases}
  a_1 x + b_1 y + c_1 z &= 0 \\
  a_2 x + b_2 y + c_2 z &= 0
\end{cases}, \quad a_{1,2}, b_{1,2}, c_{1,2} \in \mathbb{R}, \dfrac{a_1}{a_2} \neq \dfrac{b_1}{b_2} \neq \dfrac{c_1}{c_2}
```
caracterizează o dreaptă în spațiu, obținută ca intersecția a două plane.
Cum planele conțin originea, iar sistemul este compatibil (simplu nedeterminat, din condiția
cu neegalitatea rapoartelor respective), rezultă că și dreapta de intersecție va trece prin
origine.

Așadar, un sistem de 2 ecuații și 3 necunoscute va caracteriza o dreaptă în spațiu,
ca intersecție a două plane, deci un subspațiu al lui $ \mathbb{R}^3 $.

Similar putem generaliza și pentru mai multe necunoscute, însă lucrurile sînt mai greu
de vizualizat. De pildă, soluția unui sistem omogen cu 3 ecuații și 4 necunoscute
va fi un plan etc.

---

## Alte exemple
Revenim acum la exemple de subspații vectoriale, care, însă, vor avea ceva mai
mică relevanță geometrică. Aceasta cel puțin pînă vom studia noțiunea de *dimensiune*
a unui spațiu vectorial, cînd multe lucruri aparent diferite se vor lega strîns.

**Exemplu:** Dacă $ V = M_2(\mathbb{R}) $ este spațiul real de matrice pătratice
$ 2 \times 2 $ cu elemente reale, atunci putem lua:
```{math}
W = \{ A \in M_2(\mathbb{R}) \mid A = A^t \}.
```
Scriind aceasta pe componente, presupunem $ A = \begin{pmatrix} a & b \\ c & d \end{pmatrix} $,
iar condiția din definiție se scrie:
```{math}
\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix} = %
\begin{pmatrix}
  a & c \\
  b & d
\end{pmatrix}
```
de unde obținem $ b = c $, deci $ A = \begin{pmatrix} a & b \\ b & d \end{pmatrix} $.
Astfel de matrice se numesc *simetrice*.

Precum vă puteți convinge ușor, ele alcătuiesc un subspațiu al lui $ V $ (exercițiu!).

**Exemplu:** Dacă $ V = \mathbb{R}[X] $, atunci putem lua $ W = \mathbb{R}_n[X] $,
pentru orice $ n \in \mathbb{N} $ și obținem, evident, un subspațiu. Cum înmulțirea
polinoamelor nu este permisă, rezultă că gradul nu se poate modifica, așadar
oricum am opera cu polinoame din $ \mathbb{R}_{n}[X] $, rezultatul va fi un polinom
din aceeași mulțime (grup de vectori).

**Exemplu:** Dacă $ V = \mathbb{R}_3[X] $ și luăm:
```{math}
W = \{ p \in \mathbb{R}_{3}[X] \mid p(2) = 0 \}
```
obținem un subspațiu. Într-adevăr, putem scrie generic:
```{math}
V = \{ p = a + bX + cX^2 + dX^3 \mid a, b, c, d \in \mathbb{R} \}
```
Atunci:
```{math}
W = \{ p = a + bX + cX^2 + dX^3 \mid a + 2b + 4c + 8d = 0 \}
```
și nu e greu de observat că, de fapt, putem trata $ W $ ca pe spațiul soluțiilor
unui „sistem“ liniar cu o ecuație și 4 necunoscute -- care va fi compatibil
triplu nedeterminat. Așadar, $ W \leq V $.

**Exemplu:** Și fiindcă am făcut analogia anterioară, să adăugăm și că o modificare minoră
a datelor de mai sus, precum:
```{math}
W = \{ p = a + bX + cX^2 + dX^3 \mid p(2) = 1 \}
```
face ca $ W $ să nu mai fie subspațiu. Aceasta deoarece „sistemul“ la care se ajunge
nu mai este omogen:
```{math}
a + 2b + 4c + 8d = 1,
```
deci nu poate conține polinomul nul ($a = b = c = d = 0$).

**Exemplu:** Să încheiem cu un exemplu care arată că orice ecuație care nu este liniară
nu poate produce subspații vectoriale. Pentru simplitate, fie $ V = \mathbb{R}^2 $
și submulțimea:
```{math}
W = \{ (x, y) \in \mathbb{R}^2 \mid y = x^2 \} = \{ (x, x^2) \mid x \in \mathbb{R} \}
```
Arătăm că $ W \nleq V $, chiar dacă, evident, conține originea. Geometric, $ W $
este reprezentat de o parabolă cu vîrful în origine și cu ramurile în sus:
```{figure} ./img/parabola.png
---
name: fig-parabola
---
Parabola $ (x, x^2) \in \mathbb{R}^2 $ *nu* formează un subspațiu vectorial al planului $ \mathbb{R}^2 $
```
Să încercăm să demonstrăm că $ W $ ar fi subspațiu, folosind definiția. Fie, deci,
doi vectori din $ W $, $ a = (x_1, y_1) $ și $ b = (x_2, y_2) $, cu
$ y_1 = x_1^2 $ și $ y_2 = x_2^2 $. Fie și doi scalari $ \alpha, \beta \in \mathbb{R} $
și scriem combinația liniară:
```{math}
\alpha a + \beta b = (\alpha x_1 + \beta x_2, \alpha y_1 + \beta y_2 )
```
Pentru ca acest vector să aparțină lui $ W $, ar trebui ca a doua componentă să fie
egală cu pătratul primeia, ceea ce este evident fals:
```{math}
(\alpha x_1 + \beta x_2)^2 = \alpha^2 x_1^2 + \beta^2 x_2^2 + 2\alpha\beta x_1x_2 %
\neq \alpha y_1 + \beta y_2
```
știm deja că $ x_1^2 = y_1 $ și $ x_2^2 = y_2 $, însă nu putem ignora termenul
mixt $ 2 \alpha\beta x_1 x_2 $. În plus, scalarii care apar la pătrat de asemenea diferă.

Acest exemplu ne arată, deci, că nici în cele mai simple cazuri nu putem accepta expresii
care nu sînt liniare (adică de gradul întîi) în spații vectoriale.

În particular, rezultă că subspațiile planului $ \mathbb{R}^2 $ sînt *numai dreptele*
care conțin originea și nicio altă curbă.

## Exerciții propuse
În fine, cîteva exerciții standard, computaționale, care se concentrează în special
pe noțiunea de subspațiu vectorial.

În toate exemplele de mai jos, studiați dacă $ V $ este subspațiu al lui $ W $.
Vă sugerăm să vă gîndiți la mai multe argumente, acolo unde este posibil: computațional, 
geometric, intuitiv și să faceți legături cu situații întîlnite anterior:

1. $ V = \{ (x, y) \in \mathbb{R}^2 \mid 3x - y = 0 \}, W = \mathbb{R}^2 $.
2. $ V = \{ (x, y, z) \in \mathbb{R}^3 \mid 3x - y = 0 \}, W = \mathbb{R}^3 $.
3. $ V = \{ (x, y, z) \in \mathbb{R}^3 \mid x = 0 \}, W = \mathbb{R}^3 $.
4. $ V = \{ p \in \mathbb{R}_2[X] \mid p(1) = 0 \}, W = \mathbb{R}_{3}[X] $.
5. $ V = \{ p \in \mathbb{R}_2[X] \mid p'(1) = 0 \}, W = \mathbb{R}_{2}[X] $.
6. $ V = \{ (x, y, z) \in \mathbb{R}^3 \mid 2x - y = 0 \text{ și } 3x - y + z = 0 \}, W = \mathbb{R}^3 $.
7. $ V $ de la exercițiul anterior și $ W = \mathbb{R}^7 $.
8. $ V = \{ A \in M_2(\mathbb{R}) \mid \mathrm{tr}(A) = 0 \}, W = M_2(\mathbb{R}) $.
Am notat cu $ \mathrm{tr}(A) $ *urma* (eng. *trace*) matricei $ A $, adică suma
elementelor de pe diagonala principală: dacă $ A = (a_{ij})_{1 \leq i,j \leq n} $, 
atunci $ \mathrm{tr}(A) = \displaystyle\sum_{0 \leq i \leq n} a_{ii} $.
