# Monoizi și grupuri

Monoizii și grupurile sînt primele exemple de structuri algebrice ale căror
proprietăți se inspiră din structuri pe care le avem la îndemînă. Sînt structuri
care folosesc o singură operație, cu anumite proprietăți, iar prototipul este
acela al *mulțimii numerelor întregi*, împreună cu operația de adunare.

Să examinăm mai întîi acest exemplu și extragem apoi proprietățile abstracte.

Mulțimea numerelor întregi conține numerele naturale, împreună cu cele negative
corespunzătoare. Așadar, vom presupune că înțelegem ce înseamnă elementele acestei
mulțimi.

Operația pe care o folosim este aceea de adunare, care în acest caz are proprietățile
[amintite](./p2-abstract.md), pe care le reformulăm și completăm într-o manieră mai
potrivită:
- suma oricăror două numere întregi este un număr întreg; cu alte cuvinte, cînd operăm
cu adunarea între numere întregi, nu avem „surprize“: obținem de fiecare dată numere
din aceeași mulțime;
- adunarea este comutativă, adică nu depinde de ordinea termenilor; altfel spus,
`a + b = b + a`, pentru orice două numere întregi `a` și `b`;
- adunarea este asociativă, adică putem aplica oricîte paranteze într-o expresie
care conține cel puțin trei termeni. De exemplu, `a + (b + c) = (a + b) + c`,
pentru orice trei numere întregi `a, b, c`;
- există un element special, numărul `0`, cu proprietatea că dacă îl adunăm cu orice
alt număr întreg, obținem tot numărul inițial. Altfel spus, `a + 0 = 0 + a = a`, pentru
orice număr întreg `a`;
- pentru orice număr întreg, există unul care îl *anulează* -- atît în sens propriu, cît și
figurat. Altfel spus, pentru orice număr întreg `a`, există un alt număr întreg `b`, cu 
proprietatea că `a + b = b + a = 0`. Evident, `b = -a` și se numește *opusul* lui `a`.

Proprietățile sus-menționate constituie exact definiția structurii algebrice de grup,
pe care formulăm riguros chiar acum.

```{prf:definition}
:label: def-grup

Fie $ A $ o mulțime nevidă și $ \ast $ o operație binară[^binar] pe $ A $.

[^binar]: O operație binară este o regulă care combină două elemente pentru a obține un al treilea.
Nu intrăm în detalii specifice, însă adăugăm că adunarea și înmulțirea, de pildă, sînt operații binare, 
deoarece combină două elemente pentru a obține un al treilea --- suma, respectiv produsul lor.

Spunem că perechea $ (A, \ast) $ formează un *grup* dacă:

- $ \ast $ este *lege internă*, adică $ a \ast b \in A, \forall a, b \in A $;
- $ \ast $ este *asociativă*, adică $ a \ast (b \ast c) = (a \ast b) \ast c, \forall a, b, c \in A $;
- există un element $ e \in A $, numit *element neutru*, cu proprietatea că $ a \ast e = e \ast a = a, \forall a \in A $;
- pentru orice element $ a \in A $, există un element $ b \in A $, numit *simetricul* lui $ a $, cu proprietatea că $ a \ast b = b \ast a = e $, elementul neutru.

Dacă, în plus, operația $ \ast $ este și comutativă, adică $ a \ast b = b \ast a, \forall a, b \in A $, atunci grupul $ (A, \ast) $ se numește *comutativ* sau *abelian*[^abelian].
[^abelian]: Denumirea este dată în onoarea matematicianului norvegian Niels Henrik Abel (1802-1829), unul dintre pionierii algebrei abstracte.
```

Definiția de mai sus -- care vine să formalizeze ceea ce am prezentat ca exemplu prin mulțimea
numerelor întregi, împreună cu operația de adunare -- este pentru o structură destul de permisivă.
Însă putem avea și restricții mai mari. De pildă, putem renunța la condiția ca fiecare element să aibă
un simetric și obținem *monoizi*. Definiția urmează (a se compara cu cea a grupurilor, noțiunile-cheie
avînd exact aceleași înțelesuri):

```{prf:definition}
:label: def-monoid

Fie $ A $ o mulțime nevidă și $ \ast $ o operație binară pe $ A $.

Spunem că perechea $ (A, \ast) $ formează un *monoid* dacă:

- $ \ast $ este *lege internă*;
- $ \ast $ este *asociativă*;
- există un element $ e \in A $, numit *element neutru*, cu proprietatea că $ a \ast e = e \ast a = a, \forall a \in A $.

Dacă, în plus, operația este și comutativă, atunci monoidul se numește *comutativ*.
```

Un exemplu la îndemînă este acela al mulțimii numerelor *naturale* cu adunarea. În acest caz,
elementul neutru fiind `0`, constatăm că niciun număr natural nu are un simetric. Pentru orice număr
natural `a`, nu există un alt număr *natural* `b` astfel încît `a + b = b + a = 0`.

Putem face o analiză similară folosind înmulțirea. De fapt, aceste exemple (folosind adunarea și înmulțirea)
sînt atît de importante, încît au influențat și terminologia specifică, pe care o detaliem în continuare.

## Terminologie specifică
Adunarea și înmulțirea numerelor (naturale, întregi, raționale, reale etc.) sînt exemple care evidențiază
cele mai importante proprietăți. De aceea, terminologia specifică a acestora s-a transmis și în cazul general.

