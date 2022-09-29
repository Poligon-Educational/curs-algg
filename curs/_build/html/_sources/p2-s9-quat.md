(cap-cuat)=
# Cuaternioni

Mulțimea cuaternionilor este una foarte surprinzătoare, din mai multe
puncte de vedere. În primul rînd, pare o structură foarte abstractă,
care impune lucrul în dimensiune 4 și prin aceasta, din start pare ceva
ce nu vom întîlni în „practică“. Acest lucru se va dovedi fals și de fapt,
aplicațiile cuaternionilor nu doar că sînt remarcabile prin rafinament
și grad de sofisticare, dar sînt și la îndemînă. Începînd cu teoria 
relativității a lui Einstein, din prima parte a secolului XX, ideea de
a lucra cu spații de dimensiune 4 pentru situații „concrete“ a devenit
tot mai utilizată. Apoi, numeroasele aplicații pe care și le-au găsit numerele
complexe au invitat la încercări de generalizare, în special țintind diverse
aplicații din algebră.

Pe la jumătatea secolului al XIX-lea, matematicianul irlandez William Rowan
Hamilton reușește să introducă structura algebrică a cuaternionilor, după 
eforturi de peste un deceniu. Acesta era în corespondență cu logicianul și
algebristul Augustus De Morgan, schimbînd idei despre formalizarea structurii
algebrice a cuaternionilor.

Dificultatea era că legile algebrei nu permiteau cea mai naturală extindere
a corpului numerelor complexe -- de la numere care aveau o parte reală și una
imaginară, la numere care să aibă o parte reală și *două* imaginare. Mult timp,
Hamilton a considerat astfel de restricții nenaturale și s-a străduit să
demonstreze că ar fi, totuși, posibil să introducă o astfel de structură, însă
fără succes.

Pînă la introducerea propriu-zisă a mulțimii și structurii cuaternionilor,
vă propunem o scurtă recapitulare privitoare la numere complexe, pentru a înțelege
mai bine apoi locul ocupat de cuaternioni.

## Numere complexe
Și istoria numerelor complexe este una foarte bogată și plină de surprize și
dificultăți. De la utilizarea lor în algebră, pentru a rezolva ecuații de gradul
al doilea cu discriminant negativ la aplicații în analiză, dar și vizualizări
și aplicații în geometrie și trigonometrie, numerele complexe (sau „imaginare“,
cum au fost cunoscute mult timp) au traversat secole, iar astăzi sînt studiate
și utilizate încă din liceu.

Nu ne propunem aici o prezentare istorică a acestei mulțimi, ci mai degrabă una
pragmatică, în care să recapitulăm principalele concepte și aplicații privitoare
la numerele complexe, așa cum apar ele începînd cu anii de liceu și pînă la
studii ceva mai avansate.

### Forme de prezentare și operații
Prin definiție, mulțimea numerelor complexe se introduce astfel:
```{math}
\mathbb{C} = \{ a + bi \mid a, b \in \mathbb{R}, i^2 = -1 \}.
```
Această prezentare se mai numește **forma algebrică** a numerelor complexe
și se pretează la numeroase aplicații privitoare la structura algebrică,
așa cum vom vedea.

Numărul $ i $ este elementul de noutate aici și se numește *unitate imaginară*.
El are proprietatea surprinzătoare de a putea fi ridicat la pătrat și a obține
o valoare negativă. Cu această aparentă[^aparenti] încălcare a regulilor algebrei -- faptul
că prin ridicare la o putere pară putem obține un număr negativ sau, echivalent,
că putem extrage radical de ordin par dintr-un număr negativ ($ i = \sqrt{-1} $,
cum este introdus în unele cărți) -- se construiește o nouă mulțime de numere.

[^aparenti]: Menționăm că încălcarea este doar *aparentă*, pentru că, așa cum vom
vedea, există prezentări echivalente ale mulțimii numerelor complexe care introduc
unitatea imaginară printr-o simplă pereche de numere reale. Rădăcina pătrată 
a numerelor negative este în continuare interzisă de *regulile interne mulțimii*
*numerelor reale*, care se pot, totuși, extinde ușor diferit în cazul complex.
Nu insistăm pe asemenea detalii tehnice și am prefera ca accentul să cadă pe 
elementele de noutate introduse de numerele complexe, atît din punct de vedere
algebric, cît și geometric, așa cum vom vedea.

