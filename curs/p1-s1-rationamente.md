# Abstractizare și raționamente

În toate ramurile matematicii, dezvoltarea teoriilor și a rezultatelor urmează anumite
ale raționamentelor. Acestea sînt validate de fundamente ale logicii care stau la
baza întregului nostru sistem de gîndire -- fie că este vorba despre o teoremă matematică
ori un argument dintr-un discurs din viața de zi cu zi. De aceea, este important să le 
înțelegem modul de funcționare, lucru care, în același timp, ne ajută și să depistăm
eventuale fisuri sau inconsecvențe într-un argument sau raționament dat.

Scopul acestei lecții nu este, însă, unul care privește în primul rînd gîndirea
critică și analiza logică a raționamentelor. Principalul motiv pentru care facem
această expunere se leagă, pe de o parte, de aplicații ulterioare, în special în ce
privește raționamentele *inductive*, dar în același timp, și pentru a pune în context
procedura de *abstractizare* care stă la baza algebrei liniare și nu numai.
Modul în care pornim, de pildă, de la mulțimea numerelor întregi, împreună cu operațiile
acesteia și construim *inele* sau *grupuri* ori *monoizi*, este unul care ține de
*abstractizare*, de *generalizare*.

Dar să mergem direct la subiect. Mai adăugăm doar că majoritatea exemplelor pe care le
vom da vor fi triviale, foarte ușor de verificat și de înțeles. Este o decizie conștientă
care ne va permite să ne concentrăm pe noutățile privitoare la raționamente și 
abstractizare în loc să explicăm detaliat exemple sofisticate.

## Despre raționamente, în general
Într-un context științific, de obicei, afirmațiile necesită demonstrații. Dacă este
vorba de situații particulare, demonstrațiile se pot da și explicit, prin enumerarea
și verificarea pe rînd a tuturor instanțelor. De exemplu, dacă avem o propoziție
precum:

> Toate elementele mulțimii $ A = \{ 0, 1, 4, 9, 16 \} $ sînt pătrate perfecte.

atunci putem să verificăm explicit, fiecare element în parte. Dar foarte rare sînt
situațiile din matematică în care lucrăm cu particularul. Majoritatea rezultatelor
sînt *universale*, adică au valoare de *generalitate* -- se doresc a fi adevărate
pentru *orice* mulțime, element, număr, obiect ș.a.m.d. 

### Cuantificatori
Ajunși aici, este bine să începem chiar cu modul de exprimare a propozițiilor
matematice cu ajutorul *cuantificatorilor*. În general, veți întîlni afirmații
generale de tipul:

> *Oricare ar fi* un număr $ x $ cu proprietatea $ P $, are loc rezultatul $ Q $.

care poate fi scrisă simbolic[^logicaprop] sub forma $ \forall x : P(x), Q $.

[^logicaprop]: Astfel de reprezentări simbolice fac obiectul logicii matematice
și mai precis, a logicii propoziționale. Nu intrăm în detalii privitoare la acest
lucru aici, însă în afară de simbolurile obișnuite pe care le întîlnim adesea
în propozițiile matematice ($ \forall, \exists, \to $ etc.), am folosit aici și o
proprietate a unui obiect. Acest lucru se notează, de obicei, funcțional: $ P(x) $
desemnează o proprietate $ P $, care se aplică unui obiect $ x $.

Afirmația sus-menționată se numește *universală* și folosește *cuantificatorul*
$ \forall $. Aceasta înseamnă că ea exprimă o proprietate care are loc pentru toate
obiectele $ x $ (în condițiile precise din afirmație), iar cuantificatorul este un
operator logic pe care îl folosim tocmai atunci cînd vrem să arătăm gradul de
generalitate. Cuantificatorul universal $ \forall $ exprimă, așa cum îi spune numele,
o afirmație... universală. Este similar propozițiilor pe care le întîlnim în logica
din clasa a noua, „*Toți* $ S $ sînt $ P $.“

Evident, o afirmație generală nu poate fi demonstrată *explicit*, adică enumerînd
instanțele pentru care ar trebui să fie adevărată. De aceea, avem nevoie de metode
generale de demonstrație, care să funcționeze *oricare ar fi* obiectul pe care îl
analizăm.

Un al doilea cuantificator pe care îl întîlnim se numește *existențial* și apare
în propoziții precum:

> *Există* un obiect $ x $ care are proprietate $ P $ astfel încît are loc rezultatul $ Q $.

care poate fi scrisă simbolic sub forma $ \exists x : P(x), Q $.
Afirmațiile existențiale au și variația de *existență unică*, adică:

> *Există și este unic* (*există un singur*) obiect $ x $ care are proprietatea $ P $...

care se scrie simbolic sub forma $ \exists! x : P(x),... $.

