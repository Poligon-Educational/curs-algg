# Algebră abstractă și algebră liniară

## Introducere și motivație
În această parte, prezentăm noțiuni fundamentale de algebră abstractă,
pe care le vom dezvolta și aplica apoi în cazul algebrei liniare.
Cîteva elemente de bază se studiază încă din liceu, în clasa a XII-a,
însă adesea nu sînt explicate *în context*, ci apar doar ca obiecte și
structuri noi, cu reguli de calcul care se memorează.

Pornind chiar de la denumire, *algebra abstractă* se ocupă cu *structuri generale*.
Prin definiție, „abstractul“ este ceva cît se poate de general, care poate fi
aplicat în mai multe contexte, care se potrivește mai multor cadre și pentru
care, cel mai adesea, este nevoie de *particularizare* sau de *interpretare*.
Preluînd din limbajul comun, am putea spune că „omul“ este o noțiune abstractă,
care se particularizează atunci cînd vorbim despre bărbați, femei, copii, tineri,
bătrîni, pictori, sculptori etc.

Noțiunea are sens chiar și în cazul limbajelor de programare, de pildă. Dacă vorbim
despre perechea de numere întregi `(2, -1)`, am putea-o *abstractiza*, adică
generaliza către un tip de dată de forma `(Int, Int)`, care ne-ar conduce la perechea
inițială prin *particularizare*.

Ceea ce se generalizează (*abstractizează*) în cazul algebrei sînt *structurile*
și operațiile. Altfel spus, pornim de la cazuri concrete de mulțimi de numere, împreună
cu operațiile permise între ele și le abstractizăm, formulînd legi, axiome și proprietăți
care să aibă loc într-un context cît mai general.

Concret, dacă ne gîndim la mulțimea numerelor naturale, ca un exemplu particular, ne întrebăm
ce au specific elementele acestei mulțimi și ce operații sînt permise între ele,
precum și ce proprietăți au aceste operații:
- vom presupune că înțelegem implicit ce înseamnă un număr natural (altfel spus, că oricine
poate identifica un astfel de număr și nu există riscul de confuzie între un număr natural
și un triunghi sau un număr natural și unul irațional, de pildă). Evităm, prin aceasta,
elemente tehnice de logică și teoria mulțimilor, pe care le abordăm pe scurt în secțiunea
despre [istoria și filosofia matematicii](./p1-istorie-fil-intro.md). Așadar, vom presupune
că înțelegem care sînt *elementele* mulțimii numerelor naturale;
- în continuare, ne întrebăm ce *operații* putem face cu aceste numere și găsim imediat
adunările, scăderile, înmulțirile și împărțirile, cu cîteva observații:
  + scăderea poate fi gîndită ca o adunare cu un număr căruia i s-a schimbat semnul:
  în loc de `5 - 3`, ne putem gîndi că avem de calculat suma dintre `5` și `3`, iar acestuia
  din urmă i-am schimbat semnul (obținînd ceea ce se cheamă *opusul* numărului, despre care detaliem
  mai jos)
  + similar, împărțirea poate fi gîndită ca înmulțirea cu *inversul* unui număr, adică în loc de
  `5/3`, ne putem gîndi că avem de calculat produsul între `5` și `1/3`;
  + operațiile de scădere și împărțire vin cu riscul de a ieși din mulțime în unele cazuri.
  Altfel spus, cînd scădem sau împărțim două numere naturale, nu sîntem siguri că rezultatul
  este tot un număr natural. `5 - 3` nu produce probleme, dar `3 - 5`, da. Similar, `4/1`
  este permis în interiorul mulțimii, dar `4/3`, nu;
  + stabilind că adunarea și înmulțirea sînt operațiile „de bază“, observăm în continuare
  că ele sînt comutative -- adică ordinea termenilor într-o sumă sau a factorilor într-un produs
  nu contează. Altfel spus, `a + b = b + a` și `a * b = b * a`, ca să ne exprimăm general,
  pentru orice numere naturale `a` și `b`;
  + similar, în cazul unor operații repetate, dar de același fel, ne putem alege ordinea în
  care să facem calcule. Altfel spus, putem opera cu oricîte paranteze, oriunde este necesar.
  De pildă, `a + (b + c) = (a + b) + c` și `a * (b * c) = (a * b) * c`, pentru orice
  numere naturale `a, b, c`. Proprietatea pe care tocmai am „descoperit-o“ se numește
  *asociativitate*;
  + există două numere „speciale“ în raport cu aceste operații: `0` și `1`. În cazul adunării,
  `0` are proprietatea că nu schimbă rezultatul, iar în cazul înmulțirii, `1` nu schimbă
  rezultatul. Pe de altă parte, înmulțirea cu `0` dă mereu rezultatul `0`, iar adunarea
  cu `1` are o semnificație specială, fiind legată de metoda de construire a numerelor naturale,
  cu ajutorul *succesorilor* (detalii în secțiunea de [istorie și filosofie](./p1-istorie-fil-intro.md)).

O astfel de analiză grosieră evidențiază modul de gîndire pe care îl putem avea atunci cînd
pornim spre abstractizare: studiem cazuri concrete, ne concentrăm pe elementele care definesc
mulțimea în cauză, apoi studiem operațiile permise și proprietățile acestora.

Apoi, în funcție de proprietățile de care sîntem interesați, putem folosi mai multe sau mai
puține dintre observații. De pildă, dacă alcătuim structuri algebrice precum *monoizi* sau *grupuri*,
atunci este suficient să folosim o singură operație. Pe de altă parte, putem avea și structuri
mai complicate, precum *inelele* sau *corpurile*, caz în care ne interesează două operații,
precum și interacțiunile între ele[^2op].

[^2op]: Veți fi constatat cu siguranță că, în ce privește adunarea și înmulțirea, au loc și
proprietăți care le combină. Una dintre acestea se numește *distributivitate* sau, mai simplu,
*desfacerea parantezelor* și ne arată, de pildă, că `a * (b + c) = a * b + a * c`, pentru
orice numere (e.g. naturale) `a, b, c`. Însă această proprietate nu intervine decît dacă
ne interesează structuri mai complicate, precum inelele sau corpurile.

---

Aceasta fiind abordarea generală, mergem acum către studiul
concret al cîtorva structuri algebrice, noțiuni pe care le vom aplica
și în ce privește algebra liniară.
