# RUNBOOK — nextcar-design-system (repo z assetami / design system)

Repo bez aplikacji: sam CSS, tokeny, opis stylu i statyczny podglad. Nie ma deployu ani sekretow.

## Podstawy
- Co to jest: design system strony nextcar.is (ciemny, jeden czerwony akcent, Barlow / Barlow Condensed), wyciagniety z produkcyjnego CSS 2026-09-20.
- Widocznosc repo: publiczne (sprawdzone `gh repo view`, 2026-10-05).
- Repo: github.com/kamiljan11/nextcar-design-system
- Wlasciciel: Kamil Jan.

## Jak uzywac
1. Claude Design: ustaw design system i wskaz to repo (albo wgraj `DESIGN.md`, `tokens/tokens.css`, `components/components.css`).
2. Zwykly projekt webowy: skopiuj `tokens/tokens.css` + `components/components.css`; dla Tailwind v4 dodatkowo `tokens/tailwind-theme.css`.
3. Podglad: `python3 -m http.server 8000` w katalogu repo, potem `/preview/index.html`.
4. Zrodlo prawdy dla decyzji (kolor, typografia, ksztalt, glos marki): `DESIGN.md`.

## Pochodzenie assetow
- Kolory, fonty, odstepy: wyciagniete z produkcyjnego CSS i computed styles strony nextcar.is (wrzesien 2026), wedlug README.
- `assets/logo.svg`: tekstowy wordmark (NEXT bialy, CAR czerwony, kursywa), zrobiony na potrzeby systemu, bez zewnetrznej grafiki.
- Zdjecia w `preview/index.html` NIE sa w repo: sa podlinkowane z nextcar.is/brand/. Zmiana lub usuniecie ich na stronie psuje podglad.
- Logotypy partnerow wymienione w `DESIGN.md` (marquee) nie sa w repo; to opis wygladu, nie pliki.

## Licencje
- Fonty Barlow i Barlow Condensed: ladowane z Google Fonts (`@import` w `tokens/tokens.css`). [DO UZUPELNIENIA przez Kamila: potwierdzic licencje obu fontow na stronie Google Fonts przed uzyciem w druku lub w materialach klienta]
- Ikony: opis wymaga stylu Lucide (linia, 1.5), ale ikony nie sa w repo. [DO UZUPELNIENIA przez Kamila: potwierdzic licencje Lucide przy ich uzyciu]
- Zdjecia na nextcar.is i logotypy partnerow: prawa nalezą do wlasciciela strony / producentow. [DO UZUPELNIENIA przez Kamila: czy wolno uzywac zdjec poza stroną nextcar.is]
- Licencja samego repo: brak pliku LICENSE. [DO UZUPELNIENIA przez Kamila: wybrac licencje, bo repo jest publiczne — domyslnie wszystkie prawa zastrzezone]

## Deploy i rollback
- Deploy: brak. Zmiana w `main` = nowa wersja dla kazdego, kto czyta repo.
- Rollback:
```bash
git revert <sha-zlego-commita> && git push
```
- Przypiecie wersji w projekcie konsumujacym: kopiuj pliki z konkretnego commita albo taga (`git archive <sha>`). Taguje sie reczenie (`git tag vX.Y.Z && git push --tags`), na razie zadnych tagow nie ma.

## Sekrety
- Brak. Repo nie uzywa zmiennych srodowiskowych ani kluczy. Nie dodawaj ich.

## Typowe problemy
| Objaw | Pierwszy krok |
|---|---|
| Podglad bez zdjec lub fontow | Sprawdz internet; zdjecia lecą z nextcar.is/brand/, fonty z Google Fonts |
| Czerwony tekst nieczytelny na ciemnym | Uzyj `--nc-primary-text` (#e24942) do tekstu, `--nc-primary` (#c9302d) tylko do wypelnien |
| Kolor rozjechal sie miedzy plikami | Ta sama wartosc jest w `tokens.css`, `tokens.json`, `tailwind-theme.css` — popraw wszystkie trzy |
| Strona nextcar.is zmienila wyglad | Zaktualizuj `tokens/`, potem `components/`, potem `DESIGN.md`, dopisz CHANGELOG |

## Kontakty
- Wlasciciel: Kamil Jan.