Ar trebui să fie clară distincția între cuantificatorul universal $ \forall $ și cel
existențial $ \exists $, în primul rînd pe baza propozițiilor și contextelor în care
apar. Exemple concrete sînt:

- Orice număr natural par este divizibil cu $ 2 $. 
Simbolic, 
```{math}
\forall x \in \mathbb{N}, x = 2k, k \in \mathbb{N}, x \ \vdots \ 2.
```
- Există un număr natural impar care este mai mare decît 1000. 
Simbolic, 
```{math}
\exists x \in \mathbb{N}: x = 2k + 1, k \in \mathbb{N}, x > 1000.
```
- Există un unic număr natural par care este mai mare decît 11 și mai mic decît 13. 
Simbolic, 
```{math}
\exists! \ x \in \mathbb{N}: x = 2k, k \in \mathbb{N}, (x > 11 \land x < 13).
```

Evident, modul de exprimare a propozițiilor respective -- atît în forma simbolică,
cît și cea în limbaj natural -- nu este unic. De exemplu, paritatea poate fi definită
chiar prin divizibilitatea cu 2. Sau dacă luăm o propoziție precum:

> Există un unic număr prim între 10 și 12.

ar trebui să o exprimăm cu ajutorul unei proprietăți care nu are un simbol anume.
Faptul că un număr este prim se poate scrie ad-hoc prin $ x \in \mathbb{N}, \mathrm{Prim}(x) $,
dar nu este o notație standard. Adică ar trebui să explicăm (să definim, de fapt) ce înseamnă
proprietatea $ \mathrm{Prim}(x) $. Am scrie, de exemplu:

```{math}
\mathrm{Prim}(x) \Leftrightarrow \forall d \in \mathbb{N} : d \mid x \Rightarrow d \in \{ 1, x \}.
```

Dacă în cazul propozițiilor universale, este evident că nu putem avea o demonstrație
prin instanțiere, adică prin enumerarea obiectelor și verificarea lor unul cîte unul,
pentru propozițiile existențiale, lucrurile sînt ceva mai complicate. De fapt, tocmai
această discuție privitoare la demonstrațiile prin instanțiere și cele generale,
abstracte, a condus la probleme filosofice fascinante, pe care le vom detalia pe
parcurs. Deocamdată, este clar că în cazul exemplelor de mai sus este ușor să demonstrăm
prin instanțiere. 
- Un număr natural impar mai mare decît 1000 este 1001. Nu trebuie decît să găsim
cel puțin unul.
- Numărul natural par mai mare decît 11 și mai mic decît 13 este 12,
care este unic tocmai prin definiția relației de ordine dintre numere naturale.
- Numărul prim dintre 10 și 12 este 11, a cărui unicitate rezultă, din nou, din modul
de funcționare a relației de ordine dintre numere naturale.

Însă cu totul altfel stau lucrurile dacă am avea o propoziție existențială mai greu
de instanțiat (sau chiar imposibil, în unele cazuri). Să luăm, de exemplu:

> Există un număr par mai mare decît 2 care nu poate fi scris ca suma a două numere prime.

