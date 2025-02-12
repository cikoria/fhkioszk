# fhkioszk
Egyszerű kioszk a Futball házba

## Általános leírás

## Tartalomjegyzék

- [Általános leírás](#általános-leírás)
- [Felületek](#felületek)
  - [Központi felület](#központi-felület)
  - [Információs rendszer](#információs-rendszer)
  - [Kvíz](#kvíz)
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
#### Felület
**Phase 1**
- A kvíz több **nehézségi szintet** támogat: gyerek (nem tud olvasni), iskolás, felnőtt, Kispest-tudós.
- A kvíz több **hosszúságot** támogat: a felhasználó a kvíz indításakor dönti el, hogy hány kérdést szeretne kapni. Itt majd kísérletezni kell az idővel, de a rövid (10), közepes (20) és hosszú (30) valószínáleg elég lesz. A gyerek szinten mindenképp 5-10 kérdés van, mert ott szükség van a kísérő segítségére, és sok kérdésnél a gyerekek elunnák magukat.
  - A kérdések adatbázisból érkeznek, véletlenszerűen. Ennek alapfeltétele, hogy az adatbázisban a kérdések tartalmazzanak egy **nehézség-jelölőt**, ami mentén leválogatja a megjelenítő kérdéseket.
- A kvíz egyetlen **kérdéstípust** támogat: feleletválasztós, 2 vagy 4 lehetséges válasszal.
  - kétféle feleletválasztós mód: csak szöveges, csak kép (ilyenkor a kérdés ugyanúgy szöveges)
  - a gyerek nehézségi szinten 2 lehetséges válasz van, és a válaszok képek, hogy a gyerek dönthessen (praktikusan ilyenkor a kísérő olvassa fel a kérdést, amit a gyerek dönt el).
- A kvíz végén **kiértékelés** van.
  - A felhasználó megtudja a helyes válaszainak számát, illetve az összes kérdés számát.
  - Az elért pontszám arányában véletlenszerű üzenetet kap. 25% alatt, 26-50%, 51-75% között és 75% fölött más-más az üzenet.
 
**Phase 2**
- Újabb kérdéstípusok.
- Toplista

A felület **minden oldalán** lehetőséget biztosít a közonti képernyőre való visszatérésre.

#### Admin
- 

## Általános adminisztráció
Mivel az eszköz kioszk módban indul, ezért **szükség** van a távoli menedzsmentre. Az eszköz rendelkezik internetes kapcsolattal.

## Környezet
*2025. február 12-i állapot szerint.*

- Raspberry Pi4 / 4Gb - Raspberry Pi OS (64-bit) Debian version: 12 (bookworm)
- Asus VT168HR érintőképernyős monitor
- hang: nincs (hangfal szükséges)