Acum, în forma algebrică, numerele complexe sînt ușor de utilizat, cîtă vreme
ținem cont de faptul că nu este permis „amestecul“ părților lor reale și imaginare.
Dacă avem $ z = a + bi \in \mathbb{C} $ ca mai sus, se definește *partea reală*
a lui $ z $ ca fiind $ \mathrm{Re}(z) = a $, iar *partea imaginară*, prin
$ \mathrm{Im}(z) = b $. Atunci, adunarea și înmulțirea numerelor complexe în forma
reală se face imediat. Fie $ z_1 = a_1 + b_1i, z_2 = a_2 + b_2i \in \mathbb{C} $. 
Avem:
```{math}
\begin{align*}
  z_1 + z_2 &= (a_1 + a_2) + (b_1 + b_2)i \\
  z_1 \cdot z_2 &= (a_1 a_2 - b_1b_2) + (a_1 b_2 + b_1 a_2)i
\end{align*}
```
Formula pentru adunare se obține pur și simplu prin adunarea pe componente, iar
formula pentru înmulțire, prin calcul direct, ținînd cont de definiția $ i^2 = -1 $
și de ne-amestecul părților reale și imaginare.

În plus, se definesc *conjugata* $ \overline{z} $ și *modulul* $ |z| $ unui număr 
complex $ z = a + bi \in \mathbb{C} $ prin:
```{math}
\begin{align*}
  \overline{z} &= a - bi \\
  |z| &= \sqrt{a^2 + b^2}  = \sqrt{z \cdot \overline{z}}
\end{align*}
```
Remarcăm că modulul aduce numerele complexe în mulțimea numerelor reale pozitive,
astfel că se comportă ca funcția obișnuită de calcul al valorii absolute.

---

Odată cu aplicațiile din geometrie, numerelor complexe li s-a dat și o 
**formă geometrică**. Astfel, se definește *planul complex* ca fiind pur și simplu
planul real $ \mathbb{R}^2 $ (o analogie despre care vom discuta imediat),
iar un punct din plan $ A(a, b) $ spunem că are *afixul* dat de numărul complex
$ z = a + bi $. Cu această prezentare, modulul numărului complex capătă semnificații
geometrice, fiind lungimea segmentului care unește punctul $ A(a, b) $ cu originea
sistemului de axe, dintr-o aplicație simplă a teoremei lui Pitagora, întrucît
partea reală devine abscisa punctului, iar partea imaginară, ordonata.

```{figure} ./img/forma-geom-complex.png
---
name: fig-forma-geom-complex
---
Forma geometrică pentru $ z = 2 + 3i $ și conjugatul său
```

În acest context, operația de conjugare a unui număr complex care reprezintă afixul
unui punct din plan schimbă semnul ordonatei și păstrează abscisa, deci corespunde
unei simetrii față de axa $ OX $.

Mai mult, această prezentare permite și o analogie cu vectorii din plan, în sensul
că numărul complex $ z = a + bi $, ca afix al unui punct din plan $ A(a, b) $,
se poate asocia *vectorului de poziție* al punctului $ A $, notat de obicei
$ \vec{r}_A $, și care unește originea sistemului de axe cu punctul $ A $.
Descompus în funcție de versori, avem:
```{math}
\vec{r}_A = a \vec{i} + b \vec{j},
```
ilustrînd o dată în plus legătura dintre vectori din plan și numere complexe.

Totodată, această legătură ne permite să vedem și că adunarea numerelor complexe
corespunde la adunarea vectorilor din plan, cu aceeași observație, că părțile
reale și imaginare nu se „amestecă“, așa cum componentele (coordonatele)
corespunzătoare versorilor $ \vec{i} $ și $ \vec{j} $ rămîn separate.

Totuși, așa cum este cazul vectorilor, o astfel de prezentare nu se pretează la
o operație de înmulțire, astfel că nu putem descrie semnificativ din punct de 
vedere geometric operația de înmulțire a numerelor complexe[^inmi]. Produsul
scalar care se definește între vectori din plan, de exemplu, nu are o semnificație
aparte în cazul numerelor complexe.

[^inmi]: Înmulțirea cu $ i $, totuși, are o semnificație aparte în prezentarea
geometrică, pe care vă invităm să o descoperiți. Fie $ z = a + bi $ afixul
unui punct din plan. Cum ați caracteriza punctul de afix $ iz $? Dar pe cel
de afix $ i^2 z = -z $? Dar punctul $ i^3 z = -iz $? Puteți lucra cu exemple
particulare, dar o componentă importantă a acestui exercițiu este să folosiți
reprezentarea grafică, adică pozițiile din plan pentru punctele respective.

---