În primul rînd, o astfel de afirmație este imposibil de demonstrat prin verificare.
Mulțimea numerelor naturale este infinită (la fel și mulțimea numerelor pare).
Afirmația sus-menționată este cunoscută sub numele de [Conjectura lui Goldbach](https://en.wikipedia.org/wiki/Goldbach%27s_conjecture).
De fapt, este negația acesteia și este nedemonstrată încă, din secolul al XVIII-lea.
În zilele noastre, putem folosi supercomputere care să încerce să găsească 
un contraexemplu al conjecturii -- ceea ce ar face ca varianta negată pe care am formulat-o
mai sus să fie adevărată. Aceasta ar fi o demonstrație prin instanțiere. Dar dacă
afirmația este falsă? Nu am ști niciodată, pentru că mereu am putea căuta instanțe,
dar ar lipsi o demonstrație generală. Nu mai vorbim de cazurile cînd propozițiile sînt
și mai abstracte, adică nu folosesc numere. De exemplu, o afirmație precum:

> Există un cerc în care nu se pot înscrie 4 triunghiuri obtuzunghice.

nu ar putea fi demonstrată (sau contrazisă) direct, pentru că nu avem cum să căutăm
prin „mulțimea tuturor cercurilor“. În schimb, propoziția va trebui să fie reformulată
într-o variantă care să se preteze căutărilor. De pildă, putem să o transformăm într-una
numerică făcînd apel la aria triunghiului, respectiv aria cercului și să ajungem
să demonstrăm o *afirmație echivalentă*, dar scrisă numeric.

Evident, exemplele pe care le-am dat sînt doar cazuri foarte simple. În matematica de
nivel înalt, afirmațiile de demonstrat, chiar și cele existențiale, sînt cu mult mai
greu de exprimat și de verificat.

Iar aici ajungem la problema filosofică pe care am menționat-o. În prima parte a 
secolului XX, matematicianul german David Hilbert a demonstrat o afirmație existențială
din geometria algebrică (a cărei dificultate ne împiedică să o formulăm aici,
dar puteți citi, de exemplu, [pagina de Wikipedia](https://en.wikipedia.org/wiki/Hilbert%27s_basis_theorem)).
Unul dintre colaboratorii lui Hilbert, germanul Paul Gordan, ar fi afirmat, la vederea
demonstrației că *Aceasta nu este matematică, este teologie!*. Gordan se referea
la faptul că un argument esențial din demonstrația lui Hilbert era pentru o afirmație
existențială, însă care nu instanția obiectul în cauză. Astfel că Gordan a simțit că
„trebuie să creadă“ că $ x $ există, cu proprietatea cerută, fără a-l vedea instanțiat,
situație pe care a asemănat-o cu teologia.

O astfel de situație a fost generalizată apoi în inițiativele de filosofie a științei
numite *constructivism* și *intuiționism*, pe care le vom detalia ulterior. În esență,
susținătorii acestor curente considerau că este inadmisibil să avem o demonstrație
pentru o afirmație existențială care să nu conțină o instanțiere *chiar și în principiu*.
Această observație din urmă se referă la faptul că, deși uneori poate fi imposibil de
instanțiat sau de construit *efectiv* un exemplu care să satisfacă propoziția,
trebuie să existe o metodă care să-l poată construi, de exemplu, folosind **inducția**
**matematică**. Adică să fie clar că există măcar o metodă de construcție, chiar dacă
această metodă nu poate fi implementată efectiv, de exemplu din cauza faptului că lucrează
cu mulțimi infinite. În cazul unei demonstrații asistate de computer, de exemplu, 
putem spune că avem o metodă efectivă de construcție, întrucît programul care a găsit 
(contra)exemplul se bazează pe un algoritm care are un număr finit de pași.

Vom reveni asupra acestei discuții în secțiuni ulterioare.

### Deducția, inducția, abducția
Raționamentele, mecanismele prin care putem construi argumente, sînt, în general,
de 3 feluri, clasificate după relația pe care o stabilesc între *particular* și *general*:
- raționamente deductive (**deducții**)
- raționamente inductive (**inducții**);
- raționamente abductive (**abducții**).

Dintre acestea, cel mai des utilizată în metoda științifică este *deducția*.
Prin *metodă științifică* se înțelege procedura, care adesea combină teoria
cu practica, prin care se produce un avans științific de un anume fel.
Poate fi vorba despre procedura de descoperire și demonstrație a unei teoreme
de matematică, de alcătuire și descriere a unui compus chimic, de pregătire
și implementare a unui experiment de fizică ș.a.m.d.

Deducția este metoda prin care se face trecerea *de la general către particular*.
Altfel spus, cunoscută fiind o situație generală, descrisă de o teoremă, postulat
sau un altfel de rezultat științific, *putem deduce* că rezultatul respectiv
se va aplica și unei situații particulare în care ne aflăm.

Un exemplu simplu: Este cunoscut faptul că orice număr par se împarte exact la 2.
*Deducem* de aici că și numărul 100004, care este par, se împarte exact la 2.
Rezultatul particular pe care l-am obținut se bazează pe o simplă particularizare
a rezultatului general.

Evident, situația în care majoritatea raționamentelor sînt de tip deductiv
este una ideală, pentru că ar însemna că avem deja toate informațiile necesare
pe cazul general și nu ne rămîne decît să le particularizăm. Dacă știm totul despre
o anumită mulțime de numere sau de obiecte matematice, atunci nu avansăm nicăieri
din punctul de vedere al cunoașterii dacă numai deducem că numere sau obiecte 
particulare din acea mulțime au proprietățile pe care le știam deja.

Totuși, deducția este foarte utilă și apare în demonstrațiile matematice în situații
mai sofisticate. De exemplu, poate să nu fie evident că un obiect cu care lucrăm
este parte a unei mulțimi despre care știm deja că are anume proprietăți. Astfel că
avem de îndeplinit sarcina mai complicată de a demonstra mai întîi că obiectul
respectiv aparține mulțimii și în fine, deducția ne ajută să tragem concluzia finală.

Simplificînd masiv, putem da următorul exemplu: Presupunem cunoscută afirmația generală:

> Orice număr prim mai mare decît 2 este impar.

Pornim acum cu numărul 124111. Dacă demonstrăm că este prim, vom putea *deduce*, folosind
afirmația de mai sus, că este impar. Evident că în acest exemplu este mult mai greu să
demonstrăm că numărul dat este prim decît că este impar. Dar esențialmente, este un caz
în care putem aplica deducția în concluzia finală.

În esență, schema după care funcționează un raționament deductiv se poate formula astfel:
- Dacă știm că o proprietate $ P $ este adevărată pentru orice obiecte de tipul $ T $ și
- Dacă știm că obiectul $ x $ are proprietatea $ T $,
- Atunci rezultă că obiectul $ x $ are proprietatea $ P $.

Evidențiem în această schemă simplificată faptul că proprietatea $ P $ cunoscută
din ipoteză este una *generală*, iar demonstrația pe care o facem este pentru un
*obiect particular*.

---

Un al doilea tip de raționament este acela *inductiv*, care face trecerea 
*de la particular la general*. Este genul de raționament care se folosește foarte des
atunci cînd se începe construcția unei teorii sau chiar în cazul abstractizării
din algebră, așa cum vom vedea.

Schema simplificată a unui raționament inductiv este aceasta:
- Dacă știm că o proprietate $ P $ este adevărată pentru o mulțime finită de obiecte $ M $ și
- Dacă avem o metodă clară și demonstrată care ne permite să adăugăm noi obiecte mulțimii $ M $,
- Atunci proprietatea $ P $ este adevărată pentru toate obiectele din $ M $.

În general, demonstrațiile inductive au 2 pași bine stabiliți, conform schemei de mai sus:

1. *Pasul de verificare*, în care se arată că proprietatea dorită este adevărată pentru cîteva elemente particulare;
2. *Pasul de inducție*, în care se presupune că proprietatea este adevărată pentru oricîte elemente și se demonstrează că ea rămîne adevărată și cînd adăugăm noi obiecte, conform metodei.

De exemplu, dacă am vrea să demonstrăm prin inducție că orice număr par este divizibil cu 2, 
am putea proceda astfel:

1. Pasul de verificare: luăm, în particular, numerele 2, 4, 6. Observăm că ele sînt divizibile cu 2, adică se împart fără rest.
2. Pasul de inducție: presupunem că avem un număr arbitrar de numere pare și că toate sînt divizibile cu 2. Care este metoda de a mai adăuga încă un număr mulțimii? Adunarea cu 2. Altfel spus, trebuie să demonstrăm că dacă $ n $ aparține mulțimii (deci este divizibil cu 2), atunci și $ n + 2 $ aparține mulțimii. Deci $ n = 2k $, pentru un anumit număr natural $ k $. Atunci $ n + 2 = 2k + 2 = 2(k + 1) $, care este evident divizibil cu 2 și am terminat.

Concluzia este că putem adăuga oricîte numere mulțimii, folosind regula de adunare cu 2
și toate vor avea proprietatea căutată, deci am demonstrat afirmația *în general*.

Metoda inducției matematice se bazează pe un principiu care stă la baza construcției
mulțimii numerelor naturale. De fapt, este una dintre metodele de a *defini* mulțimea
$ \mathbb{N} $, a numerelor naturale. În general, avem următoarea:

```{prf:definition}
:label: def-inductiv

O mulțime $ A $ se numește *inductivă* dacă are proprietățile:
- conține 2 elemente fixate;
- se poate defini o funcție *succesor*, $ S : A \to A $, astfel încît 
să aibă loc $ \forall x \in A, S(x) \in A $.
```

Se poate demonstra că mulțimea numerelor naturale este inductivă, fiind
descrisă prin așa-numitul *triplet Peano*, denumit după matematicianul italian
Giuseppe Peano (1858-1932), care conține:
- două elemente fixate, numerele $ 0 $ și $ 1 $;
- funcția succesor, $ S(x) = x + 1 $, cu proprietatea din definiție.

Se *definesc*, apoi numerele $ 2 = S(1), 3 = S(2) = S(S(1)) $ ș.a.m.d.

```{note}
Aici, de fapt, lucrurile sînt mai delicate, în general. Putem adresa întrebări precum:
- Dar ce sînt 0 și 1 și de unde știm că ele există pentru a le lua ca puncte de pornire?
- De unde știm că funcția succesor are proprietatea din definiție, adică faptul că orice
succesor al unui număr natural este tot număr natural?
- Ce sînt, de fapt, *numerele*?

și multe altele, la care filosofia matematicii a răspuns în felurite moduri încă
din secolul al XIX-lea. Evident, aici am prezentat o variantă ultrasimplificată a discuției,
dar încurajăm astfel de întrebări și căutări pentru răspunsurile lor.
```

La prima vedere, poate părea că metoda inducției matematice nu este una suficient de 
riguroasă sau nu poate constitui baza unor demonstrații formale. Însă acest lucru
nu este adevărat și există un *principiu al inducției matematice* care arată exact
faptul că o demonstrație prin inducție este validă. Intuitiv, esența rezidă în
regula care ne permite să adăugăm încă un element la mulțime; acolo se regăsește
mare parte din esența unor astfel de demonstrații. Dar și pasul de verificare este
unul fundamental. Este celebră în acest sens următoarea „demonstrație“ pentru
„teorema“:

> Toți caii sînt albi.

„Demonstrația“ prin inducție funcționează cam așa:

1. Pasul de verificare: Alegem un cal alb.
2. Pasul de inducție: Presupunem că avem deja o mulțime de cai despre care știm că
sînt albi (ipoteza de inducție) și demonstrăm că, adăugînd încă unul la mulțime,
cu toții vor fi albi. Modul în care se adaugă încă un cal este... standard, nu avem
o metodă anume. Să presupunem, deci, că avem o mulțime de $ n $ cai care sînt albi
și separat, pe al $ n + 1 $-lea, pe care am vrea să-l adăugăm. Procedăm astfel:
scoatem unul dintre cei $ n $ cai albi din mulțime și rămîn $ n - 1 $, apoi îl adăugăm
pe cel pe care îl avem în plus. Împreună cu el, vom avea din nou o mulțime de $ n $ cai,
despre care știm deja că sînt albi. Acum cel pe care îl avem separat este deja alb
(făcea parte din vechea mulțime), deci avem $ n + 1 $ cai care sînt albi și am
terminat demonstrația.

Surprinzător sau nu, greșeala în acest raționament *nu* este la pasul de inducție,
ci la pasul de verificare. Faptul că există cel puțin un cal alb ne permite să
alegem *unul*. Dar conform principiului inducției matematice, ar trebui să putem
alege și *oricare 2* sau *oricare 3*, ceea ce, evident, nu putem. Cînd demonstrăm
că toate numerele pare sînt divizibile cu 2, de exemplu, am ales să începem cu
2, 4 și 6. Dar afirmația rămîne adevărată și dacă am fi început cu oricare număr
par, oricare două numere pare, oricare 3 numere pare etc.

Încă o observație foarte importantă privitoare la metoda inducției matematice
este că ea se poate aplica doar pentru proprietăți care pot conține *enumerări*.
Exemplele pe care le-am dat se bazau pe numere naturale. Nu este obligatoriu
ca obiectele despre care demonstrăm să fie chiar numere naturale, dar trebuie
ca proprietățile demonstrate să poată fi enumerate cu numere naturale.
De exemplu, în „demonstrația“ despre cai: animalele nu sînt numere naturale,
dar am lucrat cu numărul lor, de fapt.

---

În fine, modul de funcționare al inducției matematice este unul foarte des
întîlnit în rezultatele matematice și nu numai. Situația în sine este aceasta,
dacă este să simplificăm:
- pornim cu o afirmație care ar putea fi adevărată, de exemplu, după ce am observat
un fel de tipar pentru un calcul anume;
- formulăm afirmația în general și folosim calculele particulare anterioare
pentru pasul de verificare;
- demonstrăm pasul de inducție.

Iată un exemplu tipic. Cunoașteți, cu siguranță, așa-numita *sumă a lui Gauss*,
adică suma primelor $ n $ numere naturale:

```{math}
S_n = 1 + 2 + 3 + 4 + \dots + n
```

Presupunem că nu ne amintim rezultatul și vrem să descoperim valoarea
acestei sume. Calculăm cîteva exemple:

- $ n = 1 \Rightarrow S_1 = 1 $;
- $ n = 2 \Rightarrow S_2 = 1 + 2 = 3 $;
- $ n = 3 \Rightarrow S_3 = 1 + 2 + 3 = 6 $;
- $ n = 4 \Rightarrow S_4 = 1 + 2 + 3 + 4 = 10 $;
- $ n = 5 \Rightarrow S_5 = 1 + 2 + 3 + 4 + 5 = 15 $.

De fiecare dată, este recomandabil să facem legătura între indicele pasului
la care ne aflăm ($n$) și valoarea obținută. Astfel că avem perechi
de forma $ (1, 1), (2, 3), (3, 6), (4, 10), (5, 15) $.

Neavînd o formulă dată, trebuie să o găsim noi. Primele 3 cazuri nu ne dau
suficiente indicii, sînt prea multe moduri în care putem obține $ (1, 1) $,
apoi $ (2, 3) $, apoi $ (3, 6) $. Dar de la $ 4 $ la $ 10 $ putem ajunge,
de exemplu, dublînd succesorul lui $ 4 $. Dacă încercăm aceeași idee pentru
$ n = 5 $, ar trebui să obținem $ 6 \cdot 2 = 12 $, iar nu $ 15 $.
Dar poate dublarea nu este operația generală, ci s-a aplicat doar în cazul
respectiv, unde eram la pasul 4. Deci poate, în general, succesorul pasului
nu se înmulțește cu 2 mereu, ci cu jumătatea pasului la care ne aflăm,
adică vom încerca formula $ S_n = \dfrac{n}{2} \cdot (n + 1) $. Dacă testăm
pentru $ n \in \{ 1, 2, 3, 4, 5 \} $, găsim că formula este adevărată.
Deci are șanse să funcționeze *în general*, iar calculele de mai sus sînt deja
pasul de verificare.

Pentru pasul de inducție, presupunem că avem deja $ S_n = \dfrac{n}{2} \cdot (n + 1) $
și vrem să vedem cum mai adăugăm încă un număr la sumă. Cu alte cuvinte,
vrem să calculăm $ S_{n + 1} $, cu o formulă similară.

Dar putem vedea că $ S_{n + 1} = S_n + (n + 1) $ și, deoarece știm deja formula
pentru $ S_n $, o putem folosi:

```{math}
S_{n + 1} = S_n + (n + 1) = \dfrac{n}{2} \cdot (n + 1) + (n + 1) = %
(n + 1) \left( \dfrac{n}{2} + 1 \right) = (n + 1) \cdot \dfrac{n + 2}{2},
```
care este exact rezultatul căutat, așadar $ S_{n + 1} = \dfrac{n + 1}{2} \cdot (n + 2) $,
deci formula pe care am „ghicit-o“ funcționează *în general*.

Un raționament de tipul acesta este des întîlnit în metoda științifică,
pentru că formulele generale nu se dau, de obicei. Astfel că trebuie să încercăm
diverse posibilități pînă o găsim pe cea corectă, a cărei corectitudine, apoi,
o demonstrăm.

---

Al treilea tip de raționament, cu mult diferit de celelalte, se numește *abducție*.
Unul dintre motivele pentru care acesta este diferit de deducție și de inducție
este că în matematică, nu se folosește niciodată. Aceasta deoarece abducția
sau *raționamentul abductiv* oferă cele mai probabile concluzii, nu neapărat pe
cele sigure. Însăși etimologia cuvîntului provine din latină, unde *ab* și *duco*
înseamnă *ceva care duce alături*, care distrage, am putea spune.

Din punctul de vedere al relației între particular și general, am putea spune că
abducția face legătura între particular și particular. Aceasta deoarece ea caută
o cauză pentru un anume eveniment particular. În funcție de evenimentul observat,
cauzele pot fi particulare sau generale, cum rezultă din exemplele de mai jos.

Iată un exemplu. Să presupunem că într-o dimineață, priviți pe fereastră și vedeți
strada udă. Prin abducție, ați putea spune că azi-noapte trebuie să fi plouat.
Dar aceasta nu este singura explicație și nici nu putem accepta afirmația ca fiind
adevărată. Pot exista mai multe cauze, cum ar fi roua dimineții sau mașina de
salubritate să fi udat strada. A fi plouat este o condiție *suficientă* ca strada să
fie udă, dar *nu este necesară*. Mai mult, în cazul de față se poate argumenta că
nici măcar nu este cea mai probabilă.

Situația aceasta este una în care s-a făcut legătura între un eveniment particular
(ploaia) și un altul, tot particular (faptul că vedem strada udă).

Dar, de exemplu, dacă un candelabru care atîrna din tavan cade și raționăm prin
abducție că e pur și simplu vina gravitației, atunci am făcut legătura între
un eveniment particular și un altul, general. Evident că în acest caz este și mai
puțin probabil ca gravitația să fie cauza adevărată a căderii candelabrului,
dat fiind că în majoritatea cazurilor, cel puțin, candelabrele sînt susținute de
structuri destul de puternice tocmai pentru a împiedica efectele gravitației.
Dar în orice caz, a spune că gravitația este cauza poate fi un raționament abductiv
ce leagă o cauză generală de un efect particular observat.

Totuși, raționamentul abductiv este foarte des utilizat „în viața reală“. În situații
critice, precum urgențe medicale sau în cele în care o demonstrație generală ori o
analiză completă ar necesita mult prea mult timp și resurse, cum este în cazul
inteligenței artificiale, abducția poate fi o metodă acceptabilă. Faptul că ne gîndim
la *cea mai probabilă cauză pentru un anume rezultat* nu este neapărat greșit și,
în funcție de situație, poate să aibă o rată de succes destul de mare.

Se poate gîndi chiar un cadru teoretic sofisticat în care să se calculeze probabilitatea
de succes pentru o anume inferență și atunci abducția poate fi justificată matematic.
Dar cum într-o teorie avem nevoie de o cauză (ipoteză) sigură, abducția nu este o 
metodă utilizabilă.

(sec-abstractizare)=
## Abstractizare
Mai departe, nu atît un tip de raționament, ci o tehnică pe care o putem folosi
pentru a înțelege sau a modela unele lucruri.

În limbajul comun, a spune despre ceva că este *abstract* înseamnă de multe ori
că este *dificil, greu de înțeles*, cauza fiind de cele mai multe ori faptul
că se folosesc concepte imaginare, științifice, tehnice sofisticate. Însă
DEX-ul ne dă următoarea explicație:

> Care este gândit în mod separat de înfățișarea materială, de exemplele 
> particulare, de ansamblul concret (senzorial) din care face parte; care este 
> detașat de obiecte, de fenomene sau de relațiile în care există în realitate.

În matematică și nu numai, *a abstractiza* este adesea sinonim cu *a generaliza*
sau *a modela*, întrucît prin atingerea generalității sau prin modelare se ajunge
la un concept care este *separat de înfățișarea materială, de exemplele particulare*.

Evident, ca în toate cazurile din istoria ideilor, drumul s-a făcut dinspre 
particular către general. Un exemplu este chiar în ce privește raționamentele prin
inducție. Dar un alt exemplu, la care inducția nu ne ajută, însă abstractizarea,
da, este acesta. Presupunem că analizăm proprietățile adunării numerelor naturale.
Observăm că ordinea adunării nu contează, pe cazuri particulare: $ 3 + 5 = 5 + 3 $,
$ 1 + 7 = 7 + 1 $, $ 100 + 1000 = 1000 + 100 $ ș.a.m.d. Din aceste cazuri particulare,
*generalizăm*, afirmînd că $ a + b = b + a, \forall a, b \in \mathbb{N} $,
proprietate care se numește *comutativitatea* adunării. 

Atunci cînd generalizăm, o putem face către o teoremă sau un rezultat care 
trebuie demonstrat sau o axiomă ori postulat, fiind afirmații care nu se demonstrează.
Exemplul de mai sus, care privește comutativitatea, poate fi demonstrat, surprinzător
sau nu. În plus, fiind vorba despre numere naturale, poate fi chiar demonstrat
prin inducție, însă nu insistăm pe aceste detalii și ne concentrăm pe procedura
de abstractizare.

Ideea de bază este aceasta: studiem cazuri particulare, concrete, apoi ne întrebăm,
treptat, dacă nu cumva proprietățile pe care le observăm în cazul particular sînt
adevărate și pentru situații mai generale. Cu cît ajungem la un nivel de generalitate
mai mare, cu atît mai bine. De exemplu, comutativitatea despre care am comentat
mai sus ne putem întreba dacă este adevărată și pentru adunarea numerelor întregi
sau raționale sau reale sau complexe.

---

O scurtă paranteză istorică și filosofică, însă strîns legată de subiect, este
aceasta. În prima parte a secolului al XX-lea, cînd se puneau bazele teoriei
mulțimilor, părea că orice generalizare se termină la mulțimi. În momentul în care
se formula o propoziție care arăta o proprietate *pentru orice mulțime*, atunci
aceea atingea gradul maximum de generalitate, pentru că nu erau concepute obiecte
care să nu fie mulțimi. Dacă rezultatul era adevărat pentru orice mulțime, atunci
era adevărat *în general*, în sensul cel mai larg cu putință în matematică.

Însă apoi a apărut așa-numitul *paradox al lui Russell* (care, însă, fusese descoperit
sub forme echivalente și de alți matematicieni, însă Bertrand Russell l-a popularizat
cel mai mult). În cadrul acestui paradox, se întreabă dacă mulțimea care conține
toate mulțimile (și care poate fi închipuită, deci prin această proprietate este
destul de clar definită) este o mulțime. Posibilitatea ca răspunsul să fie negativ
era înspăimîntătoare, pentru că obiecte matematice care să *nu* fie mulțimi erau
foarte greu de închipuit și cu atît mai greu de formalizat, tocmai pentru că definiția
axiomatică a mulțimilor era atît de generală, încît părea că nu mai lasă loc de nimic
altceva. Dacă un obiect matematic nu este o mulțime... nu poate fi ceva suficient de
riguros definit, deci nu merită studiat din punct de vedere matematic.

Rezultatul a fost surprinzător: mulțimea tuturor mulțimilor nu putea fi o mulțime,
așa că a fost necesară tratarea cu cît mai multă rigoare a obiectelor care nu au
această proprietate (nu sînt mulțimi). Este vorba despre așa-numitele *clase proprii*.
Scopul acestei paranteze nu este să detaliem despre structura claselor proprii,
ci să reținem această trecere treptată către abstract, unde mulțimile nu au fost
frontierele finale.

Studiul a continuat, chiar, și mai mult către generalitate. Ideea de mulțime însăși
putem spune că este o încununare a eforturilor de abstractizare. În esență, o mulțime
este orice colecție de obiecte (matematice sau nu neapărat) care au ca principală
proprietate faptul că pot fi distinse între ele. Cu alte cuvinte, dacă este clar
unde „se termină“ un obiect și „începe“ un altul, adică nu există niciun risc de
confuzie între (oricare) două obiecte, atunci obiectele respective alcătuiesc o mulțime.
Este motivul pentru care, de exemplu, într-o mulțime nu contează ordinea elementelor
și nici nu se acceptă elemente repetate. Un contraexemplu simplu de mulțime este,
de pildă $ \{ 1, 2, 2, 3 \} $.

Acum începe partea ceva mai tehnică. Mulțimea tuturor mulțimilor s-a demonstrat
că nu este o mulțime. Dar ce putem spune despre... grupul tuturor grupurilor,
de exemplu? Din punctul de vedere al structurii subiacente, este destul de clar:
obiectele sînt grupuri (v. {prf:ref}`def-grup`), iar operațiile dintre ele sînt date de 
{ref}`morfisme<sec-substructuri-morfisme>` de grupuri. Similar, întrebările se pot
pune și despre inele, corpuri, spații vectoriale și alte tipuri de structuri algebrice.
Informația abstractă care ne interesează aici pornește de la tiparul grupurilor:
vrem să știm care este mulțimea de obiecte și în ce mod putem opera între aceste
obiecte.

Pentru aceste situații au apărut noi obiecte matematice numite *categorii*.
Unul dintre principalii cercetători care au lucrat la această structură nouă
a fost americanul Saunders MacLane (1909-2005). Ce legătură are aceasta cu 
abstractizarea? În afara faptului că în introducerea categoriilor s-a folosit
tehnica de abstractizare pe care am întîlnit-o pînă acum, mai circulă o anecdotă
conform căreia teoria categoriilor și chiar, în general, această inițiativă de
abstractizare era denumită de unii matematicieni *abstract nonsense*
(*fleacuri abstracte*, în traducere liberă). Ba chiar s-au scris articole ori
notițe de curs, precum [acesta](https://people.math.harvard.edu/~elkies/M55a.05/nonsense.html),
al profesorului de la Harvard Noam Elkies, care se referă la argumentele
bazate pe teoria categoriilor *abstract nonsense*.

---

Reținem, deci, că prin procedeul de abstractizare se extrag informațiile
esențiale și generale ale unui obiect. Cu cît informațiile extrase
(*abstrase*, am putea spune) se aplică unei clase mai mari de obiecte, cu atît
generalizarea este mai utilă.

### Exemplu din programare
Ideea de abstractizare nu este specifică numai matematicii. Este chiar un concept
pe care îl întîlnim în programare și în implementarea multor limbaje.
În esență, lucrurile funcționează ca în matematică: dacă avem o structură cît mai
generală, care ne oferă o perspectivă de ansamblu care depinde cît mai puțin
de cazuri particulare, atunci avem o abstracțiune.

Un exemplu concret și cel mai simplu este în cazul funcțiilor. În Python, de pildă,
putem scrie o funcție care calculează valorile unei expresii de gradul al doilea
$ f(x) = ax^2 + bx + c $, atunci cînd se dau parametrii $ a, b, c $ și argumentul
$ x $. Codul ar putea arăta cam așa:

```python
# definim funcția de gradul al doilea, cu parametri și argument real
def quadratic(a -> float, b -> float, c -> float, x -> float) -> float:
    return (a * x**2 + b * x + c)
```

Putem să nu vedem această implementare și în program, o putem apela direct:

```python
# afișăm valorile funcției f(x) = 5x^2 + 7x + 3
# pentru x = -2, -1, 0, 1, 2, 3, 4, 5
a = 5
b = 7
c = 3
for x in range(-2, 5):
    print(quadratic(a,b,c,x))
```

Folosită astfel, funcția `quadratic` este o abstracțiune. Putem să nu îi vedem
exact implementarea -- mai precis, limbajul ne permite să o ascundem, să
„facem abstracție de ea“ și să o folosim direct pentru rezultate.

Similar funcționează lucrurile și în cazul claselor, definite în limbaje care permit
programare orientată pe obiecte. Și acestea abstractizează („ascund“) implementarea
unor concepte, oferindu-ne doar o *interfață* care ne permite să interacționăm
cu conceptul care a fost abstractizat. În exemplul de mai jos, creăm o clasă
`Point`, care ne permite să stocăm cele 2 coordonate ale unui punct din plan.
Clasa are un *constructor* (`__init__`) prin care se creează un punct 
și un *destructor* (`__del__`) prin care se șterge.

```python
class Point:
    def __init__(self, xx, yy):
        self.x = xx
        self.y = yy

    def __del__(self):
        del self.x
        del self.y
```
Acum putem lucra foarte ușor direct cu „abstracția“ `Point`:

```python
myPoint = Point(2, 3)
```

Ideea generală, așadar, a abstractizării este aceasta: oricînd putem
porni de la situații particulare, strîns legate de concret, de exemple,
către formulări și structuri generale, care să depindă de cît mai puține
obiecte sau condiții, spunem că *generalizăm* sau *abstractizăm*. Tehnica
se poate aplica în matematică, în cazul unor proprietăți sau rezultate sau
în programare, cînd printr-o interfață se ascunde construcția propriu-zisă,
la care avem acces printr-o variantă simplificată, (aparent) generală.
