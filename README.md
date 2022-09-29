# Algebră liniară și aplicații

Acest repository conține un curs de algebră liniară și aplicații în programare, tehnologie și nu numai.

## Cuprins orientativ

**PARTEA I:** Elemente de istorie și filosofie a conceptelor studiate;

**PARTEA II:** Elemente de matematică
- Structuri algebrice;
- Trecerea de la geometrie la algebră abstractă;
- ...

**PARTEA III:** Aplicații în programare (C++ și Python):
- calcule matriceale și vectoriale;
- algoritmi de bază cu vectori și valori proprii;
- elemente de geometrie + vizualizare.


## Idei & TODOs
[Aici](./idei.md).

## Unelte și indicații
- [Jupyter Book](https://jupyterbook.org/en/stable/intro.html);

### Setup
Am folosit un *virtual environment* în Python:
```sh
$ python -m venv .venv
```

El trebuie activat la fiecare utilizare nouă a directorului:
```sh
(curs) $ source .venv/bin/activate
```

Acolo am toate pachetele necesare în `requirements.txt`:
```sh
$ cat requirements.txt
jupyterlab
jupyter-book
matplotlib
numpy
sphinx-proof
```

pe care le putem instala cu comanda:
```sh
$ pip install -r requirements.txt
```

### Build & View
Cartea (`curs`) se compilează cu comanda:
```sh
$ jupyter-book build curs
```

Apoi se deschide `curs/_build/html/intro.html`.

## Fișiere importante
- [`_config.yml`](./curs/_config.yml): conține configurația de ansamblu a cărții;
- [`_toc.yml`](./curs/_toc.yml): conține informațiile privitoare la cuprins (fișierele incluse);
