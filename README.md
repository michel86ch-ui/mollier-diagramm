# Mollier h-x Diagramm

Interaktives Psychrometrie-Werkzeug fuer feuchte Luft im Browser.
Live: https://michel86ch-ui.github.io/mollier-diagramm/

## Ansichten

- **Einfach** â€“ ein Punkt. Temperatur, Absolutfeuchte und relative Feuchte haengen
  zusammen: die zwei zuletzt angefassten Werte bleiben **fix**, der dritte wird
  **berechnet** und laeuft mit. Absolutfeuchte wahlweise als Wassergehalt *x*
  [g/kg trockene Luft] oder als *rho_w* [g/m^3]. Klick ins Diagramm setzt
  Temperatur und Absolutfeuchte direkt.
- **T-x Diagramm** â€“ bis zu 5 Punkte, Temperatur ueber Wassergehalt.
- **h-x Diagramm (Mollier)** â€“ schiefwinkliges Original-Koordinatensystem
  (eta = h - 2501*x), Isotherme 0 degC horizontal, Isenthalpen fallend.

## Berechnung

- Saettigungsdruck nach Magnus (WMO 2018): p_s = 611.2 * exp(17.67*T/(T+243.5)) Pa
- Wassergehalt: x = 0.62198 * p_v / (p - p_v)
- Enthalpie: h = 1.006*T + x*(2501 + 1.860*T) kJ/kg
- Absolutfeuchte: rho_w = p_v / (R_w * T_K), R_w = 461.52 J/(kg*K)
- Feuchtkugel iterativ ueber die Psychrometergleichung
- Luftdruck frei einstellbar (Standard 101 325 Pa)

Referenzpunkt 20 degC / 50 % / 101 325 Pa: x = 7.26 g/kg, Taupunkt 9.27 degC,
Feuchtkugel 13.80 degC, h = 38.54 kJ/kg, rho_w = 8.64 g/m^3.

Einzelne HTML-Datei, keine Abhaengigkeiten.