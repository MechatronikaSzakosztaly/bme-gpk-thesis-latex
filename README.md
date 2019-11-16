# bme-gpk-thesis-latex
BME GPK irányelvek szerinti szakdolgozat és diplomaterv sablon.

A sablon alapja a BME VIK MIT [thesis-template-latex] sablonja.

Kapcsolódó dokumentumok:
- GPK [Útmutató]
- GPK [Word sablon]

Jelenlegi kimenet: [`thesis.pdf`]

### Tulajdonságok
- [x] GPK irányelveknek megfelel
- [x] Egyoldalas és kétoldalas nyomtatás
- [x] `XeLaTeX`, `PDFLaTeX` és `LuaLaTeX` kompatibilitás
- [x] Diplomaterv és Szakdolgozat automatikus kezelése
- [x] Angol nyelvű dolgozat támogatása


## Letöltés
Az oldal tetején látható `Clone or download` gomb megnyomásával `Download ZIP`

vagy

    $ git clone https://github.com/MechatronikaSzakosztaly/bme-gpk-thesis-latex.git


## Használat
A használatról a `thesis.pdf` 2. és 4. fejezete ad felvilágosítást. A forrásfájlokat a 4.6 fejezet részletezi.

Mindenképp olvasd el a [GPK Útmutató]t is, ugyanis a dolgozat pontos formai követelményeit abban találod!

### Gyorstalpaló
A fő `.tex` fájl a gyökérmappában található `thesis.tex`. Ebben `%TODO` kommentel vannak jelölve a beállítandó paraméterek.

A saját forrásfájlokat a `content/` mappa tartalmazza, ezeket kell átírni illetve kicserélni a saját tartalomra. A sablon belső fájljai az `include/` mappában vannak, ezeket ideális esetben nem kell módosítanod. A képeket a `figures/` mappába, a bibliográfiát pedig a `bib/` mappába célszerű helyezni.

### Szoftverek
Szerkesztésre az Overleaf, Windowson a TeXStudio, Linuxon a LaTeXila (GTK) vagy a Kile (Qt) javasolt. Ha VS Code szerkesztőt használsz, a Latex Workshop kiegészítővel érdemes próbálkoznod.

Fordítók közül a `PDFLaTeX` preferált, de a többi is működik.


### GYIK

#### 1. Hogy állíthatom be, hogy a tartalomjegyzék csak két szint mély legyen?
Az `include/preamble.tex` fájlban a következő sort kell módosítani:

    \setcounter{tocdepth}{3}

A 0. szint a chapter, az 1. a section, a 2. pedig a subsection.

#### 2. A táblázataim / ábráim nagyon elmásznak a helyükről
Használd a `[htbp]` pozicionálást! A `[h!]` megpróbálja pont oda tenni, de ha ez lehetetlen, akkor feladja. A `[htbp]` megpróbálja oda tenni, aztán egy oldal tetejére, aljára, végül külön oldalra. Az eredmény sokkal jobb lesz. A pozícionálással érdemes a dokumentum elkészülte után foglalkozni.

    \begin{table}[htbp]

#### 3. Hogyan hivatkozzak máshonnan szerzett ábrákra?
A label belsejébe kell tenni a hivatkozást, ehhez azonban a `\protect` parancsra is szükség van.
    
    \label{A fluxuskondenzátor működése \protect\cite{DocJegyzetei}}

## Névjegy
Révész Levente  
levente.revesz@gmail.com


[thesis-template-latex]: https://github.com/FTSRG/thesis-template-latex
[GPK Útmutató]: https://www.gpk.bme.hu/images/gepeszkar/doku/Szabalyzatok/2015/6-melleklet(SZD&DT&ZV&SZGY_Szabalyzat)_Utmutato.pdf
[GPK Word sablon]: https://www.gpk.bme.hu/images/gepeszkar/doku/Szabalyzatok/2015/7-melleklet(SZD&DT&ZV&SZGY_Szabalyzat)_SZD_DT_forma_egyoldalas_HUN.docx
[`thesis.pdf`]: thesis.pdf
