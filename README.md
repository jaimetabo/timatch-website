> # ⛔️ STILLGELEGT — dieses Repo wird nicht mehr benutzt
>
> **Stand 6. September 2026.** `app.timatch.de` zeigt **nicht mehr hierher**. Die Weiterleitung
> macht seitdem STRATO selbst: eine Subdomain im Domainpaket TIMATCH (7070811) mit „Umleitung
> Extern" auf `https://timatch.de/`. Der CNAME-Eintrag `app → jaimetabo.github.io` ist entfernt.
>
> **Hier ist nichts mehr zu tun.** Änderungen an der Website gehören nach
> [`jaimetabo/timatch-web`](https://github.com/jaimetabo/timatch-web) — dort liegt seit dem
> 23. August 2026 alles: Landingpage, Hilfe, Rechtstexte. Auch die vier Auffangseiten für die
> alten `.html`-Adressen liegen dort im Wurzelverzeichnis, weil die STRATO-Umleitung den Pfad
> beibehält.
>
> Das Repo ist **archiviert** und bleibt als Beleg stehen. Es zu löschen bringt nichts und nimmt
> die Historie mit.

---

# timatch-website — stillgelegt

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

## Warum es damals hierblieb — und warum das nicht mehr galt

Die Begründung lautete: Die alten Adressen stünden in App Store Connect und in jeder bereits
ausgelieferten Fassung der App, und eine veröffentlichte App könne man nicht zurückholen.

**Der zweite Teil stimmte nicht.** Die App war am 6. September 2026 nur in TestFlight, nicht im
Store — es gab also gar keine ausgelieferte Fassung, die man nicht mehr erreichen könnte. App
Store Connect war zu dem Zeitpunkt längst auf `timatch.de` umgestellt. Damit fiel der Grund weg,
für fünf Weiterleitungsseiten ein eigenes Repository zu betreiben.

## Wie umgeleitet wird

GitHub Pages kann keine 301er schicken — es gibt keine Server-Konfiguration. Jede Seite trägt
deshalb:

- `<meta http-equiv="refresh" content="0; url=…">` — leitet den Browser um
- `<link rel="canonical" href="…">` — sagt Suchmaschinen, welche Adresse die richtige ist
- `<meta name="robots" content="noindex, follow">` — die alte Adresse soll aus dem Index
- einen sichtbaren Verweis, falls die Umleitung blockiert wird

Erzeugt hat sie `/tmp/umleitung.py`; der Inhalt ist so kurz, dass eine Änderung von Hand genügt.
