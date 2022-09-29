# Istoria spațiilor vectoriale

Astăzi, avem o perspectivă de ansamblu asupra structurilor algebrice și le privim
ca o evoluție treptată. De la monoizi, care au o singură operație, cu cele mai
puține proprietăți, apoi mai adăugăm o proprietate importantă și ajungem la grupuri,
după care mai adăugăm o operație și ajungem la inele, încă o proprietate ne duce
la corpuri și în fine[^structuri], complicăm structura considerînd o pereche alcătuită 
dintr-un grup și un corp și obținem un spațiu vectorial ș.a.m.d.

[^structuri]: În realitate, această „zoologie“ este și mai complicată. Există
structuri și mai obscure sau sofisticate, după necesități: magme, module, algebre
(acestea din urmă, la rîndul lor, poartă diverse nume, care le diferențiază foarte
mult: algebre Hopf, algebre Lie, algebre Weyl...) și multe altele.

Dar nu ar trebui să surprindă pe nimeni faptul că în istorie, dezvoltarea acestor
structuri algebrice nu a fost deloc la fel de simplă și de ramificată. Structurile
algebrice au apărut aproape independent și pentru scopuri de multe ori aproape
complet diferite. {ref}`Abstractizarea<sec-abstractizare>` despre care am vorbit
într-o secțiune anterioară ne oferă ceea ce în studiul academic se numește o
*citire inversă* (eng. *revese reading*) a lucrurilor, în sensul că înțelegem
cu ajutorul cunoștințelor din prezent, avînd deja o perspectivă bine dezvoltată,
lucruri din trecut. Altfel spus, aplicăm cunoștințele curente retroactiv.

Însă istoria conceptelor matematice în general și a structurilor algebrice în 
particular a fost foarte rar una bine organizată. De pildă, v-ar surprinde să aflați
că teoria mulțimilor, pe care astăzi o considerăm o ramură de bază a fundamentelor
matematicii, împreună cu logica provine din... analiză matematică și, mai exact,
din studiul seriilor Fourier și al seriilor trigonometrice?

În ce privește structurile algebrice, apariția grupurilor, de exemplu, se datorează
unor studii asupra permutărilor și matricelor, de către Joseph Louis Lagrange
și Arthur Cayley în primă fază (secolele XVIII-XIX) și extinse ulterior cu 
studiul rădăcinilor ecuațiilor algebrice prin Évariste Galois (secolul XIX).

Noi ne vom concentra aici pe *istoria spațiilor vectoriale*. Chiar și așa, este
greu de făcut o legătură unică între concepte matematice atît de importante,
pentru că tocmai prin generalitatea lor, se pretează la multiple abordări și
aplicații, care le leagă adesea de foarte multe domenii. Mai mult, înainte chiar
de a se fi formalizat conceptul, putem găsi frînturi ale acestor structuri în
mai multe locuri și ne putem întreba, de pildă:

> Calculul matriceal și proprietățile operațiilor cu matrice pot fi considerate puncte 
> de pornire pentru spații vectoriale? Dar transformările geometrice? Dar mecanica 
> newtoniană, prin utilizarea vectorilor în plan și în spațiu?

În cele ce urmează, vom folosi în special articolele {cite}`moore`, {cite}`grayvsp`,
{cite}`dorier` și {cite}`stout`, în care se trasează originea conceptului de spațiu
vectorial și din care vom extrage în special părțile legate de geometrie și
calcul vectorial, pe care le detaliem în celelalte părți ale cursului.

## Inspirație geometrică și algebrică
```{figure} ./img/felix_klein.png
---
name: fig-felix-klein
---
Felix Klein (cca. 1850), via Wikipedia
```

**Felix Klein (1849-1925)** a fost un matematician german ale cărui reușite merg dincolo
de rezultate matematice propriu-zise. În 1872, Klein publică lucrarea
*Vergleichende Betrachtungen über neuere geometrische Forschungen* (*Cercetări comparative*
*asupra dezvoltărilor geometrice recente*), care devine un program de cercetare,
cunoscut astăzi sub numele de *Programul de la Erlangen*, după universitatea la
care lucra autorul.