Legătura cu geometria poate fi extinsă și către trigonometrie. Astfel,
numărul complex $ z = a + bi $, care este afixul unui punct din plan $ A(a, b) $,
se mai poate scrie și sub **formă trigonometrică**, anume:
```{math}
z = r(\cos \theta + i \sin \theta),
```
unde $ r $ este modulul lui $ z $, adică $ r = \sqrt{a^2 + b^2} $, iar
$ \theta \in [0, 2\pi) $ se numește *argumentul principal* al lui $ z $
și reprezintă unghiul pe care îl descrie vectorul de poziție al punctului
$ A $ cu axa $ OX $, măsurat în sens invers acelor de ceasornic (numit și
*sens trigonometric*), începînd cu cadranul I.

```{figure} ./img/forma-trig-complex.png
---
name: fig-forma-trig-complex
---
Forma trigonometrică a numărului complex $ z = 4 + 2i $
```

### Paranteză: Coordonate polare

Această descriere conduce la așa-numitele *coordonate polare*, utilizate pentru
reprezentarea punctelor din plan. Coordonatele „obișnuite“, abscisa și ordonata,
se mai numesc și *carteziene*, fiind introduse și utilizate aprofundat de
matematicianul francez al secolului al XVII-lea, René Descartes, al cărui nume
latinizat era *Renatus Cartesius*. Intuitiv, coordonatele carteziene facilitează
lucrul cu drepte și segmente și am putea spune că împart planul real într-un
fel de sistem ortogonal similar pătrățelelor de pe foile de matematică. Însăși
reprezentarea unui punct din plan, folosind coordonate carteziene, presupune
lucrul cu drepte: se trasează o paralelă la $ OX $ în dreptul ordonatei
și o paralelă la $ OY $ în dreptul abscisei. Intersecția între cele două drepte
va fi chiar punctul căutat.

Coordonatele polare, de cealaltă parte, presupun un fel de lucru cu cercuri
concentrice. Punctului de coordonate carteziene $ A(a, b) $ îi corespunde punctul
de coordonate polare $ A(r, \theta) $, unde $ r $ este lungimea segmentului care
unește punctul $ A $ cu originea -- adică raza cercului centrat în origine și care
conține punctul $ A $ -- iar $ \theta $ este unghiul pe care îl face raza $ OA $
cu axa $ OX $, măsurat în sens trigonometric, pornind din cadranul I.

Legătura între cele două sisteme de coordonate se dă prin calcule elementare de
trigonometrie:
```{math}
\begin{cases}
  x &= r \cdot \cos \theta \\
  y &= r \cdot \sin \theta
\end{cases}
```
și în plus, avem identitatea remarcabilă că $ x^2 + y^2 = r^2 $, care este tocmai
ecuația cercului centrat în origine și cu raza $ OA $.

---

Revenind la forma trigonometrică a numerelor complexe, identități trigonometrice
simple ne permit să facem calcule surprinzătoare. Pornind de la așa-numita
*formulă a lui Moivre*, pentru două numere complexe scrise trigonometric
$ z_1 = r_1 (\cos \theta_1 + i \sin \theta_1) $ și $ z_2 = r_2(\cos \theta_2 + i\sin \theta_2) $,
găsim:
```{math}
z_1 \cdot z_2 = r_1 r_2 (\cos (\theta_1 + \theta_2) + i \sin (\theta_1 + \theta_2)).
```
Această formulă poate fi extinsă pentru calculul puterilor unui număr complex,
inclusiv al puterilor reale (deci și radicali) și chiar negative, deci și pentru împărțire.

Nu insistăm aici pe astfel de calcule, dar trebuie, totuși, menționat că, odată
cu trecerea către forma geometrică a numerelor complexe, s-a deschis posibilitatea
de a utiliza întregul aparat trigonometric, ce ne permite să ajungem la rezultate
computaționale dificile destul de ușor.

---

Tot legat de forma trigonometrică, într-o variantă ceva mai avansată, găsim și
**forma polară**. Aceasta pornește de la definiția funcției exponențiale cu ajutorul
unei serii de puteri, definiție care îi aparține matematicianului elvețian
al secolului XVIII, Leonhard Euler. Fără a intra în prea multe detalii, Euler definește
*funcția exponențială* prin:
```{math}
\exp(x) = \displaystyle\sum_{n \geq 0} \dfrac{1}{n!} \cdot x^n,
```
iar posteritatea a denumit valoarea $ \exp(1) $ *numărul lui Euler*, $ e $[^e].
Dacă se aplică tehnici de bază care asociază o serie de puteri *oricărei funcții*
*complexe*, nu doar exponențialei și nu doar în cazul real, se obține:
```{math}
\exp(ix) = \cos x + i \sin x,
```
ceea ce face ca formei trigonometrice a numerelor complexe să i se asocieze
forma polară:
```{math}
z = r \cdot \exp(i\theta),
```
unde $ r $ și $ \theta $ au aceeași semnificație ca în forma trigonometrică.

