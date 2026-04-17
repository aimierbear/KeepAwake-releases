# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt-BR.md) · [Italiano](README.it.md)**

Une app pour la barre de menus macOS qui contrôle le comportement de mise en veille du MacBook avec deux interrupteurs indépendants : garder votre Mac éveillé capot fermé, et bloquer la mise en veille par inactivité pendant que vous travaillez.

> 📦 **Ce dépôt ne distribue que le `.dmg` signé et notarisé. Le code source se trouve dans un dépôt privé.**

## ⬇️ Téléchargement

Dernière version → **[KeepAwake-releases/releases/latest](../../releases/latest)**

Chaque `.dmg` est signé avec le Developer ID `C3SNXE45AV (Xiaoneng Wu)` et notarisé par Apple. Gatekeeper de macOS l'accepte sans afficher la boîte de dialogue de confirmation « téléchargé depuis internet ».

## 🧰 Configuration requise

- macOS 14 Sonoma ou supérieur
- Apple Silicon ou Intel

## ✨ Fonctionnalités

- **Éveillé capot fermé** — garde le Mac en fonctionnement même avec le capot fermé (autorisation administrateur requise la première fois)
- **Empêcher la veille d'inactivité** — supprime la mise en veille par inactivité pendant que KeepAwake fonctionne (IOKit assertion)
- **Minuteur d'arrêt automatique** — 30 min / 1 / 2 / 4 / 8 heures
- **Démarrage automatique à la connexion, mémorisation du dernier état, réinitialisation automatique des interrupteurs à la fermeture**
- **Résilient aux plantages** — si l'app se ferme inopinément, le helper remet `disablesleep` à 0 après 60 s
- **15 langues** — suit la langue du système macOS

## 📥 Installation

1. Téléchargez `KeepAwake-0.3.0.dmg` depuis la [dernière version](../../releases/latest)
2. Double-cliquez sur le DMG pour le monter, faites glisser **KeepAwake.app** dans `/Applications`
3. Lancez depuis Launchpad ou Applications
4. La première fois que vous activez « Éveillé capot fermé », macOS demandera l'autorisation d'ajouter un élément en arrière-plan → cliquez sur **Autoriser**

## 🔐 Signature et notarisation

- Developer ID : `Xiaoneng Wu (C3SNXE45AV)`
- Service de notarisation Apple : ✅ Accepté
- Ticket agrafé (fonctionne hors ligne, Gatekeeper peut vérifier sans réseau)

## ⚠️ Risque de surchauffe capot fermé — à lire absolument

**L'aération principale du MacBook se situe sous le clavier.** Lorsque le capot est fermé et l'ordinateur portable posé à plat sur une surface, le flux d'air est restreint. Exécuter des charges lourdes dans cet état (exports vidéo, compilations, entraînement ML, inférence IA prolongée, jeux) peut provoquer :

- Thermal throttling CPU/GPU → votre tâche devient en réalité *plus lente*
- Usure accélérée de la batterie due à des températures élevées prolongées
- Dans les cas extrêmes, arrêt thermique ou dommage matériel

**Usage sûr :**

- ✅ Adapté aux tâches **légères** en arrière-plan — synchronisation de fichiers, téléchargements, maintien de SSH / bureau à distance, réception AirPlay
- ⚠️ Pour les charges **lourdes** capot fermé, surélevez l'ordinateur ou utilisez un support ventilé. **Ne jamais** le placer sur un lit, une couverture, un canapé, ou dans un sac.
- ❌ Ne combinez pas « capot fermé + charge lourde + aérations bloquées »

`Empêcher la veille d'inactivité` annule aussi l'économie de batterie. Activez-le quand vous en avez besoin, désactivez-le quand c'est fini.

**KeepAwake ne surveille pas la température ni la charge. La gestion des risques vous revient.**

### 🌡️ Nouveauté v0.3 : Protection thermique passive (activée par défaut)

Lorsque « Éveillé capot fermé » est activé, KeepAwake surveille l'état thermique du système (`NSProcessInfo.thermalState`) :

- `Serious` pendant 60 s → désactive automatiquement « Éveillé capot fermé » pour que le système puisse se mettre en veille et refroidir
- `Critical` → désactivation immédiate

Lors du déclenchement, une notification est affichée et une bannière d'avertissement apparaît en haut du menu. Vous pouvez la désactiver dans les préférences du menu (« Protection thermique capot fermé »), mais **ce n'est pas recommandé**.

**Rappel : une protection logicielle passive ne remplace pas un refroidissement physique.** Évitez toujours « capot fermé + charge lourde + aérations bloquées ».

## 🔒 À propos du code source

Le dépôt source est privé. Ce dépôt n'existe que pour distribuer le DMG signé et notarisé. Si vous avez besoin d'accéder au code pour un audit ou une contribution, contactez l'auteur.

## Licence

Usage personnel.
