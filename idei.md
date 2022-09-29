# TODOs
- [ ] de făcut index cu cuvinte-cheie;
- [ ] de personalizat fonturi, culori în ansamblu;
- [ ] de personalizat numele bucăților (*definition*, *theorem* etc.);
- [ ] prettify LaTeX (mai uniform...);
- [ ] dark mode;
- [ ] de revenit pentru a adăuga cross-references & citări;
- [ ] probleme cu `\overline`;
- [ ] probleme cu numărătoarea;
- [ ] de împărțit altfel (părți/capitole/secțiuni);
- [ ] de folosit culori în text (pentru elemente din anume mulțimi diferite etc.);
- [ ] changelog (ultimile modificări și ce pagini s-au schimbat) -- preluat din `git`, cu filtru, doar dacă se schimbă `.md` sau `.tex`-uri?
- [ ] tooltips popup peste link-uri?

---

# De citit documentație
- [Sphinx LaTeX customization (incl. preamble)](https://www.sphinx-doc.org/en/master/latex.html);
- [MyST Syntax guide](https://myst-parser.readthedocs.io/en/latest/syntax/optional.html#syntax-mathjax);
- [Manim](https://github.com/3b1b/manim);
- [Side by side responsive (sub)figures](https://github.com/executablebooks/jupyter-book/issues/820);

---

# Capitole
**Majoritatea exemplelor vor fi în 2D și 3D.**

## [ ] P2 (+ P3): Geometrie în plan & spațiu
- de adăugat ca un capitol nou;
- **spații afine**;
- transformări geometrice (+ afine);
  + prezentare generală (funcțională);
  + prezentare matriceală;
  + opțional: legături (izomorfisme);
  + de revăzut shearing (fără translație!);
  + de adăugat exemple concrete cu transformări succesive și inverse (în 3D);
- produs vectorial + generalizare (produs exterior -- prea greu);
  + handedness în sisteme de coordonate ([exemplu](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/bb324490(v=vs.85)));
  + [Freya Holmer dot product](https://mobile.twitter.com/freyaholmer/status/1200807790580768768?lang=en);
  + [Freya Holmer cross product](https://twitter.com/freyaholmer/status/1203059678705602562?lang=en);
  + `alga` (+ material Rodica);
- arii și volume;

Bibliografie (grafică):
- Hughes, Van Dam - *Computer Graphics, Principles and Practice*, 3rd edition, 2014;
- Schneider, Eberly - *Geometric Tools for Computer Graphics*, 2003;

**Separat matematică și implementare**.
  
## [ ] P2: Vectori și valori proprii
- neapărat început cu motivație și multe exemple:
  + din AI (e.g. SVD);
	* [Principal Component Analysis (PCA) @ Math](https://en.wikipedia.org/wiki/Principal_component_analysis);
	* [PCA @ AI](https://vitalflux.com/why-when-use-eigenvalue-eigenvector/);
	* [Eigenfaces](https://en.wikipedia.org/wiki/Eigenface);
  + [Eigenvalues of geometric transformations](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors#Eigenvalues_of_geometric_transformations) -- v. și capitolul de mai sus (transformări geometrice)!
- diagonalizare -> extragerea „informațiilor esențiale“ (asemenea numerelor prime);
- forma canonică Jordan -- **Se pare că principalele aplicații sînt în exponențiale matriceale și ecuații diferențiale!**
  + vezi Strang, *Appendix B*;
  + de căutat aplicații -- chiar e necesară?

## [X] P2: Produs scalar și ortonormare
- accent pe Gram-Schmidt + implementare algoritmică;
- versori -> sistem de coordonate;
- complement ortogonal;

## [ ] P2: Spații normate
- diverse exemple de distanță (incl. Manhattan - pentru pixeli?);
- la geometrie în plan și spațiu, nu cred că are rost despre spații normate în general;
  
## [ ] P2: Conice și cuadrice (?)
- dacă găsești aplicații oarecum algoritmice de aducere la forma canonică;

## [X] P2: Cuaternioni
- numere complexe mai întîi;
- numere hipercomplexe în general;
- structura algebrică de corp;
- structura algebrică de spațiu vectorial;
- aplicații în geometrie --> *La geometrie în plan și spațiu*

## [ ] P3: NLP
- spațiul vectorial de cuvinte/ocurențe;

## [X] P2 + P3: Descompuneri matriceale
- LU;
- Cholesky;
- SVD;
- altele;

## [ ] P3: Direcții suplimentare
- teoria categoriilor: adaugă abstract;
- topologie: adaugă idei din cazul real;
- analiză funcțională: adaugă analiză;
- tipuri de geometrie, bazate pe spații vectoriale (diferențială, algebrică, complexă);
- mai departe: algebre (diverse);
- aplicații în fizica modernă: spații Hilbert;
- teoria măsurii;

## [ ] P3: Cod
- Implementare concepte OpenGL de bază în Python: 
  + *Developing Graphics Frameworks with Python and OpenGL* - Lee Stemkoski, Michael Pascale;

## [ ] P1: Biografii
- Felix Klein;
- Hermann Grassmann;
- William R. Hamilton;

## [ ] P1: Discuții filosofice
- numere complexe;
- dimensiuni superioare;
- structuralism; 

## [ ] P1: Istorie
- conceptul de spațiu vectorial:
  + [Wiki](https://en.wikipedia.org/wiki/Vector_space#History);
  + [The history of the concept of a finite-dimensional vector space - Jeremy Gray](https://hal.archives-ouvertes.fr/hal-01306970/document);
  + [A General Outline of the Genesis of Vector Space Theory - J. L. Dorier](https://pdf.sciencedirectassets.com/272588/1-s2.0-S0315086000X00249/1-s2.0-S0315086085710245/main.pdf?X-Amz-Security-Token=IQoJb3JpZ2luX2VjEOj%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaCXVzLWVhc3QtMSJHMEUCIQCbj4D7q9zivgo%2BudZ8GpcVnIpxZPEsP0j%2FcfMP1Es1CQIgLLSpmhsgG29Mnsv1s9BlqBRvOebA%2BsUN%2F%2FfB5bU3TMsq0gQIcRAFGgwwNTkwMDM1NDY4NjUiDC2e7AY%2B616Yj3MxJCqvBORGsAiSJWK%2FWyBFfzyahe4yldW2h35IRfTZvi9GdkHppylOu60LN4jLEmzvWwK5ABBVgBavLfn%2FuIuNygn2TI7x1uKEhpn8zD%2FTylQ96096QMrwzZuR1Ae9pj3HOi35uJh6p5cX4blTNC5icVCDYz7qldccTIAq%2BccCdQ1hpspiMQRXkGZWyBrbK%2FYOC4E1stW52FrGYrA43tD9jse372IKMOIXsthasW2IRHGob7%2FsAHMUO1WQYOq9yE4WjmyOXOJWwUYJRKZTjHOG1sYu3Sf2Jn7Y6mQ4au8zfRxr6PX4wyPvz5pIW3QrWoF1hJtqouMomBOmzKUG%2FcDaQ8QrDy9JxNayZRcz2ZOC0kFwcEAsl8fnP%2FjugdSUgiMKzZnxZw8roUZy7%2BgZ2LBvmvdS2B0c8p0HXvyZCayiIyP0QW%2BVtSpHE2iGIrhvfSfTKH3h8eWL3gJUU4NVdDk%2FMFkUtUP4xRXAFGUfQ67VlrqnSN1w9VUjYAaofUxv29kBfl5MPUR1kGy0OSHFhNyVCdYZY%2FWeXEdJRvuiRS1ZjEMea6CMmvWjghXfcbQTk%2BdweP5gmwuX3XvGWW8V7KWADhgsd%2Fk9mUdixgvcgrqHQ4KqzYsGRwQ8g2vAVIHouhWxcESDXsMLgcHf9k3PgzC2mx%2BdWxJwsp4qiorcsWxacbS%2FEKOnLsz2A5S5%2BVGXXhW5Bcg4zMInJGrJ8v2RcBWHRS7WWhcjIdsKNgfqVYlWfTIWDxEwjcDBmAY6qQEe%2FjDhtDU6SQdv8h2NWkUt%2F3WjmWf4dSZ1TZ%2BXDBjqiGMWA5IqH%2BV573OQMUlXXslzZSZR8%2BB%2BBEyluE8N3wk7jSc09PcetXtlPNxvUkQcewHbIq3RY815ytg026iv8t3rqdygA6U9H421iGyUJkxO4zbJoaYrOUmme9XykUk%2FLxVr9Z72Q4UTZj%2B3Rx%2BBij5uLRbHv8xSyppyJ8laZQ%2B1kUsfFSfd0VOR&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20220901T083314Z&X-Amz-SignedHeaders=host&X-Amz-Expires=300&X-Amz-Credential=ASIAQ3PHCVTY6CK4WVG3%2F20220901%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Signature=cc42867c4b84b33a8983fb2f5ca930ead0f32b15a4e71a3442548507ffb316d8&hash=78c8cdd4a059b5c31b5aa285680d2a840c6914af6de0202a3999ae219e2abde1&host=68042c943591013ac2b2430a89b270f6af2c76d8dfd086a07176afe7c76c2c61&pii=S0315086085710245&tid=spdf-7564d394-6748-4f5b-8b20-e466b5f8e0c9&sid=2fed6f9c2fd44347a879fe2652273d7a4865gxrqb&type=client&ua=585751060f5e04&rr=743ca8f148af98b8);
  + [The Axiomatization of Linear Algebra - Moore](https://www.sciencedirect.com/science/article/pii/S0315086085710257);
  + [The Development of Algebraic Structures During the 19th Century - R. Stout](https://pillars.taylor.edu/cgi/viewcontent.cgi?article=1002&context=acms-1981);

## [ ] P2: Grupuri de simetrie ++
- opțional, mai dificil decît cel în care am vorbit despre permutări, diedral etc;
- despre SO, SL, SU etc.
- cîteva aplicații în fizică și geometrie
- vezi, de exemplu [aici](https://en.wikipedia.org/wiki/3D_rotation_group) pentru rotații;