În acest sens, avem următoarele noțiuni (pe care le exemplificăm după aceea):
- dacă operația pe care o folosim se definește cu ajutorul adunării, atunci elementul neutru se mai numește
*elementul nul* sau chiar *zero* al operației;
- tot cînd operația pe care o folosim se definește cu ajutorul adunării, simetricul unul element se mai
numește *opusul* său;
- dacă operația pe care o folosim se definește cu ajutorul înmulțirii, elementul neutru se mai numește
*elementul unitate* sau *unitate* sau chiar *unu* al operației;
- tot cînd operația folosită se definește cu ajutorul înmulțirii, simetricul unui element se mai numește
*inversul* său.

```{note}
În general, simetricul elementului $ x $ se notează $ x' $, iar în cazurile particulare,
opusul lui $ x $ se notează $ -x $ și inversul său, $ x^{-1} $.
```

Iată două exemple:

**Exemplu:** Considerăm pe mulțimea numerelor reale $ \mathbb{R} $ operația $ \ast $, definită prin:

$$ x \ast y = x + y - 5, \forall x, y \in \mathbb{R} $$

Evident, operația se definește cu ajutorul adunării. În acest caz, avem:
- elementul neutru -- care se numește *element nul* -- este numărul 5 (puteți verifica ușor că $ x \ast 5 = 5 \ast x = x, \forall x \in \mathbb{R} $);
- simetricul unui element $ x $ -- care se numește *opusul său* -- este elementul $ 10 - x $ (puteți verifica ușor că $ x \ast (10 - x) = (10 - x) \ast x = 5, \forall x \in \mathbb{R} $).

Pentru cazul înmulțirii, putem avea similar:

**Exemplu:** Considerăm pe mulțimea numerelor raționale $ \mathbb{Q} \setminus \{ 0 \} $[^nenul] operația $ \ast $, definită prin:

$$ x \ast y = 3xy, \forall x, y \in \mathbb{Q} \setminus \{ 0 \} $$

Evident, operația se definește cu ajutorul înmulțirii și avem (puteți verifica fiecare afirmație):
- elementul neutru -- care se numește *element unitate* -- este numărul $ \dfrac{1}{3} $;
- simetricul unui element $ x $ -- care se numește *inversul său* -- este elementul $ \dfrac{1}{9x} $.

[^nenul]: De remarcat că trebuie să eliminăm numărul 0, întrucît el va încălca o proprietate definitorie
pentru grupuri: nu va avea un simetric (justificați!).

În general, dacă există riscul de confuzie, vom evita folosirea acestei terminologii.
Dar în același timp, ea este foarte utilă pentru a ne aminti de cele mai importante exemple.

## Exemple suplimentare
Schițăm în continuare și alte exemple de monoizi și grupuri. Vă invităm să completați detaliile
pentru a vă convinge că structurile, împreună cu operațiile respective, formează monoizi sau grupuri.

**Exemplu:** Pe mulțimea numerelor reale pozitive $ \mathbb{R} $ definim operația:

$$ x \ast y = \sqrt[3]{x^3 + y^3}, \forall x, y \in \mathbb{R}. $$

Vă puteți convinge ușor că avem de-a face cu un grup, unde:
- elementul neutru este $ e = 0 $;
- simetricul unui element $ x \in \mathbb{R} $ este $ -x $.

**Exemplu:** Putem lucra și cu matrice, de exemplu, fie $ A = M_2(\mathbb{R}) $, operația
fiind adunarea matricelor. Adică, pentru $ X = \begin{pmatrix} a & b \\ c & d \end{pmatrix} $
și $ Y = \begin{pmatrix} e & f \\ g & h \end{pmatrix} $, avem:

$$ X + Y = \begin{pmatrix} a + e & b + f \\ c + g & d + h \end{pmatrix} $$

În acest caz:
- elementul neutrul este matricea nulă, $ E = 0_2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} $;
- simetrica unei matrice $ X $ ca mai sus este matricea $ -X = \begin{pmatrix} -a & -b \\ -c & -d \end{pmatrix} $.


