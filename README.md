# 📘 Mon année BT

**Une appli gratuite et open source pour les élèves** : organiser son année scolaire, prendre ses cours en photo ou à la voix, et réviser avec une équipe d'intelligences artificielles.

Créée par **BAYILE Jean Daniel**, élève en BT Électronique à Abidjan 🇨🇮.

## ✨ Fonctions

**S'organiser**
- 🗓️ **Emploi du temps** importé depuis une simple photo (l'IA remplit tout).
- 📊 **Notes /20**, moyennes, note à viser au prochain devoir.
- 🔔 **Rappels** sur le téléphone, même appli fermée.
- 🧠 **Révision espacée**, objectifs, série de jours, bilan de la semaine, carte de ton année.

**Prendre ses cours**
- 📷 **En photo** : l'IA transcrit le texte. Les schémas sont découpés automatiquement, ou à la main au doigt (cadre réglable, pivot), ajustables à tout moment, et l'IA peut les redessiner proprement.
- 🎙️ **À la voix** : l'IA transcrit le prof toutes les 2 minutes.

**Réviser**
- 🧑‍🏫 **11 méthodes d'étude** : *comprendre* (prof particulier, explique avec tes mots, pas à pas, analogies, comparer), *retenir* (cartes mémoire, texte à trous, carte mentale, podcast), *s'évaluer* (questions ouvertes, vrai ou faux piégeux), plus une **séance guidée** de 25 min.
- ✅ **Correction de devoirs** par plusieurs IA qui se relisent.
- 🎧 **NotebookLM** : tu choisis les cours qu'il peut utiliser, l'appli les prépare (texte propre, sommaire, légendes des schémas), puis tu copies le texte ou envoies le fichier et tu lances une vidéo explicative ou un podcast en français. NotebookLM n'a pas de connexion pour les applis : l'envoi se fait à la main, avec seulement les cours que tu as choisis.
- ⚡ **Labo d'électronique** (sans internet) : loi d'Ohm, code couleur des résistances, série/parallèle, diviseur, circuit RC, binaire/hexa, portes logiques, plus deux jeux (Sprint 60 s et Paires).
- 🤖 **Volt**, un compagnon qui grandit avec ton niveau, et un « Le saviez-vous ? » chaque jour.

**Les intelligences artificielles**
- **Gemini** (gratuit) est l'IA par défaut : crée ta clé sur https://aistudio.google.com/apikey.
- 🧠 **Claude** en option : colle une clé API Claude dans *Réglages → Intelligence artificielle*. C'est un produit séparé de l'abonnement Claude, payant à l'usage (crédits à acheter sur console.anthropic.com). La voix (enregistrement des cours) reste confiée à Gemini.
- 🤝 **Équipe d'IA en missions** : un binôme principal (par ex. Claude ou Gemini + une IA spécialiste devoirs) et des renforts (Groq, Mistral, OpenRouter gratuits ; ChatGPT, Perplexity, DeepSeek…). Chaque travail est une mission : relecture croisée, erreurs corrigées, relais en cas de panne, classement avec MVP et « loser », banc après 3 échecs d'affilée.
- Les noms techniques des IA sont cachés par défaut.

**Une vraie appli**
- ✨ Écran de démarrage, bouton Retour du téléphone qui revient à l'écran d'avant (et ferme le menu), message hors connexion, « Annuler » après une suppression, barre du bas qui s'efface pendant qu'on écrit, taille du texte réglable, états vides accueillants.
- 🎨 Couleurs, fond, image, mode sombre, ou thème créé par l'IA. Icônes vectorielles sobres.
- 🔄 **Synchronisation complète** téléphone ↔ PC via Firebase : cours, photos, notes, planning, couleurs, rappels et IA (clés chiffrées avec ton code secret). Mise à jour automatique, sans écraser des données plus récentes.
- 🛡️ **Sauvegardes** cloud (30 versions) et copies automatiques sur l'appareil.

## 📥 Installer

Toutes les versions sont dans **[Releases](../../releases/latest)**.

| Appareil | Comment faire |
|---|---|
| 📱 **Android** | Télécharge **MonAnneeBT.apk** et ouvre-le. Si Android le demande, autorise « Installer des applis inconnues » pour ton navigateur. |
| 💻 **Windows** | Télécharge le fichier **Setup** (.exe) et lance-le. Si Windows affiche « Windows a protégé votre PC » : *Informations complémentaires* puis *Exécuter quand même* (l'appli n'a pas de signature payante). Une version **portable** (sans installation) est aussi proposée. |
| 🍎 **iPhone / iPad** | Pas d'APK sur iPhone. Ouvre la **version web** dans **Safari**, touche **Partager** puis **Sur l'écran d'accueil**. |
| 🖥️ **Mac, Linux, Chromebook** | Ouvre la **version web** dans Chrome ou Edge, puis clique sur l'icône d'installation dans la barre d'adresse. |

La **version web** est à l'adresse https://danielelectronsmart-web.github.io/monanneebt-app/ et marche aussi **sans internet** une fois ouverte.
Dans l'appli : **Réglages → Installer l'appli** donne ces étapes, adaptées à ton appareil, avec des boutons pour partager le lien à tes amis.

Au premier lancement, l'appli te guide : prénom, matières, emploi du temps, couleurs, clé IA.

### 🔄 Mettre à jour
1. Sur GitHub : **Code → Add file → Upload files**, glisse le nouvel `index.html` (même nom : il remplace l'ancien), puis **Commit changes**.
2. Attends le rond vert dans l'onglet **Actions** (10 à 15 minutes).
3. Installe le nouvel APK **par-dessus** l'ancien : tes données sont gardées.

### Activer la version web (une seule fois)
1. Sur GitHub, ouvre ton dépôt, puis **Settings → Pages**.
2. Dans **Source**, choisis **GitHub Actions**.
3. Relance **Actions → Construire APK et logiciel Windows → Run workflow** : l'adresse apparaît à l'étape « Mettre le site en ligne ».

Tant que les Pages ne sont pas activées, l'étape web échoue en silence : l'APK et le logiciel Windows sont construits normalement.

## 🛠️ Pour les développeurs

Toute l'appli tient dans **un seul fichier** : `index.html`.
À chaque envoi sur `main`, GitHub Actions (`.github/workflows/build.yml`) fabrique automatiquement l'APK Android (Capacitor), le logiciel Windows (Electron) et la version web, puis publie les deux premiers dans Releases. Les icônes viennent d'un script embarqué dans ce fichier.

Signature Android : ajoute la clé dans **Settings → Secrets and variables → Actions → `KEYSTORE_B64`** (contenu en base64 d'un keystore `androiddebugkey` / mot de passe `android`). Sans ce secret, l'APK est signé avec une clé temporaire et les mises à jour demandent de réinstaller.

Contributions bienvenues : ouvre une *issue* ou une *pull request* 🙌

## 📄 Licence

MIT : libre d'utiliser, modifier et partager.