[^e]: În general, funcția exponențială -- inversa funcției logaritmice -- se definește
cu ajutorul seriilor de puteri. Totuși, în multe lucrări se obișnuiește să se
folosească notația $ \exp(x) = e^x $, pe care o vom folosi și noi. Iar dacă vă
întrebați despre funcții exponențiale de bază arbitrară, precum $ 2^x, \pi^x, 3^x $
ș.a.m.d., aflați că se acordă prioritate bazei logaritmilor naturali datorită
proprietăților pe care le are, inspirate majoritatea de apariția ei în multe
situații concrete de fizică, de la mecanică newtoniană la fizică atomică și altele.
În plus, orice altă bază se poate folosi cu ajutorul formulei de schimbare a bazei
din calculul logaritmic: $ \log_a b = \dfrac{\ln a}{\ln b} $.

O astfel de prezentare are, pe lîngă avantajele formei trigonometrice, și alte
beneficii computaționale. De exemplu, formula lui Moivre devine acum o simplă
consecință a regulii de calcul cu puteri. Refolosind notațiile din cazul
trigonometric, avem:
```{math}
z_1 \cdot z_2 = r_1 r_2 e^{\theta_1 + \theta_2}.
```
În plus, forma polară deschide și calea către extinderea unor funcții reale în cazul
complex, cum ar fi chiar logaritmul natural:
```{math}
z = re^{i\theta} \Rightarrow \ln z = \ln (re^{i\theta}) = \ln r + i\theta.
```
Sînt mai multe dificultăți tehnice cînd trecem de la funcții reale la funcții
complexe, pe care nu le detaliem aici, însă am arătat pe scurt cum legătura între
funcția exponențială și numerele complexe poate fi un punct de pornire
către rezultate spectaculoase.

---
Există și o **formă matriceală** de reprezentare a numerelor complexe, însă
trebuie avută grijă atunci cînd o exprimăm. Conform celor de mai jos, grupul
numerelor complexe, ca spațiu vectorial real, are dimensiune 2, deci dacă ar fi
să reprezentăm un număr complex ca o matrice din $ M_2(\mathbb{R}) $, trebuie să
ne asigurăm că o scriem ca un element al unui *sub*spațiu bidimensional al lui
$ M_2(\mathbb{R}) $.

Ca indicii de pornire, este suficient să reprezentăm numărul 1 și unitatea imaginară
sub formă matriceală, pentru că ulterior, orice număr complex poate fi scris ca o
combinație liniară a acestora. Ne putem baza pe faptul că numărul complex 1 trebuie
să corespundă matricei unitate și în plus, deoarece pentru numere reale avem
$ x = x \cdot 1, \forall x \in \mathbb{R} $, trebuie ca numărul real $ x $
să fie reprezentat ca matricea $ xI_2 $.

Folosind și proprietatea unității imaginare, $ i^2 = -1 $, rezultă că trebuie
să facem o corespondență pentru $ i $ sub forma unei matrice al cărei pătrat
să fie $ -1 \cdot I_2 $.

După cîteva încercări, găsim corespondența generală:
```{math}
a + bi \mapsto \begin{pmatrix} a & -b \\ b & a \end{pmatrix}.
```

Această formă matriceală nu este la fel de folosită precum celelalte și este mai 
degrabă o ilustrare a corespondenței între *spațiul vectorial* $ \mathbb{C} $ 
și un subspațiu bidimensional al lui $ M_2(\mathbb{R}) $, structuri despre care
detaliem chiar acum.

### Corpul și spațiul complex
Deja din forma algebrică, dar și din cea geometrică a numerelor complexe
putem intui că este vorba despre structuri algebrice bogate.

Dacă lucrăm, de exemplu, doar cu adunarea și înmulțirea numerelor complexe
din forma algebrică, anume:
```{math}
\begin{align*}
  z_1 + z_2 &= (a_1 + a_2) + (b_1 + b_2)i \\
  z_1 \cdot z_2 &= (a_1 a_2 - b_1b_2) + (a_1 b_2 + b_1 a_2)i
\end{align*}
```
găsim imediat că:
- ambele operații sînt interne, evident, deci produc tot numere complexe;
- ambele operații sînt asociative și comutative, deoarece se definesc folosind doar
operații elementare, asociative și comutative;
- elementul neutru pentru adunare este numărul complex $ 0 = 0 + 0 \cdot i $;
- elementul neutru pentru înmulțire este numărul complex $ 1 = 1 + 0 \cdot i $;
- opusul numărului complex $ z = a + bi $ este numărul complex $ -z = (-a) + (-b) i $;
- inversul numărului complex $ z = a + bi $ este numărul complex 
$ z^{-1} = \dfrac{a}{a^2 + b^2} - \dfrac{b}{a^2 + b^2} i $. Acesta se obține scriind
pur și simplu $ z^{-1} = \dfrac{1}{z} = \dfrac{1}{a + bi} $, iar apoi folosind 
*raționalizarea numitorilor*, adică prin amplificarea fracției cu $ \overline{z} $
și folosind identitatea $ z \cdot \overline{z} = |z|^2 $.

