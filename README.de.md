# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt-BR.md) · [Italiano](README.it.md)**

Eine macOS-Menüleisten-App, die das Ruhezustandsverhalten des MacBook mit zwei unabhängigen Schaltern steuert – hält deinen Mac bei geschlossenem Deckel wach und blockiert den durch Inaktivität ausgelösten Ruhezustand während der Arbeit.

> 📦 **Dieses Repository verteilt nur die signierte und notarisierte `.dmg`-Datei. Der Quellcode liegt in einem privaten Repository.**

## ⬇️ Download

Neueste Version → **[KeepAwake-releases/releases/latest](../../releases/latest)**

Jede `.dmg` ist mit der Developer ID `C3SNXE45AV (Xiaoneng Wu)` signiert und von Apple notarisiert. macOS Gatekeeper akzeptiert sie ohne den zweiten „aus dem Internet geladen"-Bestätigungsdialog.

## 🧰 Systemanforderungen

- macOS 14 Sonoma oder neuer
- Apple Silicon oder Intel

## ✨ Funktionen

- **Wach bei geschlossenem Deckel** — Mac läuft weiter, auch wenn der Deckel geschlossen ist (einmalige Administrator-Autorisierung erforderlich)
- **Inaktivitäts-Ruhezustand verhindern** — unterdrückt den durch Inaktivität ausgelösten Ruhezustand, während KeepAwake läuft (IOKit assertion)
- **Automatischer Ausschalt-Timer** — 30 Min / 1 / 2 / 4 / 8 Stunden
- **Autostart beim Anmelden, letzten Zustand merken, Schalter beim Beenden automatisch zurücksetzen**
- **Absturzsicher** — wenn die App abstürzt, setzt der Helper `disablesleep` nach 60 s automatisch auf 0 zurück
- **15 Sprachen** — folgt der macOS-Systemsprache

## 📥 Installation

1. Lade `KeepAwake-0.2.0.dmg` aus der [neuesten Version](../../releases/latest) herunter
2. Doppelklicke auf die DMG zum Einbinden, ziehe **KeepAwake.app** nach `/Applications`
3. Starte aus dem Launchpad oder dem Programme-Ordner
4. Beim ersten Aktivieren von „Wach bei geschlossenem Deckel" fragt macOS nach Erlaubnis, ein Hintergrundobjekt hinzuzufügen → klicke auf **Erlauben**

## 🔐 Signatur und Notarisierung

- Developer ID: `Xiaoneng Wu (C3SNXE45AV)`
- Apple Notary Service: ✅ Akzeptiert
- Geheftetes Ticket (funktioniert offline, Gatekeeper kann ohne Netzwerk verifizieren)

## ⚠️ Überhitzungsrisiko bei geschlossenem Deckel — bitte lesen

**Die Haupt-Lüftungsöffnung des MacBook liegt unter der Tastatur.** Wenn der Deckel geschlossen ist und der Laptop flach auf einer Oberfläche liegt, wird der Luftstrom eingeschränkt. Intensive Arbeitslasten in diesem Zustand (Videoexport, Kompilieren, ML-Training, lange KI-Inferenz, Spiele) können verursachen:

- CPU/GPU Thermal Throttling → deine Aufgabe wird tatsächlich *langsamer*
- Beschleunigte Batteriealterung durch längere hohe Temperaturen
- Im Extremfall thermische Abschaltung oder Hardware-Schäden

**Sicherer Einsatz:**

- ✅ Geeignet für **leichte** Hintergrundaufgaben — Dateisynchronisation, Downloads, SSH / Remote-Desktop aufrecht halten, AirPlay-Empfang
- ⚠️ Bei **intensiven** Arbeitslasten mit geschlossenem Deckel stelle den Laptop auf oder benutze einen Kühlständer. Lege ihn **niemals** auf ein Bett, eine Decke, ein Sofa oder in eine Tasche.
- ❌ Kombiniere nicht „Deckel geschlossen + hohe Last + blockierte Lüftungsöffnungen"

`Inaktivitäts-Ruhezustand verhindern` überschreibt ebenfalls das Akkusparverhalten. Schalte es ein, wenn du es brauchst, und aus, wenn du es nicht mehr brauchst.

**KeepAwake überwacht weder Temperatur noch Last. Risikomanagement liegt bei dir.**

## 🔒 Über den Quellcode

Das Quell-Repository ist privat. Dieses Repository existiert nur zur Verteilung der signierten und notarisierten DMG. Wenn du Codezugriff für ein Audit oder einen Beitrag benötigst, kontaktiere den Autor.

## Lizenz

Privatnutzung.