**Exemplu:** Pe de altă parte, dacă lucrăm cu înmulțirea matricelor (cu 2 linii și 2 coloane, avînd elemente reale),
obținem doar un monoid, deoarece nu orice matrice este inversabilă (într-adevăr, elementul neutru ar fi
matricea $ I_2 $, așadar simetrica unei matrice $ X $ coincide cu inversa acesteia $ X^{-1} $,
care nu există decît dacă $ \det(X) \neq 0 $.

Putem regla acest lucru folosind doar matrice inversabile, care formează un grup denumit
*grupul general liniar*, notat în cazul nostru $ GL_2(\mathbb{R}) $.

```{note}
Lucrul cu matrice, în special pătratice, din $ M_2(\mathbb{R}) $ sau $ M_3(\mathbb{R}) $
va fi foarte important pentru aplicațiile geometrice și de grafică pe care le vom studia
ulterior.

Pe lîngă grupul general liniar, mai există și alte cazuri particulare, precum grupul
special liniar, ortogonal și special ortogonal, cu proprietăți și aplicații deosebite,
pe care le vom detalia la momentul respectiv.
```

## Exerciții propuse
1. Dați un alt exemplu de monoid care să nu fie grup, în afara celui al numerelor naturale
cu adunarea și celui al numerelor întregi cu înmulțirea.
2. Dați exemplu de un grup care să nu fie comutativ.
3. Dați exemplu de un monoid (care nu e grup) care să nu fie comutativ.
4. Ce proprietăți are operația $ (x, y) \mapsto x $, definită pentru numere reale?
5. Ce proprietăți are operația $ (x, y) \mapsto x^2 + y^2 $ definită pentru numere întregi?
6. Demonstrați că operația $ (x, y) \mapsto \dfrac{4x + 4y}{4 + xy} $, definită pe intervalul
$ A = (-2, 2) $ conduce la o structură de grup comutativ.
7. Pe mulțimea punctelor din plan (formal, $ \mathbb{R}^2 = \mathbb{R} \times \mathbb{R} $)
definim operația $ P \ast Q = $ mijlocul segmentului $ [PQ] $, pentru orice două puncte $ P, Q \in \mathbb{R}^2 $.
Ce proprietăți are această operație?
8. Pe mulțimea numerelor naturale se definește operația $ x \ast y = (x + y) \ \mathrm{mod} \ 13, \forall x, y \in \mathbb{N} $,
adică restul împărțirii sumei $ x + y $ la $ 13 $ (operația *modulo*, simbolizată în programare de obicei cu operatorul `%`).
Ce proprietăți are această operație?
9. Pe intervalul $ (0, \infty) $ se definește operația $ x \ast y = x^{\ln y}, \forall x, y > 0 $.
Ce proprietăți are această operație?

(sec-substructuri-morfisme)=
## Substructuri și morfisme
### Intuiție
În general, matematicienii (și nu numai) caută să obțină cît mai multe obiecte, structuri
și informații „gratis“, adică prin particularizare sau eliminarea treptată a unor proprietăți,
condiții, cerințe etc.

Două dintre cele mai simple metode de a obține structuri noi aproape „gratis“ sînt
cu ajutorul substructurilor și morfismelor.

Substructurile se formează într-o manieră foarte simplă: se dă o structură (monoid, grup, inel, corp etc.)
și ne întrebăm cît de multe elemente putem elimina, dar să păstrăm totuși, proprietățile structurii.
Imaginați-vă o pictură foarte detaliată a unui animal, de pildă. Ea se identifică imediat și e clar
dintr-o privire ce animal reprezintă. Acum ne întrebăm: ce putem elimina din pictura respectivă,
dar imaginea de ansamblu să nu aibă de suferit, adică în continuare să fie clar că reprezintă
animalul în cauză? Putem șterge, poate, fundalul? Putem elimina din părțile corpului animalului?

De remarcat, totuși, că nu avem voie să *schimbăm* elemente ale picturii, ci doar să eliminăm
din cele prezente. De pildă, nu este permis să schimbăm culoarea animalului -- chiar dacă acest
lucru nu l-ar face de nerecunoscut. În cazul unei picturi a unui cîine pe o pajiște înverzită,
putem elimina iarba de pe pajiște sau putem păstra doar capul cîinelui, dar nu avem voie să
schimbăm culoarea ierbii ori a cîinelui, să zicem.

Ceea ce se obține în cazul unei astfel de eliminări este o substructură, adică un obiect
care este *o parte* a obiectului inițial, este inclus în el. 

Abstract, în cazul numerelor, dacă lucrăm, de exemplu, cu mulțimea numerelor întregi și 
să presupunem că pornim cu grupul $ (\mathbb{Z}, +) $, ne putem întreba ce numere putem elimina,
dar astfel încît submulțimea lui $ \mathbb{Z} $ pe care o obținem încă să fie grup în raport
cu aceeași operație de adunare. 

În primă fază, ne putem gîndi că eliminăm doar cîteva numere,
să zicem $ A = \mathbb{Z} \setminus \{ 1, -2, 6 \} $. Ne întrebăm: este $ (A, +) $ grup?
Răspunsul destul de ușor de văzut este negativ (justificați!), iar după mai multe încercări,
vom constata că nu este o idee bună să eliminăm doar cîteva numere oarecare, ci va trebui
să renunțăm la submulțimi întregi, caracterizate prin anume proprietăți. De pildă,
submulțimea notată $ 2 \mathbb{Z} $, a numerelor întregi pare, formează o structură de grup
în raport cu adunarea. Ce puteți spune despre mulțimea numerelor întregi impare (care nu are
o notație anume)? Mai general, dacă notăm $ n \mathbb{Z} = \{ nx \mid x \in \mathbb{Z} $,
pentru $ n \in \mathbb{Z} $ fixat -- submulțimea multiplilor unui număr fixat $ n $ --,
în ce cazuri este $ (n\mathbb{Z}, +) $ un grup?

Așadar, ca idee generală, reținem că pentru a obține o substructură, nu avem decît să 
eliminăm o parte a elementelor structurii inițiale, dar astfel încît operația cu care
vine structura să inducă în continuare același tip de structură și pe submulțime.

Simbolic, $ A $ formează o substructură (e.g. subgrup, submonoid) pentru structura
(e.g. grupul, monoidul) $ (B, \ast) $ dacă $ A \subseteq B $ și $ (A, \ast) $ are
aceeași structură ca $ (B, \ast) $.

În cazul concret de mai sus, am văzut că $ 2\mathbb{Z} $ este un subgrup al grupului
$ (\mathbb{Z}, +) $.

---

În ce privește morfismele, lucrurile par complicate inițial, însă ideea este similară cu
cea din cazul substructurilor. Cheia este, într-un fel, chiar în denumire. Cuvîntul
*morfism* se leagă de grecescul μορφώ (*morpho*), care înseamnă, generic, „formă“.
Așadar, un morfism este o construcție care trans-formă sau, mai general, care afectează
sau păstrează forma unei structuri.

Înainte de a da detaliile concrete, să ne mai amintim că în matematică, trans-formările
se fac, de obicei, cu ajutorul funcțiilor. De pildă, dacă vrem să transformăm numerele
naturale în numere pare, definim funcția $ f : \mathbb{N} \to \mathbb{N}, f(x) = 2x $
sau dacă vrem să transformăm perechile de numere întregi în numere raționale, definim
funcția $ f : \mathbb{Z} \times \mathbb{Z}^\ast \to \mathbb{Q}, f(x, y) = \dfrac{x}{y} $.

La fel stau lucrurile și în ce privește structurile algebrice. Un morfism este o funcție
care păstrează structura. Am spus la începutul acestei secțiuni că, odată obținută
o structură, scopul ar fi să încercăm să obținem „gratis“ și altele. Pe lîngă considerarea
substructurilor -- adică eliminarea unor submulțimi din structurile inițiale -- putem
opera și cu ajutorul morfismelor, adică să trans-formăm o mulțime într-o alta, cu proprietatea
că dacă mulțimea inițială era înzestrată cu o structură algebrică, atunci și mulțimea în care
aceasta se transformă să aibă aceeași structură.

Putem da direct un exemplu, pentru că substructura de mai sus se poate scrie și sub forma
unui morfism. Pornim cu grupul $ (\mathbb{Z}, +) $ și definim funcția 
$ f : \mathbb{Z} \to 2\mathbb{Z}, f(x) = 2x $, funcția de dublare. În acest caz, practic,
facem un *transfer de structură* de la $ (\mathbb{Z}, +) $ la $ (2\mathbb{Z}, +) $
și obținem (aproape) „gratis“ încă un grup. Sigur, putem argumenta că motivul pentru care
știm că $ 2\mathbb{Z} $ este un grup provine de la analiza substructurii, așa că morfismul
nu mai aduce nicio informație suplimentară. Însă vom vedea imediat că, de fapt, puteam porni
și invers: am fi putut demonstra că $ (2\mathbb{Z}, +) $ este un grup doar folosind
morfismul $ f $.

### Definiții formale
Pe baza explicațiilor intuitive de mai sus, să dăm acum definițiile formale și exemple suplimentare.

```{prf:definition}
:label: def-submonoid
Fie $ (A, \ast) $ un monoid (comutativ) și $ B \subseteq A $ o submulțime a lui $ A $.

Spunem că $ B $ este un *submonoid* al lui $ A $ dacă $ (B, \ast) $ este monoid (comutativ).
```

Nu pare mare lucru ceea ce am definit mai sus și, într-adevăr, din punct de vedere practic,
nu este eficient să demonstrăm *din nou* proprietățile monoidului pentru o submulțime, din moment
ce știm deja proprietățile monoidului inițial. De aceea, în exerciții, cel mai adesea
se folosesc rezultate simplificate, iar nu definiția. Ideea de bază este că unele proprietăți
(precum comutativitatea și asociativitatea) se preiau automat la submulțimi, deci oricum
nu trebuie verificate din nou.

Varianta cea mai scurtă și practică este:

```{prf:theorem}
:label: thm-submonoid
Fie $ (A, \ast) $ un monoid (comutativ) și $ B \subseteq A $ o submulțime a lui $ A $.

Atunci $ B $ este submonoid dacă și numai dacă au loc:
- $ e \in B $;
- $ \forall x, y \in B, x \ast y \in B $.
```

Altfel spus, este suficient să verificăm că $ B $ preia elementul neutru și proprietatea
de lege internă.

```{note}
În general, faptul că $ B $ este o substructură a lui $ A $ se notează
$ B \leq A $, indiferent de tipul structurii (cu excepția cazului cînd structura în sine
implică mai multe mulțimi, cum va fi cazul spațiilor vectoriale).

Dacă $ B \leq A $ înseamnă submonoid, subgrup, subinel sau subcorp se deduce,
de obicei, din context. 

În unele situații, pentru a fi și mai expliciți, se pot scrie
și operațiile, adică putem avea, de pildă, $ (B, \ast, \circ) \leq (A, \ast, \circ) $
în cazul unui subinel sau $ (B, \ast) \leq (A, \ast) $ în cazul unui subgrup.
```

În cazul grupurilor, lucrurile stau foarte asemănător:

```{prf:definition}
:label: def-subgrup
Fie $ (A, \ast) $ un grup (comutativ) și $ B \subseteq A $ o submulțime a lui $ A $.

Spunem că $ A $ este *subgrup* dacă $ (A, \ast) $ este grup (comutativ).
```

În practică, vom folosi:

```{prf:theorem}
:label: thm-subgrup
Fie $ (A, \ast) $ un grup (comutativ) și $ B \subseteq A $ o submulțime a lui $ A $.

Atunci $ B $ este subgrup dacă și numai dacă $ x \ast y' \in B, \forall x, y \in B $.
```

În relația din teoremă avem concentrate toate proprietățile (sub)grupului:
- asociativitatea și, eventual, comutativitatea se preiau oricum de la grupul ambiant;
- elementul neutru se preia luînd $ y = x $, caz în care $ x \ast x' = e $;
- proprietatea de lege internă se preia în doi pași:
  + mai întîi, putem lua $ x = e $ și avem că $ y' \in B, \forall y \in B $;
  + apoi, legea internă rezultă imediat: $ x \ast y' \in B, \forall x, y' \in B $.

**Exemplu:** Pentru monoidul $ (\mathbb{N}, +) $ avem submonoidul $ 2\mathbb{N} $,
alcătuit din numerele naturale pare:
- într-adevăr, $ 0 \in 2\mathbb{N} $, deci $ 2\mathbb{N} $ preia elementul neutru;
- suma a două numere pare este un număr par, deci $ 2\mathbb{N} $ preia proprietatea
de lege internă a adunării.

Așadar, $ 2\mathbb{N} \leq \mathbb{N} $.

**Exemplu:** Similar se poate demonstra și că $ 2 \mathbb{Z} $ este submonoid al
lui $ (\mathbb{Z}, \cdot) $ (exercițiu!).

**Exemplu:** Dacă considerăm, de exemplu, $ 3\mathbb{Z} = \{ 3x \mid x \in \mathbb{Z} \} $,
vom constata că nu formează un submonoid pentru $ (\mathbb{Z}, \cdot) $:
- produsul a doi multipli de 3 este un multiplu de 3: $ 3x \cdot 3y = 3 \cdot (3xy), \forall x, y \in \mathbb{Z} $;
- dar elementul neutru, numărul 1, nu este multiplu de 3, așadar $ 1 \notin 3\mathbb{Z} $.

**Exemplu:** Pornind cu grupul matricelor inversabile, $ GL_2(\mathbb{R}) $, putem defini:

$$ A = \{ M \in GL_2(\mathbb{R}) \mid \det(A) = \text{ număr impar sau} \dfrac{1}{t}, \text{ cu } t \text{ impar} \} $$

Atunci putem constata că $ (A, \cdot) \leq (GL_2(\mathbb{R}), \cdot) $, 
folosind {prf:ref}`thm-subgrup`, dacă $ M, N \in A $, atunci $ \det(M) $ și $ \det(N) $ sînt
numere impare sau inverse de numere impare. Atunci $ \det(N^{-1}) = \dfrac{1}{\det(N)} $,
care este tot un număr impar sau un invers de număr impar. În fine,
cum $ \det(M \cdot N^{-1}) = \det(M) \cdot \det(N^{-1}) $, avem concluzia.

Așadar, $ A $ formează un subgrup al lui $ GL_2(\mathbb{R}) $. Cum nici grupul inițial nu era
comutativ, nici subgrupul $ A $ nu are această proprietate.

---

Pe scurt, reținem, deci, că o substructură este o submulțime a unei structuri
algebrice care păstrează proprietățile relevante (algebric).

Așa cum vom vedea imediat, este un caz particular al morfismelor.

---

Începem chiar cu definiția abstractă, chiar dacă impactul inițial va fi puternic.
Însă vom clarifica lucrurile imediat.

```{prf:definition}
:label: def-morfism

Fie $ (A, \ast) $ și $ (B, \circ) $ două grupuri (monoizi) și $ f : A \to B $ o funcție.

Spunem că $ f $ este un *morfism* de grupuri (monoizi) dacă:

$$ f(x \ast y) = f(x) \circ f(y), \quad \forall x, y \in A. $$
```

Dacă presupunem că avem deja date cele două structuri $ A $ și $ B $, atunci $ f $
realizează o corespondență, un fel de „dicționar“ între acestea, dar astfel încît
să se păstreze proprietățile algebrice. Să examinăm cu atenție definiția:
- pornim cu două elemente arbitrare $ x, y \in A $;
- între ele, are sens operația $ \ast $, deci calculăm $ x \ast y $, care este tot un element din $ A $;
- rezultatul îl „trimitem“ cu funcția $ f $, către un element al lui $ B $, adică $ f(x \ast y) \in B $;
- pe de altă parte, putem trimite și elementele individuale, adică $ f(x) \in B $, $ f(y) \in B $;
- între aceste imagini are sens operația $ \circ $, deci putem calcula $ f(x) \circ f(y) $;
- proprietatea de morfism cere ca aceste calcule să coincidă. Altfel spus, fie că luăm două elemente
și aplicăm operația corespunzătoare între ele, apoi trimitem rezultatul prin $ f $, fie că trimitem
mai întîi elementele și aplicăm operația corespunzătoare între imaginile lor, trebuie să obținem același lucru.

Lucrurile sînt mai simple decît par: Cazul cel mai ușor este acela al funcției *incluziune*.
Dacă, de exemplu, $ A \subseteq B $ și $ \ast = \circ $, atunci proprietatea de morfism se satisface
automat pentru funcția incluziune, care nu este altceva decît funcția identitate: trimitem elementele
din mulțimea mai mică $ A $ către mulțimea mai mare $ B $ fără nicio transformare: $ f(x) = x, \forall x \in A $,
pentru că $ x $ deja se găsește și în $ B $.

Comentariul anterior ne arată că morfismul este o generalizare a substructurii. Dar, bineînțeles,
există și alte modalități de a utiliza și evidenția un morfism. Una dintre cele mai importante
este aceea a *izomorfismelor*, care sînt *morfisme bijective*. Pe scurt, avem:

```{prf:definition}
:label: def-izo

Fie $ (A, \ast) $ și $ (B, \circ) $ două grupuri (monoizi) și $ f : A \to B $ un morfism.

Dacă $ f $ este o funcție bijectivă, atunci grupurile (monoizii) $ A $ și $ B $ se numesc
*izomorfe* și scriem $ A \simeq B $.

În cazul particular cînd cele două structuri coincid, deci $ A = B $, izomorfismul
se numește *automorfism*.
```

În fapt, ca să nu ne pierdem în detalii tehnice[^bij], pentru a arăta că două grupuri $ A $ și $ B $ sînt izomorfe,
de pildă, pornim cu o funcție (dată sau construită de noi), $ f : A \to B $, pentru care arătăm:
- $ f $ este morfism, conform definiției {prf:ref}`def-morfism`;
- arătăm că există $ g : B \to A $ o altă funcție, care:
  + este de asemenea morfism;
  + este inversa lui $ f $, adică $ f(g(x)) = g(f(x)) = x $, pentru orice element $ x $.

[^bij]: Riguros, lucrurile stau ceva mai complicat. O funcție bijectivă este o funcție care este
simultan injectivă și surjectivă. Fiecare dintre aceste proprietăți trebuie verificată separat,
prin metode specifice. Aici, însă, este suficient să înțelegem noțiunile de bază, la un nivel
mai scăzut al rigorii.

**Exemplu:** Considerăm grupul aditiv al numerelor complexe, $ (\mathbb{C}, +) $.
Fie funcția $ f : \mathbb{C} \to \mathbb{C}, f(z) = \overline{z} $, funcția de conjugare.

Se poate verifica imediat că $ f $ este automorfism, întrucît:

**#TODO: De ce nu pune `overline`-ul pe sumă??**

- $ \overline{z + t} = \overline{z} + \overline{t}, \forall z, t \in \mathbb{C} $, deci $ f $ este morfism;
- $ \overline{\overline{z}} = z $, deci funcția este propria inversă.

**Exemplu:** Considerăm grupul aditiv al numerelor întregi, $ (\mathbb{Z}, +) $ și
grupul aditiv al numerelor întregi pare, $ (2\mathbb{Z}, +) $. Definim funcția
$ f : \mathbb{Z} \to 2\mathbb{Z}, f(x) = 2x, \forall x \in \mathbb{Z} $, funcția
de dublare. Avem:
- $ 2(x + y) = 2x + 2y, \forall x, y \in \mathbb{Z} $, deci funcția este un morfism;
- $ g : 2\mathbb{Z} \to \mathbb{Z}, g(t) = \dfrac{t}{2}, \forall t \in 2\mathbb{Z} $
este inversa lui $ f $, deci $ f $ este bijectivă, adică realizează un izomorfism.

Am arătat, așadar, că grupul $ \mathbb{Z} $ este izomorf cu un subgrup al său, $ 2 \mathbb{Z} $.

Astfel de rezultate sînt utile atunci cînd vrem să „traducem“ unele structuri în altele.
De exemplu, un izomorfism ne poate arăta că un număr complex este „același lucru“[^izo] cu o matrice
de un anumit tip:

[^izo]: De fapt, etimologic, izo-morfism provine din prefixul grecesc isos (ἴσος), care înseamnă
*la fel, egal*, atașat cuvîntului μορφή (morphe), care înseamnă *formă*.

**Exemplu:** Fie grupul multiplicativ al numerelor complexe de modul 1:

```{math}
A = \{ z \in \mathbb{C} \mid |z| = 1 \}
```

și grupul de matrice:

```{math}
B = \left\{ \begin{pmatrix} \cos \alpha & \sin \alpha \\ -\sin \alpha & \cos \alpha \end{pmatrix} \mid \alpha \in \mathbb{R}\right\}.
```

Faptul că ambele structuri sînt grupuri comutative puteți verifica ușor (exercițiu!).

```{margin}
Amintim, pentru un număr complex $ z = a + bi \in \mathbb{C} $ scris sub forma algebrică,
avem și *forma trigonometrică*, $ z = r(\cos \theta + i \sin \theta) $, unde
$ r = |z| = \sqrt{a^2 + b^2} $, iar $ \theta = \arctan \dfrac{b}{a} = \mathrm{Arg}(z) $,
*argumentul principal* al lui $ z $.

Vom reveni la aceste noțiuni în contextul transformărilor geometrice.
```
Definim funcția:

```{math}
f : A \to B, \quad f(z) = \begin{pmatrix} \cos \alpha & \sin \alpha \\ -\sin \alpha & \cos \alpha \end{pmatrix}, \text{ unde } \alpha = \mathrm{Arg}(z),
```

care preia *argumentul principal* al numărului complex $ z $.

Se poate demonstra destul de ușor (exercițiu!) că funcția $ f $ realizează un izomorfism,
ceea ce înseamnă că numerele complexe de modul unitate sînt „același lucru“ cu matricele
pătratice din $ B $.

Un exemplu similar, mai mult sau mai puțin surprinzător, este acesta:

**Exemplu:** Fie $ A = (\mathbb{R}, +) $, grupul aditiv al numerelor reale și

```{math}
B = \left\{ M(a) = \begin{pmatrix} 1 & a \\ 0 & 1 \end{pmatrix} \mid a \in \mathbb{R} \right \},
```

considerat împreună cu înmulțirea.

Se poate arăta ușor că $ (B, \cdot) $ este un grup comutativ și mai mult, că $ A \simeq B $, prin funcția:

```{math}
f : A \to B, \quad f(a) = M(a), \forall a \in \mathbb{R},
```
adică exact funcția care asociază unui număr real o matrice din $ B $ care depinde numai de
acel număr real.

---

### Un truc
Fără a fi suficient, putem folosi un mic truc în cazul izomorfismelor.
Deoarece o astfel de funcție arată, practic, faptul că două structuri sînt „la fel“
din punct de vedere algebric, rezultă, în consecință, că și elementele lor neutre trebuie
să corespundă. Imaginați-vă că un izomorfism este un fel de „dicționar“, care ne ajută să
vedem cum „traducem întocmai“ elementele unei structuri în elementele alteia. Printre altele,
și elementele neutre trebuie să corespundă.

De aceea, pentru a verifica dacă o funcție este sau nu izomorfism (și chiar numai morfism),
este necesar (nu suficient!) să verificăm că ea face elementele neutre să corespundă.
O astfel de condiție -- necesară, dar nu suficientă -- poate fi foarte utilă în cazul negativ.
Dacă elementele neutre ale două structuri *nu* corespund printr-o funcție dată, atunci funcția
respectivă nu poate fi morfism, deci nici izomorfism.

Iată două exemple:

**Exemplu:** În cazul grupurilor $ A $ și $ B $ din exemplul anterior, elementul neutru
pentru $ A $ este numărul $ 0 $, iar pentru $ B $, este matricea unitate, $ I_2 $,
care poate fi scrisă sub forma $ I_2 = M(0) $, deoarece se obține pentru $ a = 0 $.

Acum, funcția $ f(a) = M(a) $ realizează evident corespondența $ f(0) = M(0) = I_2 $,
adică face elementele neutre să corespundă. De aceea, funcția *are șanse* să fie
(izo)morfism -- fără a avea garanția că este, într-adevăr, dar a trecut un test preliminar,
ca să spunem așa.

```{note}
În unele cărți, se cere explicit ca morfismele să respecte elementele neutre.
Cu alte cuvinte, se adaugă încă din definiție axioma $ f(e_A) = e_B $.

În alte materiale, morfismele care respectă această proprietate se numesc *morfisme unitare*
și sînt permise inclusiv cazurile cînd proprietatea nu are loc.

În acest material, nu vom face astfel de distincții și vom presupune automat că orice
morfism este unitar (cum, de altfel, poate fi și dedus din definiție dacă luăm $ y = x^{-1} $
în {prf:ref}`def-morfism`.
```

**Exemplu:** Grupul multiplicativ al numerelor reale nu poate fi izomorf cu grupul aditiv
al numerelor reale. Aceasta pentru că, dacă am avea $ f : \mathbb{R} \to \mathbb{R} $
cu această proprietate, ar trebui să avem $ f(1) = 0 $. Dar $ 1 $ mai are o proprietate
importantă, anume că $ -1 \cdot (-1) = 1 $ și, aplicînd proprietatea de morfism, obținem:
```{math}
f(-1 \cdot (-1)) = f(1) = 0 = f(-1) + f(-1).
```
Dacă presupunem că $ f(-1) = t \in \mathbb{R} $, ajungem la ecuația $ t + t = 0 \Rightarrow t = 0 $,
deci și $ f(-1) = 0 $, ceea ce nu se poate (în cazul unei funcții bijective, nu se pot repeta
valorile; cum $ f(1) = 0 $, nu mai poate exista alt număr care să aibă imaginea $ 0 $).

```{note}
De fapt, în exemplul al doilea de mai sus, am folosit implicit o altă proprietate, aceea
a *ordinului* unui element. Prin definiție, spunem că un element dintr-un grup are ordinul $ n $
dacă atunci cînd aplicăm operația între elementul respectiv și el însuși de $ n $ ori
se obține elementul neutru. De pildă, $ -1 $ are ordinul 2 față de înmulțire, deoarece
$ -1 \cdot (-1) = 1 $, care este elementul neutru.

Or pentru adunare, nu poate exista niciun element de ordin 2, întrucît dacă $ t $ ar fi
un astfel de element, am avea $ t + t = 0 $, de unde nu putem obține decît $ t = 0 $.

Ideea de bază este aceasta: cînd două grupuri (sau structuri, în general) sînt izomorfe,
toate proprietățile lor algebrice „importante“ (termen vag, dar pe care nu ne folosește să-l detaliem acum)
se preiau de la o structură la alta. În particular, elementele neutre corespund, iar
un element de ordin $ n $ corespunde la un element de același ordin.
```

---

## Exerciții propuse
1. Arătați că $ f : \mathbb{R} \to \mathbb{R}, f(x) = ax $ este un automorfism
al grupului aditiv $ (\mathbb{R}, +) $, pentru orice $ a \in \mathbb{R} $, fixat.
2. Fie mulțimea:
```{math}
M = \left\{ A(x) = \begin{pmatrix} x & x \\ 0 & x \end{pmatrix} \mid x \in \mathbb{R} \right\}
```
  + Arătați că $ (M, +) $ este grup comutativ;
  + Arătați că $ f : M \to \mathbb{R}, f(A(x)) = x, \forall x \in \mathbb{R} $ este un izomorfism de grupuri aditive.
3. Arătați că grupul multiplicativ al numerelor complexe $ (\mathbb{C}, \cdot) $ nu poate
fi izomorf cu grupul multiplicativ al numerelor reale $ (\mathbb{R}, \cdot) $.

## Nucleu și imagine
Această secțiune este ceva mai tehnică, însă relevantă din cel puțin două motive:
- ne arată cum să obținem noi structuri, date unele anume;
- se va prelua aproape mot-à-mot în cazul spațiilor vectoriale.

*Nucleul* unui morfism $ f $, denumit în engleză *kernel*, motiv pentru care se notează
cu $ \mathrm{Ker}(f) $ extrage o informație importantă, însă pentru care avem nevoie
de cîteva preliminarii. Mai întîi, definiția.

```{prf:definition}
:label: def-ker
Fie $ f : A \to B $ un morfism (de grupuri, monoizi).

*Nucleul* lui $ f $ se definește prin:

$$ \mathrm{Ker}(f) = \{ x \in A \mid f(x) = e_B \} $$.
```

Cu alte cuvinte, nucleul arată ce elemente corespund elementului neutru.
Desigur, în condițiile și cu notațiile de mai sus, avem oricum $ f(e_A) = e_B $,
deci $ e_A \in \mathrm{Ker}(f) $ în toate cazurile. Important este să vedem
dacă mai găsim și alte elemente în nucleu.

Un rezultat ne arată relevanța nucleului:

```{prf:theorem}
:label: thm-ker

Dacă $ f : A \to B $ este un morfism (de grupuri, monoizi),
atunci are loc:

$$ \mathrm{Ker}(f) = \{ e_A \} \Leftrightarrow f \text{ injectivă}. $$
```

Cu alte cuvinte, numai atunci cînd morfismul este injectiv găsim doar elementul
neutru în nucleu. Reciproc, dacă măcar un element diferit de elementul neutru se
găsește în nucleu, știm sigur că morfismul nu este injectiv. Acest lucru poate
fi ușor justificat din chiar definiția nucleului: orice element de acolo
are proprietatea că merge în elementul neutru. Deci dacă $ e_A $ și $ x \neq e_A $
se găsesc în nucleu, atunci $ f(e_A) = f(x) = e_B $, lucru care nu se poate întîmpla
pentru o funcție injectivă.

Și reciproca se demonstrează ușor: Presupunem că $ \mathrm{Ker}(f) = \{ e_A \} $
și mai presupunem, pentru un raționament prin reducere la absurd, că $ f(x) = f(y) $,
cu $ x \neq y $. Dar, din proprietatea definitorie a morfismului, avem succesiv
(vom presupune o notație multiplicativă):

```{math}
f(x) = f(y) \Leftrightarrow f(x) \cdot f(y)^{-1} = e_B \Leftrightarrow f(x) \cdot f(y^{-1}) = e_B %
\Leftrightarrow f(xy^{-1}) = e_B \Leftrightarrow xy^{-1} \in \mathrm{Ker}(f) = \{ e_A \}.
```

Așadar, $ xy^{-1} = e_A \Leftrightarrow x = y $, care contrazice ipoteza de lucru.

Vedem, deci, care este informația esențială pe care o extrage nucleul: ne arată cît de departe
este un morfism de a fi injectiv.

Proprietatea pe care o așteptam și care ne arată cum construim noi substructuri este următoarea:

```{prf:theorem}
:label: thm-ker-subgrup

Dacă $ f : A \to B $ este un morfism (de grupuri, monoizi), atunci $ \mathrm{Ker}(f) \leq A $.
```

Demonstrația este un exercițiu foarte util, motiv pentru care schițăm doar cîteva indicații:
- încercați să înțelegeți mai întîi cum funcționează structura de grup din $ \mathrm{Ker}(f) $:
ea preia operația din $ A $ (o putem presupun multiplicativă), precum și elementul neutru;
- apoi folosiți teorema {prf:ref}`thm-subgrup`: luăm două elemente $ x, y \in \mathrm{Ker}(f) $
și demonstrăm că $ xy^{-1} \in \mathrm{Ker}(f) $. Nu aveți decît să folosiți definiția: un element
se găsește în $ \mathrm{Ker}(f) $ atunci cînd imaginea sa prin $ f $ este elementul neutru.

---

De cealaltă parte, imaginea este un concept ceva mai cunoscut, mai ales că are
exact același sens pe care îl are și în cazul funcțiilor obișnuite, nu neapărat
morfisme.

Prin definiție, avem:

```{prf:definition}
:label: def-img

Pentru o funcție $ f : A \to B $, se numește *imaginea* lui $ f $, notată $ \mathrm{Im}(f) $
sau $ f(A) $, mulțimea valorilor funcției. Formal:

$$ \mathrm{Im}(f) = \{ y \in B \mid \exists x \in A, f(x) = y \}. $$
```

Cu alte cuvinte, dacă o valoare din codomeniu este luată efectiv, ea se găsește în imagine.

De exemplu, pentru funcția $ f : \mathbb{N} \to \mathbb{N}, f(x) = 2x $,
avem că imaginea este alcătuită doar din numere pare, pentru că funcția produce doar astfel
de rezultate. Un număr impar precum $ 5 $ nu se poate găsi în imagine, deoarece nu există
niciun număr natural care să-i corespundă prin $ f $ (i.e. $ f(x) = 2x = 5 $ nu are soluții naturale).

În cazul morfismelor, definiția este identică.

Relevanța imaginii este pentru proprietatea de surjectivitate a unei funcții:

```{prf:definition}
:label: def-surj

O funcție $ f : A \to B $ se numește *surjectivă* dacă $ \mathrm{Im}(f) = B $,
adică $ \forall y \in B, \exists x \in A, f(x) = y $.
```

De exemplu, funcția de mai sus nu este surjectivă, deoarece avem o infinitate de numere naturale
(cele impare) care nu se găsesc în imagine.

Similar, funcția $ f : \mathbb{R} \to \mathbb{R}, f(x) = x^2 $ nu este surjectivă,
deoarece nu poate lua valori numere negative.

Pentru structuri algebrice, avem:

```{prf:theorem}
:label: thm-img

Fie $ A, B $ două grupuri (monoizi) și $ f : A \to B $ un morfism.
Atunci $ \mathrm{Im}(f) \leq B $.
```

Demonstrația procedează folosind numai definiția (vom presupune din nou o notație multiplicativă):
- înțelegeți mai întîi structura de grup (monoid) de pe $ \mathrm{Im}(f) $, care
moștenește operația și elementul neutru din $ B $;
- folosind teorema {prf:ref}`thm-subgrup`, arătați că pentru orice două elemente
$ y, z \in \mathrm{Im}(f) $, are loc $ yz^{-1} \in \mathrm{Im}(f) $. Nu uitați că
apartenența la imagine se traduce prin faptul că există un element din domeniu care corespunde
elementului respectiv din imagine: $ y \in \mathrm{Im}(f) \Leftrightarrow \exists x \in A, f(x) = y $.

```{note}
Punînd acum cap la cap informațiile din {prf:ref}`thm-ker` și {prf:ref}`thm-img`, obținem încă o metodă
de a demonstra că un morfism $ f : A \to B $ este chiar izomorfism: trebuie să avem simultan că
$ \mathrm{Ker}(f) = \{ e_A \} $ și $ \mathrm{Im}(f) = B $.
```

---

În cazul grupurilor (și chiar al [inelelor și corpurilor](./p2-s2-inele-corpuri.md)), nu e foarte
clară aplicația pe care o au nucleul și imaginea, cu excepția exemplelor abstracte oferite.
Însă în cazul spațiilor vectoriale, exemplele vor fi mult mai ușor de vizualizat, astfel că ne oprim
aici cu detaliile teoretice și vom reveni asupra acestor noțiuni în capitolele despre spații vectoriale
și geometrie.