Programul propus de Klein este unul de utilizare a metodelor algebrice în studiul 
geometriei. Am putea trasa istoria acestor idei tocmai în secolul al XVII-lea,
unde francezii François Viète și René Descartes au introdus notația pe care o
cunoaștem astăzi pentru coordonatele punctelor din plan. Tot odată cu ei, s-a
formalizat și notația algebrică pentru ecuații polinomiale.

Klein introduce un {ref}`grup de ordin 4<sec-gr-klein>`, *Vierrengruppe*, care astăzi 
îi poartă numele și a cărui descriere poate fi formulată cu ajutorul transformărilor 
din plan. Aceasta s-a dovedit o inițiativă deosebită pentru aplicarea metodelor
algebrice în studiul geometriei și nu după mult timp, un mare contemporan și compatriot 
al lui Klein, **David Hilbert (1862-1943)**, face următorul pas foarte important,
prin contribuțiile sale fundamentale în domeniul numit astăzi *geometrie algebrică*.

```{figure} ./img/Hilbert.jpg
---
name: fig-david-hilbert
---
David Hilbert (cca. 1912), via Wikipedia
```

Cu ajutorul geometriei algebrice, Hilbert și colaboratorii săi -- dintre care menționăm
pe una dintre cele mai importante figuri feminine din matematică, 
**Emmy Noether (1882-1935)** -- au dat înțelesuri precise interpretărilor geometrice
ale structurilor algebrice. Și tot de Hilbert și contemporanii săi se leagă și 
introducerea structurilor algebrice de *inel* și *corp*, cărora le-au găsit aplicații
fundamentale și în fizică.

```{figure} ./img/Noether.jpg
---
name: fig-noether
---
Emmy Noether (cca. 1900), via Wikipedia
```

Precum menționează și istoricul și matematicianul Jeremy Gray în {cite}`grayvsp`,
este foarte probabil ca de-a lungul istoriei, matematicienii să fi folosit concepte
pe care astăzi le legăm în mod fundamental de spații vectoriale fără a le
formaliza sau a le pune în acest context riguros. Operația fundamentală dintr-un spațiu
vectorial, aceea de *combinație liniară*, a stat la baza rezolvării sistemelor de
ecuații liniare cel puțin din timpul lui Carl Friedrich Gauss (1777-1855). De fapt,
s-au găsit chiar dovezi că poporul chinez, în primele secole ale erei noastre,
făcea operații cu numere tabelate într-un fel de proto-matrice și similar, rezolvau
sisteme liniare prin metoda substituției și a reducerii. Aceste metode nu sînt altceva
decît combinații liniare ale vectorilor care alcătuiesc liniile sau coloanele matricei
sistemului.

În plus, dacă situăm lucrurile în contextul istoric, realizăm că și 
**William Rowan Hamilton (1805-1865)**, cel creditat cu introducerea cuaternionilor
a fost aproape contemporan cu Hilbert. Importanța majoră a acestui fapt este aceea
că, așa cum {ref}`am arătat și noi<cap-cuat>`, cele 3 unități imaginare ale cuaternionilor
au fost introduse tocmai pentru a respecta axiome ale structurilor algebrice.
De aici, este clar că Hamilton și contemporanul și colaboratorul său, Augustus De Morgan,
cunoșteau și utilizau măcar o parte a axiomelor algebrei abstracte.

```{figure} ./img/hamilton.png
---
name: fig-hamilton
---
Sir William Rowan Hamilton (cca. 1850), via Wikipedia
```

O altă sursă de inspirație importantă pentru istoria spațiilor vectoriale este geometria.
Și nu ne referim numai la geometria în plan și în spațiu, eventual aplicată pentru
rezolvarea problemelor de fizică clasică. Se arată în {cite}`moore` că, deși ideea de
segment orientat a fost utilizată în fizică și geometrie încă din secolul al XVIII-lea,
unde astronomii foloseau termenul ca sugerînd distanțe și raze ale planetelor, în
matematică, un vector rar apărea cu un sens diferit de cel al reprezentării geometrice
din dimensiune cel mult 3. Etimologia cuvîntului provine din latinescul *vectus*,
care înseamnă *a purta, a transporta*, ceea ce explică utilizări ca *vector de poziție*
sau *rază vectoare* din astronomie, făcîndu-se referire la un transport, o mișcare
închipuită.