Concluzia acestor observații este că $ (\mathbb{C}, +, \cdot) $ este un *corp comutativ*,
numit *corpul numerelor complexe*. În particular $ (\mathbb{C}, +) $ și $ (\mathbb{C}, \cdot) $
sînt grupuri comutative.

Dar putem merge și mai departe. Inspirați de analogia planului complex cu cel real, putem
găsi un izomorfism între $ \mathbb{C} $ și $ \mathbb{R}^2 $, la nivel de corpuri comutative.
Însă pentru ca acest izomorfism să funcționeze, trebuie să definim cu atenție operațiile
pe $ \mathbb{R}^2 $. Pentru $ x = (a_1, b_1), y = (a_2, b_2) \in \mathbb{R}^2 $, definim:
```{math}
\begin{align*}
  x + y &= (a_1 + a_2, b_1 + b_2) \\
  x \cdot y &= (a_1 a_2 - b_1 b_2, a_1 b_2 + a_2 b_1)
\end{align*}
```
Evident, această definiție este dată astfel încît să corespundă operațiilor cu numere complexe.
Totuși, se poate demonstra ușor că $ \mathbb{R}^2 $ devine corp comutativ cu aceste operații,
iar funcția:
```{math}
f : \mathbb{R}^2 \to \mathbb{C}, \quad f(a, b) = a + bi
```
este un izomorfism. Folosindu-l, găsim că $ f(0, 1) = i $, iar acesta poate fi un punct
de pornire în înțelegerea unității imaginare. Mai precis, dacă analizăm cu atenție
structura de pe $ \mathbb{R}^2 $, vedem că $ (0, 1) \cdot (0, 1) = (-1, 0) $
și totodată, este evident că dacă definim submulțimea $ \{ (a, 0) \in \mathbb{R}^2 \} $,
nu avem altceva decît o „copie“ a lui $ \mathbb{R} $. Așadar, numerele reale se regăsesc
în $ \mathbb{R}^2 $ sub forma perechilor care au a doua componentă nulă.

Egalitatea $ (0, 1) \cdot (0, 1) = (-1, 0) $ devine acum una specială: pătratul
unui număr care *nu* este real (deoarece nu are a doua componentă nulă) este numărul
real $ -1 $, scris sub forma $ (-1, 0) $. E drept, operația folosită pentru acest
pătrat nu este înmulțirea standard, dar în orice caz, nu este cu mult diferită de
aceasta.

De aceea, spuneam, putem gîndi unitatea imaginară ca pe un „număr“ deosebit, însă
nu neapărat ca pe unul care „încalcă regulile algebrei“, întrucît locul lui natural
este într-un context unde funcția radical, de exemplu, și chiar funcția putere, dacă
se definesc, au o semnificație ușor diferită de cele standard.

---

Tot această legătură cu planul real, dar și structura de grup aditiv pe mulțimea
numerelor complexe ne invită să studiem o eventuală structură de spațiu vectorial.
Pentru simplitate, vom considera în continuare că lucrăm cu corpul real drept corp
de scalari. Și, cum structurile interne sînt deja clare, mai definim operația
externă cît se poate de natural:
```{math}
\alpha \cdot (a + bi) = \alpha a + (\alpha b) i, \forall \alpha \in \mathbb{R}, a + bi \in \mathbb{C}.
```
Cu această definiție, se verifică ușor că într-adevăr $ \mathbb{C} $ devine un spațiu
vectorial real. Mai mult, el are dimensiune 2, baza fiind mulțimea $ \{ 1, i \} $,
deoarece orice număr complex este o combinație liniară între unitatea reală și cea
imaginară. Acest lucru face ca spațiul vectorial $ \mathbb{C} $ să fie izomorf
(ca spațiu vectorial) cu $ \mathbb{R}^2 $, corespondența pe care am remarcat-o
anterior, la nivel de corpuri, păstrîndu-se și aici: $ 1 \mapsto (1,0) $ și $ i \mapsto (0, 1) $,
dacă este să definim izomorfismul pe bazele canonice. Evident, în cazul spațiului
vectorial complex nu mai putem vorbi de înmulțirea vectorilor, iar produsul
scalar este pur și simplu o copie a celui din $ \mathbb{R}^2 $: pentru vectorii
complecși $ z_1 = a_1 + b_1 i $ și $ z_2 = a_2 + b_2 i $, avem produsul scalar
euclidian:
```{math}
\langle z_1, z_2 \rangle = a_1 a_2 + b_1 b_2.
```

