# SüdEnergie Heizlastrechner

Verkaufs-/Planungstool, das die Gebäude-**Heizlast** über zwei unabhängige Methoden
überschlägig ermittelt und gegeneinander plausibilisiert. Mobil-/Tablet-first,
Dashboard-Look (analog zum Wirtschaftlichkeitsrechner).

> **Disclaimer:** Orientierung für Angebot und Vorplanung. Verbindlich ist die
> raumweise Heizlastberechnung nach **DIN EN 12831** durch eine Fachkraft –
> Voraussetzung für BAFA/BEG-Förderung.

## Methoden

- **A · Fläche** – Prozentverfahren: spezifische Heizlast (W/m²) je Baujahr-Klasse,
  abzüglich Sanierungen (Fenster −10 %, Dach −15 %, Fassade −20 %, max. 45 %),
  oder fester Wert 50 W/m² bei „vollständig saniert“. Optionaler Anbau wird addiert.
- **B · Verbrauch** – Vollbenutzungsstunden: `Heizlast = (Verbrauch_kWh × 0,90) ÷ Vbh`.

Beide Methoden laufen **live** (kein Submit). Bei Abweichung > 20 % erscheint eine
Warnung mit den häufigsten Ursachen (z. B. Kachelofen/Zusatzheizung).

## Tech

Single-File-App: [`index.html`](index.html) (Vanilla JS, inline CSS/JS),
optional PWA (`manifest.json`, `sw.js`). Kein Backend, reine Frontend-Rechnung.

## Lokal starten

Einfach `index.html` im Browser öffnen. Für PWA/Service-Worker über einen
lokalen Server ausliefern, z. B.:

```bash
python -m http.server 8080
```

## Deploy

Vorgesehen für **GitHub Pages** (Repo `suedenergie-heizlast` unter `suedenergie-pv`),
einbettbar auf der PV-Seite/Blog.

## Hinweis

Das Logo `suedenergie-logo.png` ergänzen (Header + PWA-Icon). Fehlt es, zeigt der
Header einen Text-Fallback „SüdEnergie“.