Sensul modern al vectorilor, fundamental pentru înțelesul spațiilor vectoriale apare
la Giuseppe Peano, în jurul anului 1890.

De fapt, înainte să trecem chiar la Giuseppe Peano, mai adăugăm că mulți matematicieni
ai finalului de secol XIX datorează foarte mult lucrărilor lui **Hermann Grassmann (1809-1877)**,
un matematician german ale cărui merite au ieșit tîrziu la iveală.

```{figure} ./img/grassmann.webp
---
name: fig-grassmann
---
Hermann Grassmann (1809-1877), via Encyclopedia Britannica
```

O înțelegere a genezei ideilor care au stat la baza spațiilor vectoriale nu se poate
face fără un studiu al operei lui. Deși nu s-a bucurat de o popularitate foarte mare,
operele lui Grassmann se pot găsi și în traduceri moderne, în engleză, cum este cazul
{cite}`grassmann`, pe care o propunem pentru un studiu amănunțit.

Continuăm acum cu privirea de ansamblu asupra ideilor ce au stat la baza spațiilor
vectoriale.

## Sisteme liniare
Conform {cite}`moore`, una dintre primele apariții ale termenului de „vector“
în algebră se datorează lui William R. Hamilton. Odată cu introducerea cuaternionilor,
acesta a vrut să separe partea reală de cele 3 părți imaginare, astfel că
a denumit partea reală, *scalară* și pe cea imaginară (cu toate cele 3 unități),
*vectorială*.

Matematicianul italian **Giuseppe Peano (1858-1932)**, căruia i se atribuie și
lucrări care au stat la baza axiomatizării numerelor naturale, are trei încercări
de a defini conceptul de spațiu vectorial.

```{figure} ./img/peano.jpg
---
name: fig-peano
---
Giuseppe Peano, via Wikipedia
```

De fapt, ceea ce face Peano este să utilizeze ingrediente pe care le considerăm
astăzi fundamentale în teoria spațiilor vectoriale pentru scopuri diferite,
intenția lui nefiind să introducă noi structuri algebrice. Peano scrie explicit
că lucrările lui continuă munca lui Grassmann din așa-numita *teorie a extinderilor*
(*Ausdehnungslehre*, în original) și introduce n-tuplurile de numere, precum
și operațiile cu acestea, pe componente:
```{math}
\begin{align*}
	(a_1, a_2, \dots, a_n) + (b_1, b_2, \dots, b_n) &= (a_1 + b_1, a_2 + b_2, \dots, a_n + b_n) \\
	\alpha \cdot (a_1, a_2, \dots, a_n) &= (\alpha a_1, \alpha a_2, \dots, \alpha a_n).
\end{align*}
```

Lucrările lui Peano au fost traduse în engleză și se găsesc în cartea {cite}`peano`,
pe care o recomandăm pentru studiu aprofundat, împreună cu colecția lui Grassmann
({cite}`grassmann`). De asemenea, două lucrări care extind și explică teoria lui
Grassmann sînt {cite}`hydeDir` și {cite}`hydeSpace`.

Metodele lui Peano au încercat să algebrizeze teoriile lui Grassmann,
care erau strîns legate de geometrie. Ceea ce Grassmann numea *adunarea punctelor*,
Peano a scris sub formă abstractă ca sumă de n-tupluri ca mai sus. În ultimul capitol
din {cite}`peano`, intitulat *Transformări ale sistemelor liniare*, apare chiar definiția
unui spațiu vectorial real:

```{prf:definition}
:label: def-sp-vect-peano

Există sisteme de obiecte pentru care se dau următoarele definiții:

- Există o echivalența între două obiecte ale sistemului, adică o propoziție
notată $ a = b $, [...]
- Există o *sumă* a două obiecte $ a $ și $ b $, adică se definește un obiect
notat $ a + b $, care aparține aceluiași sistem și care satisface condițiile:

$$ (a = b) \Rightarrow (a + c = b + c), a + b = b + a, a + (b + c) = (a + b) + c $$

- Dacă $ a $ este un obiect al sistemului și $ m $ este un întreg pozitiv, numim $ ma $
suma a $ m $ obiecte egale cu $ a $. [...]

- În fine, presupunem că există un obiect al sistemului, pe care îl notăm cu $ 0 $,
astfel încît, pentru orice obiect $ a $, produsul $ 0a = 0 $, iar dacă notăm
$ a - b = a + (-1)b $, atunci $ a - a = 0, a + 0 = a $.

Sistemele de obiecte care satisfac proprietățile de mai sus se numesc *sisteme liniare*.
```

Peano oferă și exemple, anume numerele reale, numerele complexe și vectorii din plan
și din spațiu. Mai mult, cu o creativitate deosebită, Peano oferă și exemplul 
funcțiilor polinomiale de o variabilă reală și notează chiar că, dacă restrîngem
gradul maxim al polinoamelor la $ n $, atunci dimensiunea acestui sistem liniar
va fi $ n + 1 $, dar dacă nu impunem o astfel de restricție, obținem dimensiune
infinită.

Faptul că Peano ajunge atît de departe în a formaliza conceptul de spațiu vectorial
și chiar dă exemple complet diferite de contextul „vizibil“ al geometriei este
realmente surprinzător.

Din păcate, așa cum s-a întîmplat și cu o bună parte a operei lui Grassmann,
nici sistemele liniare ale lui Peano nu s-au bucurat de succes și utilizare pe scară
largă din partea matematicienilor. În fapt, Peano însuși nu a acordat suficient
de multă atenție subiectului, considerîndu-l doar un rezultat secundar, pe care l-a
folosit în teorii mai sofisticate și nu unul care merită atenție de sine stătător.

Similar l-au tratat și compatrioții și contemporanii săi, **Cesare Burali-Forti** și
**Roberto Marcolongo**, care, deși au scris o lucrare intitulată *Transformări liniare*
în 1912, unde menționează lucrările lui Peano, aplicațiile pe care aceștia le urmăresc
erau în mecanică și notează numai:

> Trecem pe scurt în revistă fundamentele teoriei generale a sistemelor liniare și
> a operatorilor liniari. În general, aceste lucruri sînt binecunoscute, în mare parte.

```{figure} ./img/burali-forti.jpg
---
name: fig-burali-forti
---
Cesare Burali-Forti (1861-1931), via Wikipedia
```

La fel au stat lucrurile și cu analistul **Salvatore Pincherle**, care face, totuși,
o remarcă în 1897 într-un articol din *Mathematische Annalen*:

> Ne rămîne doar să cităm anumite lucrări care se ocupă de calcul funcțional,
> dar care îl tratează dintr-un nou punct de vedere și care astfel fac anumite
> generalități din acest calcul foarte clare și aproape intuitive. Acesta este
> punctul de vedere al vectorilor sau al calculului geometric. [...] Pe acest
> subiect, Peano a scris pagini foarte interesante unde [...] dă cele mai simple
> proprietăți ale operațiilor liniare aplicate elementelor determinate de $ n $
> coordonate. Autorul notează [...] că se pot considera chiar și sisteme liniare
> cu un număr infinit de dimensiuni.

Patru ani mai tîrziu, Pincherle scrie o lucrare în care reia axiomele lui Peano pentru
spații liniare într-un context surprinzător: acela al funcțiilor analitice, despre
care a demonstrat că este infinit dimensional.

```{figure} ./img/pincherle.jpg
---
name: fig-pincherle
---
Salvatore Pincherle (1853-1936), via Wikipedia
```