---

Vedem, deci, că prin numerele complexe am extins pe cele reale într-un sens
pe de o parte surprinzător (prin proprietățile unității imaginare), dar pe 
de altă parte, suficient de natural și de util, fiind vorba pur și simplu de
o altă modalitate de a vedea planul real.

Întrebarea care se pune, acum, este dacă am putea continua extinderea și către
o mulțime care, eventual, să joace un rol similar pentru spațiul euclidian
tridimensional. Adică să avem o nouă mulțime de numere și operații definite
între acestea în așa fel încît să ajungem cel puțin la o structură de grup
și de spațiu vectorial real, care să fie izomorf cu $ \mathbb{R}^3 $.

Așa începe căutarea cuaternionilor.

(sec-multimea-h)=
## Mulțimea $ \mathbb{H} $
Ca să trecem direct la concluzii -- deși povestirea istorică are meritele ei
și o vom prezenta altundeva -- Hamilton și nimeni altcineva nu au reușit să
construiască o mulțime nouă de numere, pe modelul mulțimii numerelor complexe,
care să fie similară într-un anume sens spațiului tridimensional real.
Toate încercările lui Hamilton se terminau cu încălcarea unor axiome fundamentale
ale algebrei: operațiile definite nu mai erau interne, se pierdea asociativitatea
ș.a.m.d. 

Un exemplu simplu de proprietate încălcată este dacă ne gîndim la
forma matriceală a numerelor complexe pe care am văzut-o și una similară pentru
numere hipercomplexe pe care o putem intui. Numărul real 1 corespunde natural
matricei unitate, indiferent de structura către care îl transportăm.
În particular, dacă am găsi un echivalent al numerelor complexe în dimensiune 3,
ar trebui să avem $ 1 \mapsto I_3 $. Similar, proprietatea de morfism care ar
face această legătură ar impune și că $ -1 \mapsto -I_3 $. Apoi ar trebui
să transportăm unitățile imaginare, $ i $ și $ j $, să spunem. Dar ținînd cont
de faptul că extindem mulțimea numerelor complexe, una dintre axiomele
corespunzătoare acestora este $ i^2 = j^2 = -1 $. Dar $ \det(-I_3) = -1 $
și nu putem găsi o matrice din $ M_3(\mathbb{R}) $ care să reprezinte
unitățile imaginare și să respecte și determinanții. Dacă, de exemplu,
matricea $ J $ (indiferent ce formă ar avea ea) reprezintă unitatea imaginară
$ j $, atunci $ J^2 = -I_3 $ și, aplicînd determinantul, rezultă
$ \det(J^2) = (\det(J))^2 = -1 $, ceea ce este imposibil pe numere reale.

Pentru dimensiune 4, însă, $ \det(-I_4) = 1 $ și se poate face corespondența.

Astfel că Hamilton a fost nevoit să accepte că nu se poate defini o astfel de 
mulțime și să încerce în dimensiune 4. Nu fără eforturi susținute, soluția a
ieșit la iveală în 1843 prin mulțimea cuaterionilor. Notată astăzi cu $ \mathbb{H} $,
în onoarea matematicianului William Rowan Hamilton, aceasta conține numere similare
celor complexe, însă *cu 3 unități imaginare*:
```{math}
\mathbb{H} = \{ a + bi + cj + dk \mid a, b, c, d \in \mathbb{R}, i^2 = j^2 = k^2 = ijk -1 \}.
```
Elementele -- cuaternionii -- își iau numele de la cuvîntul latinesc *quaternio*,
însemnînd generic „cuaternar“.


Pe lîngă faptul că $ i, j, k $ sînt unități imaginare și au pătratul egal cu $ - 1 $,
o altă proprietate definitorie este importantă, anume că *înmulțirea cuaternionilor*
*nu mai este comutativă*, ci are o proprietate numită *anticomutativitate*.
Este unul dintre obstacolele întîlnite de Hamilton, pe care, în final, a trebuit să-l
accepte. Ordinea efectuării operațiilor de înmulțire între cuaternioni contează
și anticomutativitatea se bazează pe proprietățile definitorii ale produselor dintre
unitățile imaginare:
```{math}
ij = -ji = k, \quad ik = -ki = j, \quad jk = -kj = i.
```
Aceste relații nu sînt întîmplătoare și ele se vor dovedi foarte importante în ce privește
legătura cuaternionilor cu spațiul tridimensional, însă momentan, păstrăm prezentarea
formală pentru o altă secțiune. Totodată, remarcăm că ele pot fi obținute imediat din
relația definitorie $ i^2 = j^2 = k^2 = ijk = -1 $.

