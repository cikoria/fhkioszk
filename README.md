# fhkioszk
Egyszerű kioszk a Futball házba

## Általános leírás

## Tartalomjegyzék

- [Általános leírás](#általános-leírás)
- [Felületek](#felületek)
  - [Központi képernyő](#központi-képernyő)
  - [Információs rendszer](#információs-rendszer)
  - [Kvíz](#kvíz)
    - [Kvíz felület](#kvíz-felület)
    - [Kvíz admin](#kvíz-admin)
- [Általános adminisztráció](#általános-adminisztráció)
- [Környezet](#környezet)

## Felületek
### Központi képernyő
Az eszköz **kioszk módban** indul, vagyis a teljes felületet egyetlen böngészőablak teszi ki.
A felhasználónak a központi képernyőn lehetősége van választani, hogy a Futball ház információs rendszerét, vagy a kvízalkalmazást indítja el.

A központi képernyő szerkezete egyszerű:
- a képernyő közepén a két választási lehetőség megjelenítése.

### Információs rendszer
A felület **minden oldalán** lehetőséget biztosít a közonti képernyőre való visszatérésre.

#### Felület
#### Admin

### Kvíz
**[Phase 1]**

- A kvíz több **nehézségi szintet** támogat: gyerek (nem tud olvasni), iskolás, felnőtt, Kispest-tudós.
- A kvíz több **hosszúságot** támogat: a felhasználó a kvíz indításakor dönti el, hogy hány kérdést szeretne kapni. Itt majd kísérletezni kell az idővel, de a rövid (10), közepes (20) és hosszú (30) valószínáleg elég lesz. A gyerek szinten mindenképp 5-10 kérdés van, mert ott szükség van a kísérő segítségére, és sok kérdésnél a gyerekek elunnák magukat.
  - A kérdések adatbázisból érkeznek, véletlenszerűen. Ennek alapfeltétele, hogy az adatbázisban a kérdések tartalmazzanak egy **nehézség-jelölőt**, ami mentén leválogatja a megjelenítő kérdéseket.
- A kvíz egyetlen **kérdéstípust** támogat: feleletválasztós, 2 vagy 4 lehetséges válasszal.
  - kétféle feleletválasztós mód: csak szöveges, csak kép (ilyenkor a kérdés ugyanúgy szöveges).
  - a gyerek nehézségi szinten 2 lehetséges válasz van, és a válaszok képek, hogy a gyerek dönthessen (praktikusan ilyenkor a kísérő olvassa fel a kérdést, amit a gyerek dönt el).
  - a felhasználó - kérdéstípustól függően - a válasz szövegére vagy a képére koppintással dönt.
  - **#TODO** a továbblépésnek két lehetséges módja van, erről **dönteni kell**
      1. kell megerősítés a döntést követően (tovább gomb).
      2. nem kell megerősítés.
- A kvíz végén **kiértékelés** van.
 
#### Kvíz felület
- A kvíz indító felülete egy **üdvözlő képernyő**, ahol kilistázásra kerülnek a nehézségi szintek. A felhasználók egy nehézségi szintre koppintással dönti el, hogy melyik kvízt szeretné kitölteni.
- A **második oldalon**, **amennyiben nem** a gyerek nehézségi szintent választotta, kilistázásra kerülnek a kvízek hosszúságai. A felhasználó koppintással dönt. Ezt követően indul a kvíz.
- A **kvízkérdések oldalai**:
  - Indikátor, ahol a felhasználó láthatja, hogy hány kérdésnél tart, valamint az összes kérdések száma. **#TODO** a helyes válaszok számolása kvíz közben **döntést igényel**.
  - Szöveges kérdés esetén:
    - Kérdés.
    - A lehetséges válaszok. A felhasználó az egyik **szövegre koppintással** dönti el, hogy szerinte melyik a helyes.
  - Képes kérdés esetén:
    - Kérdés.
    - A lehetséges válaszok képei. A felhasználó az egyik **képre koppintással** dönti el, hogy szerinte melyik a helyes.
- **Kiértékelő oldal**:
  - A felhasználó megtudja a helyes válaszainak számát, illetve az összes kérdés számát.
  - Az elért pontszám arányában véletlenszerű üzenetet kap.
  - Visszatérés gomb az üdvözlő képernyőre.
- A kvíz az első oldal, vagyis az üdvözlő képernyő kivételével **bármikor megszakítható** a főképernyőre visszatéréssel. Ehhez egy jól látható gombnak kell lennie a képernyőn. Amennyiben a felhasználó már egy kérdést tartalmazó oldalon van, megerősítő felület jelenik meg: kilépek/folytatom. A kilépekre koppintás esetén visszatér az üdvözlő képernyőre.
 
**[Phase 2]**

- [ ] Újabb kérdéstípusok.
- [ ] Toplista nehézségi szintenként.

A felület **minden oldalán** lehetőséget biztosít a közonti képernyőre való visszatérésre.

#### Kvíz admin
**[Phase 1]**

Az admin felületnek nem szükséges autentikáció.

A kvíz adatbázisból dolgozik. Az admin felületnek a következőket kell támogatnia:
- **nehézségi szint létrehozása** -> esetünkben a nehézségi szint egyenlő az önálló kvízzel. Alapértelmezésben négy kategória van: gyerek (nem tud olvasni), iskolás, felnőtt, Kispest-tudós, azonban lehet újakat létrehozni.
  1. nehézségi szint neve: szöveges mező
  2. lehetséges válaszok számának meghatározása: 2/4
- **nehézségi szintek listázása, szerkesztése, törlése**
  1. az elérhető nehézségi szintek egy listában jelennek meg.
  2. a lista oszlopai: id, nehézségi szint megnevezése, válaszok száma, szerkesztés, törlés.
  3. a szerkesztés gombra kattintva a **nehézségi szint létrehozása** oldal jelenik meg, és a nehézségi szint szerkeszthető.
  4. a törlés gombra kattinva megerősítő ablak felület meg: igen/nem.
     - igen válasz esetén a felhasználónak döntenie kell, hogy a nehézségi szinthez tartozó kérdéseket a rendszer melyik másik nehézségi szinthez rendelje hozzá, vagy hagyja nehézségi szint nélkül.
     - a törlés csak ezt követően valósul meg.
- **új kérdés felvitele** ->
  1. kérdés beírása: szöveges mező
  2. kérdés típusa: szöveg/kép
  3. válaszok megadása: négy szöveges mező/négy filefelöltési lehetőség. Képes válasz esetén a képek megjelennek bélyegkép méretben, cseréjük a feltöltés gomb ismételt megnyomásával lehetséges.
  4. helyes válasz megadása: négy gomb
  5. nehézségi szint megadása: gombként kilistáva az ismert nehézségi szintek -> **!** egy kérdéshez több nehézségi szint is tartozhat, vagy egy sem!
  6. a kérdés aktív: igen/nem -> nem esetén a rendszer nem veszi figyelembe a kérdést a kvízek létrehozásakor.
- **kérdések listázása, szerkesztése, törlése**
  1. az elérhető kérdések egy listában jelennek meg.
  2. a csoportos műveletek nem képezik a **[Phase 1]** részét.
  3. a lista oszlopai: id, kérdés, típus, válaszok száma, nehézségi szint(ek), aktív, szerkesztés, törlés
  4. a szerkesztés gombra kattinva az **új kérdés felvitele** oldal jelenik meg, és a kérdés szerkeszthető.
  5. a törlés gombra kattintva megerősítő felölet jelenik meg: igen/nem
- **kiértékelő üzenenet létrehozása**
  - Adott sávhatáronként, a teljesítményétől függően más és más kiértékelő üzenertet kap a felhasználó.
    - 25% alatt: szöveges mező.
    - 26-50% között: szöveges mező.
    - 51-75% között: szöveges mező.
    - 75% fölött: szöveges mező.
 
**[Phase 2]**

- [ ] Kérdések importálása nehézségi szint létrehozásakor más nehézségi szintekből.
- [ ] Többféle kiértékelő üzenet, a **kiértékelő üzenetek listázása, szerkesztése, törlése** felület, valamint a sávhatárok beállításának lehetősége.

## Általános adminisztráció
Mivel az eszköz kioszk módban indul, ezért **szükség** van a távoli menedzsmentre. Az eszköz rendelkezik internetes kapcsolattal.

## Környezet
*2025. február 12-i állapot szerint.*

- Raspberry Pi4 / 4Gb - Raspberry Pi OS (64-bit) Debian version: 12 (bookworm)
- Asus VT168HR érintőképernyős monitor
- hang: nincs (hangfal szükséges)