Privind în urmă, am putea spune că motivul pentru care metodele lui Peano nu s-au
bucurat de succesul meritat este acela că în perioada respectivă, adică în chiar
ultimii ani ai lui 1800 și primii ai lui 1900, *sistemele axiomatice* nu erau des
întîlnite. Matematicienii nu erau obișnuiți să lucreze cu structuri definite cu
ajutorul unor axiome. Astfel că descrierea pe care a dat-o Peano pentru sistemele
liniare erau greu de înțeles și mai ales, greu de apreciat la adevărata valoare.

---

În jurul anului 1898, Peano își schimbă abordarea: în loc să se concentreze pe
rezultate de geometrie și analiză, pentru care sistemele axiomatice să fie doar
un produs secundar sau un ingredient, acesta pornește cu ținta explicită de a
*axiomatiza geometria*, cu ajutorul vectorilor:

> În această lucrare îmi propun să iau în considerare ideile care se întîlnesc
> în teoria vectorilor și să le clasific în idei primitive, care sînt extrase
> din observații ale spațiului fizic și idei derivate, a căror definiție este
> dată; și să consider care propoziții pot fi presupuse primitive și care sînt
> deduse drept consecințe ale acestora, prin procese pur logice, fără apel la
> intuiție.
> Astfel, teoria vectorilor pare să fie dezvoltată fără a presupune studii
> geometrice anterioare. Și de aceea, toată geometria se poate trata cu
> ajutorul acestei teorii și rezultă posibilitatea teoretică de a înlocui
> geometria însăși cu teoria vectorilor. {cite}`peanoAnalisi`

Singurele două concepte pe care Peano le-a luat drept primitive au fost punctele
și egalitatea segmentelor, pe care a scris-o folosind noțiuni anterioare: un segment
era gîndit ca o diferență de puncte, deci egalitatea segmentelor $ [AB] $ și
$ [CD] $ s-ar scrie $ a - b = c - d $, unde $ a,b,c,d $ sînt puncte. Pe lîngă
acestea, el a trasat 11 axiome, care acoperă chiar mult mai mult decît structura
de spațiu vectorial, printre care chiar și structura de 
{ref}`spațiu euclidian<sec-sp-eucl>`. El a notat produsul scalar al doi vectori
$ u $ și $ v $ prin $ u \mid v $ și a scris axiomele:
```{math}
\begin{align*}
  u \mid v &\in \mathbb{R} \\
  u \mid v &= v \mid u \\
  (u + v) \mid w &= u \mid w + v \mid w \\
  u \neq 0 &\Rightarrow u \mid u \in (0, \infty)
\end{align*}
```

Nici această axiomatizare nu a avut multe ecouri în comunitatea matematică,
cu o excepție notabilă. În lucrarea sa din 1903, *Principiile matematicii*,
fundamentală pentru ceea ce avea să devină curentul logicist (și pe care îl vom
detalia într-un capitol ulterior), britanicul **Bertrand Russell (1872-1970)**
practic traduce axiomele lui Peano (creditîndu-l corespunzător). Russell mai
adaugă că o astfel de definiție, bazată pe axiome, se poate folosi pentru
spații euclidiene și, chiar dacă nu este singura posibilă, în opinia lui, este
cea mai simplă.

```{figure} ./img/russell.jpg
---
name: fig-russell
---
Bertrand Russell (cca. 1957), via Wikipedia
```

## Regula paralelogramului
Poate surprinzător, o inițiativa de axiomatizare a calculului cu vectori a apărut
în lucrările francezului **Gaston Darboux (1842-1917)**.

```{figure} ./img/darboux.jpg
---
name: fig-darboux
---
Gaston Darboux (cca. 1910), via Wikipedia
```

În 1875, Darboux publică o lucrare în care tratează rezultanta unor forțe concurente
care acționează asupra aceluiași corp. Pentru aceasta, are nevoie de o regulă de
compunere a forțelor, adică de adunare a vectorilor. Este ceea ce astăzi numim
*regula paralelogramului*.

```{figure} ./img/regula-par.png
---
name: fig-regula-par
---
Regula paralelogramului de calcul al sumei vectoriale
```