Din punct de vedere algebric, operațiile dintre cuaternioni se definesc natural:
- adunarea se face pe componente;
- înmulțirea se face prin extinderea anticomutativității dintre unitățile imaginare.

Astfel că avem, pentru doi cuaternioni $ q_1 = a_1 + b_1i + c_1j + d_1k $
și $ q_2 = a_2 + b_2i + c_2j + d_2k $:
```{math}
\begin{align*}
  q_1 + q_2 &= (a_1 + a_2) + (b_1 + b_2)i + (c_1 + c_2)j + (d_1 + d_2)k \\
  q_1 \cdot q_2 &= (a_1 a_2 - b_1b_2 - c_1c_2 - d_1d_2) + \\
				&+ i(a_1 b_2 + a_2 b_1) + j(a_1 c_2 + a_2 c_1) + k(a_1 d_2 + a_2 d_1) + \\
				&+ ij(b_1c_2 + b_2 c_1) + ik(b_1d_2 + b_2d_1) + jk(c_1d_2 + c_2 d_1) + \\
				&+ ji(c_1b_2 + c_2b_1) + ki(d_1b_2 + d_2b_1) + kj(d_1c_2 + d_2c_1) \\
				&= (a_1a_2 - b_1b_2 - c_1c_2 - d_1d_2) + \\
				&+ i(a_1b_2 + a_2b_1 + c_1d_2 + c_2d_1 - d_1c_2 - d_2c_1) + \\
				&+ j(a_1c_2 + a_2c_1 + b_1d_2 + b_2d_1 - d_1b_2 - d_2b_1) + \\
				&+ k(a_1d_2 + a_2d_1 + b_1c_2 + b_2c_1 - c_1b_2 - c_2b_1)
\end{align*}
```
Laborios de scris, însă calculele de mai sus rezultă doar din proprietatea de anticomutativitate
a produsului cuaternionilor.

Se definește, de asemenea, și conjugatul unui cuaternion prin schimbarea semnului părților
imaginare, precum și modulul, printr-o formulă similară cazului complex. Dacă
$ q \in a + bi + cj + dk \in \mathbb{H} $, atunci:
```{math}
\begin{align*}
  \overline{q} &= a - bi - cj - dk \\
  |q| &= \sqrt{a^2 + b^2 + c^2 + d^2}
\end{align*}
```

Studiul proprietăților algebrice ale operațiilor de mai sus ne conduce la concluzia că
$ (\mathbb{H}, +, \cdot) $ este un corp, însă *necomutativ* -- aici intervine anticomutativitatea
menționată. Totuși, structura aditivă este de grup comutativ, astfel că ne putem aștepta
la o structură de spațiu vectorial real pe $ (\mathbb{H}, +) $, ceea ce și obținem foarte
ușor, cu înmulțirea cu scalari $ \alpha \in \mathbb{R} $ fiind definită pentru un cuaternion
arbitrar $ q = a + bi + cj + dk \in \mathbb{R} $ prin:
```{math}
\alpha \cdot (a + bi + cj + dk) = (\alpha a) + (\alpha b)i + (\alpha c)j + (\alpha d)k.
```

Este ușor de văzut acum că $ \{ 1, i, j, k \} $ formează o bază a spațiului vectorial real
al cuaternionilor, deci $ \mathbb{H} \simeq \mathbb{R}^4 $, printr-un izomorfism natural,
care face să corespundă bazele canonice:
```{math}
\begin{align*}
  1 &\mapsto (1, 0, 0, 0) \\
  i &\mapsto (0, 1, 0, 0) \\
  j &\mapsto (0, 0, 1, 0) \\
  k &\mapsto (0, 0, 0, 1)
\end{align*}
```
Spre deosebire de cazul complex, unde putem separa partea reală și partea imaginară
a unui număr, în cazul cuaternionilor, cele 3 părți imaginare formează ceea ce se cheamă
*partea vectorială* a cuaternionului, iar prima componentă („partea reală“) se numește
*partea scalară*. Astfel că un cuaternion se poate separa într-un scalar real și
un vector din $ \mathbb{R}^3 $.

Mai trebuie remarcat că, din punctul de vedere al dimensiunii spațiilor vectoriale,
avem cu siguranță și izomorfismele de spații vectoriale:
```{math}
\mathbb{H} \simeq \mathbb{C}^2 \simeq M_2(\mathbb{R}).
```

---

