# timatch-website — nur noch Umleitungen

Dieses Repo bediente `app.timatch.de` mit Hilfe, Support und den Rechtstexten. **Seit dem
23. August 2026 liegen diese Inhalte auf `timatch.de`** (Repo `jaimetabo/timatch-web`), im neuen
Design und unter sprechenden Adressen.

Hier stehen nur noch Umleitungen:

| alt | neu |
|---|---|
| `app.timatch.de/` | `timatch.de/` |
| `app.timatch.de/hilfe.html` | `timatch.de/hilfe/` |
| `app.timatch.de/support.html` | `timatch.de/en/support/` |
| `app.timatch.de/datenschutz.html` | `timatch.de/datenschutz/` |
| `app.timatch.de/privacy.html` | `timatch.de/en/privacy/` |

## Warum das hier nicht einfach gelöscht wird

Die alten Adressen stehen in **App Store Connect** und in **jeder bereits ausgelieferten Fassung
der App**. Eine veröffentlichte App kann man nicht zurückholen: Wer eine ältere Version behält,
tippt weiterhin auf `app.timatch.de/datenschutz.html`. Eine tote Adresse in einer Datenschutz-
Verlinkung ist schlimmer als eine Umleitung, die ewig steht.

**Dieses Repo bleibt bestehen, und der CNAME-Eintrag `app` bei STRATO bleibt bestehen.**

## Wie umgeleitet wird

GitHub Pages kann keine 301er schicken — es gibt keine Server-Konfiguration. Jede Seite trägt
deshalb:

- `<meta http-equiv="refresh" content="0; url=…">` — leitet den Browser um
- `<link rel="canonical" href="…">` — sagt Suchmaschinen, welche Adresse die richtige ist
- `<meta name="robots" content="noindex, follow">` — die alte Adresse soll aus dem Index
- einen sichtbaren Verweis, falls die Umleitung blockiert wird

Erzeugt hat sie `/tmp/umleitung.py`; der Inhalt ist so kurz, dass eine Änderung von Hand genügt.