În urma articolului respectiv, Darboux își propune să se concentreze pe problema
calculului vectorial din punct de vedere pur geometric, axiomatic. De aceea,
începe lucrul la propriul set de axiome care să îl ajute în acest sens (cf. {cite}`darboux`):

1. Rezultanta totală este unică și nu se schimbă prin permutarea ordinii rezultantelor parțiale.
2. Rezultanta totală nu se schimbă prin rotirea segmentelor în jurul unui punct.
3. Legea compunerii se reduce la adunarea algebrică pentru segmente care au aceeași direcție.
4. Direcția și mărimea rezultantei sînt funcții continue în raport cu segmentele.

Aceste axiome ale lui Darboux au fost preluate de alți doi matematicieni germani, Rudolf
Schimmack și Georg Hamel, care le-au extins pentru a ține cont și de celelalte proprietăți
de bază ale adunării: comutativitatea și asociativitatea. Pînă după 1910, lucrările lui
Darboux, continuate de Schimmack și Hamel, dar preluate și de alți matematicieni,
s-au amestecat cu studiul funcțiilor continue în ceea ce astăzi am numi spații vectoriale
de funcții reale continue. În particular, s-a ajuns la conceptul de bază a unui astfel
de spațiu, pentru care se cereau proprietăți suplimentare, dat fiind că era vorba
despre spații de funcții. Abia în jurul anului 1929, cînd s-a demonstrat existența
bazelor căutate putem spune că un produs colateral a fost acceptarea structurii de
spațiu vectorial și a prezentării sale axiomatice.

---

Pînă în jurul anului 1930, cercetările foloseau spații vectoriale implicit, de obicei
pentru aplicații analitice sau în strînsă legătură cu geometria. O oarecare excepție
o constituie lucrarea lui Hermann Weyl, *Spațiu, timp, materie* (1918), urmată în 1928
de *Teoria grupurilor și mecanica cuantică*, în care aplicațiile vectorilor și ale
spațiilor vectoriale se leagă ceva mai strîns de algebra abstractă. La fel este cazul
și teoriilor lui Hilbert, care introduce *Zahlring*, *inelul numerelor (întregi)*,
un punct de cotitură important, apărut chiar din 1897. 

Odată cu impunerea treptată a metodelor axiomatice, prin chiar figura influentă a 
lui Hilbert și apoi, prin descendenții acestuia, începe să se contureze tot mai
clar o prezentare abstractă, axiomatică, generală, mai ales prin intervenția
lui Abraham Fraenkel. Pornind de la conceptul de *Zahlring* al lui Hilbert, dar și
de la numerele hipercomplexe, Fraenkel își propune o axiomatizare cît se poate
de generală a structurilor (algebrice de numere), întrucît -- considera el --
numerele nu sînt esențiale doar pentru cei care lucrează în aritmetică.
Formalizarea multor astfel de structuri vine, însă, de la Emmy Noether, în
lucrarea ei din 1921, *Teoria idealelor în inele*.

---

În concluzie, ca o privire de ansamblu, putem spune că ideile abstracte remarcabile
ale lui Peano merită recunoscute, ca fiind printre primele încercări atît de
generale pentru o teorie abstractă a spațiilor vectoriale. Faptul că ele nu au
primit recunoașterea potrivită este explicabil în primul rînd prin aceea că
matematica nu era încă familiarizată cu metoda axiomatică. De îndată ce Hilbert
și colaboratorii săi au propus tot mai apăsat această inițiativă de prezentare
abstractă, axiomatică -- sub forma curentului pe care astăzi îl numim *formalism*
și despre care vom discuta într-un capitol ulterior -- metodele s-au diversificat
și atenția s-a mutat tocmai asupra acestor abordări pe care, privind retrospectiv,
le putem considera vizionare.

Din punctul de vedere al fluxului ideilor, reținem că structura de spațiu vectorial
a fost de la început strîns legată de geometrie. Legături ulterioare au arătat 
relevanța calculului vectorial în analiză, fizică, topologie și multe alte domenii.