Fără legătură cu aceste izomorfisme, se pot da și două forme matriceale ale cuaternionilor,
utile în studiul structurii de corp. Astfel, un cuaternion $ q = a + bi + cj + dk $ se poate
reprezenta ca o matrice $ Q_{\mathbb{C}} \in M_2(\mathbb{C}) $ sub forma:
```{math}
q \mapsto Q_{\mathbb{C}} = \begin{pmatrix} a + bi & c + di \\ -c + di & a - bi \end{pmatrix}.
```

O observație importantă, chiar dacă pare foarte tehnică este următoarea:
```{important}
În corespondența de mai sus și, în general, oricînd lucrăm simultan cu numere
complexe și cuaternioni, *unitățile imaginare sînt obiecte diferite*!
Astfel, unitatea imaginară complexă $ i \in \mathbb{C} $ este un obiect matematic
diferit de unitatea imaginară $ i \in \mathbb{H} $. 

De exemplu, privite în contextul spațiilor vectoriale, prima reprezintă perechea
$ (0, 1) \in \mathbb{R}^2 $, în timp ce a doua, cvadruplul $ (0, 1, 0, 0) \in \mathbb{R}^4 $.
```

Același cuaternion se poate reprezenta și ca o matrice din $ M_4(\mathbb{R}) $:
```{math}
q \mapsto Q_{\mathbb{R}} = %
\begin{pmatrix}
a & -b & -c & -d \\
b & a & -d & c \\
c & d & a & -b \\
d & -c & b & a
\end{pmatrix}.
```

```{note}
Omitem detaliile demonstrației sau alte explicații suplimentare, dar precizăm că
reprezentarea unui cuaternion ca matrice reală *nu este unică*. Într-adevăr, se poate
arăta că pentru un cuaternion fixat, există 48 de reprezentări diferite ca matrice
din $ M_4(\mathbb{R}) $.
```

---

Vom prezenta aplicații ale cuaternionilor în geometrie și în grafica pe computer
într-un capitol separat. În ciuda faptului că $ \dim \mathbb{H} = 4 $, ca spațiu
vectorial real, există numeroase aplicații în geometria spațială.

Nu putem, totuși, să nu ne întrebăm: Putem merge mai departe? Putem construi
încă o mulțime de numere cu parte reală și imaginară care să modeleze un spațiu
$ \mathbb{R}^n $? Iar dacă da, pentru ce $ n $ se poate face acest lucru?

## Numere hipercomplexe
Mulțimea numerelor complexe a fost introdusă pentru numeroase scopuri
des întîlnite în matematică. Unul dintre cele mai clare este acela de rezolvare
a ecuațiilor de gradul al doilea cu discriminant negativ. Ulterior, s-au descoperit
numeroase alte aplicații.

În ce privește mulțimea cuaternionilor, am putea argumenta că descoperirea ei
se bazează mai mult pe o motivație algebrică. Atît Hamilton, cît și colaboratorul
și sfătuitorului său, Augustus De Morgan, au fost cercetători de prim rang
în algebra abstractă. Așa se explică interesul lor de a căuta structuri algebrice
noi, pornind de la cazuri cunoscute.

Dar cît de departe se poate merge, *dacă* se poate continua? Ce surprize ne
rezervă structurile superioare, dacă ele există? Și avem, totuși, o explicație
a faptului că nu putem face nimic în dimensiune 3?

Răspunsul la aceste întrebări este unul foarte sofisticat, departe de scopurile
acestei lucrări. Însă adăugăm două lucruri foarte importante: astfel de numere,
începînd cu cuaternionii, poartă numele de *hipercomplexe*, fiind generalizări
în dimensiune superioară ale numerelor complexe. Căutarea lor putem spune că
a ajuns la final, prin așa-numita **construcție Cayley-Dickson**, un efort
de aproape 100 de ani. Într-o lucrare din 1919, matematicianul american
Leonard Eugene Dickson a introdus o construcție care conduce la „toate“ mulțimile
de numere hipercomplexe, împreună cu structurile lor algebrice.

Din construcția respectivă preluăm două proprietăți fundamentale, a căror justificare
este extrem de sofisticată, dar poate fi găsită în lucrarea lui Dickson ({cite}`dickson`):
- dimensiunile structurilor nu pot avea decît puteri ale lui $ 2 $, ceea ce explică de
ce nu s-a putut găsi o structură în dimensiune $ 3 $ și, totodată, arată că următoarea
după cuaternioni are dimensiune $ 8 $ (fiind numită mulțime de *octonioni*);
- dacă în cazul cuaternionilor s-a pierdut comutativitatea, în cazul octonionilor
și a structurilor superioare se pierde chiar și asociativitatea. Astfel că rezultatele
nu pot fi analizate în contextul structurilor algebrice studiate pînă acum, însă
chiar și așa, au proprietăți remarcabile, care le fac, totuși, utile în algebra abstractă.
