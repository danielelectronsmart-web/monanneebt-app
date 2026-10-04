# 📘 Mon année BT

**Une appli gratuite et open source pour les élèves** : organiser son année scolaire, prendre ses cours en photo ou à la voix, et réviser avec une équipe d'intelligences artificielles.

Créée par **BAYILE Jean Daniel**, élève en BT Électronique à Abidjan 🇨🇮.

## ✨ Fonctions

- 🗓️ **Emploi du temps** : importé depuis une simple photo (l'IA remplit tout).
- 📷 **Cours en photo** : l'IA transcrit le texte. Les schémas sont découpés automatiquement, ou à la main au doigt (cadre réglable, pivot), ajustables à tout moment, et l'IA peut les redessiner proprement.
- 🎙️ **Cours enregistré** : l'IA transcrit la voix du prof toutes les 2 minutes.
- 🧑‍🏫 **Étudier avec l'IA**, 11 méthodes par catégorie : *comprendre* (prof particulier, explique avec tes mots, pas à pas, analogies, comparer), *retenir* (cartes mémoire, texte à trous, carte mentale, podcast), *s'évaluer* (questions ouvertes, vrai ou faux piégeux), plus une **séance guidée** de 25 min.
- ✅ **Correction de devoirs** : plusieurs IA corrigent, comparent et se relisent.
- 🤝 **Équipe d'IA en missions** : un binôme principal (Gemini + une IA spécialiste devoirs) et des renforts. Chaque travail est une mission : relecture croisée, erreurs corrigées, relais en cas de panne, classement avec MVP et « loser », banc après 3 échecs d'affilée.
- 🤖 **Équipe d'IA** : Gemini (gratuit) + Groq, Mistral, OpenRouter (gratuits) + ChatGPT, Claude, Perplexity…
- 🧠 **Révision espacée**, objectifs, série de jours, bilan de la semaine.
- 🔔 **Rappels** sur le téléphone, même appli fermée.
- 📊 **Notes /20** et moyennes.
- 🎨 **Couleurs, fond, image** personnalisables, ou thème créé par l'IA.
- ⚡ **Labo d'électronique** (sans internet) : loi d'Ohm, code couleur des résistances, série/parallèle, diviseur, circuit RC, binaire/hexa, portes logiques, plus deux jeux (Sprint 60 s et Paires). **Volt**, un compagnon qui grandit avec ton niveau, et un « Le saviez-vous ? » chaque jour.
- 🔄 **Synchronisation complète** téléphone ↔ PC via Firebase : cours, photos, notes, planning, couleurs, rappels et IA (clés chiffrées avec ton code secret). Mise à jour automatique, sans écraser des données plus récentes.
- 🛡️ **Sauvegardes** cloud (30 versions) et copies automatiques sur l'appareil.
- ⚖️ **IA Gratuite ou Premium** : une clé gratuite suffit ; les IA payantes se branchent en option. Les noms techniques sont cachés par défaut.
- 🧩 **Icônes** vectorielles sobres, qui suivent tes couleurs et le mode sombre.

## 📥 Installer

| Appareil | Comment faire |
|---|---|
| 📱 **Android** | Ouvre la page **Releases** du dépôt, télécharge **MonAnneeBT.apk**, ouvre-le. Si Android le demande, autorise « Installer des applis inconnues » pour ton navigateur. Pour une **mise à jour**, installe le nouvel APK **par-dessus** : tes données sont gardées. |
| 💻 **Windows** | Sur la même page, télécharge le fichier **Setup** (.exe) et lance-le. Si Windows affiche « Windows a protégé votre PC » : *Informations complémentaires* puis *Exécuter quand même* (l'appli n'a pas de signature payante). Une version **portable** (sans installation) est aussi proposée. |
| 🍎 **iPhone / iPad** | Pas d'APK sur iPhone. Ouvre la **version web** dans **Safari**, touche **Partager** puis **Sur l'écran d'accueil**. |
| 🖥️ **Mac, Linux, Chromebook** | Ouvre la **version web** dans Chrome ou Edge, puis clique sur l'icône d'installation dans la barre d'adresse. |

La **version web** est à l'adresse `https://TON-COMPTE.github.io/NOM-DU-DEPOT/` et marche aussi **sans internet** une fois ouverte.
Dans l'appli : **Réglages → Installer l'appli** donne ces étapes, adaptées à ton appareil, avec des boutons pour partager le lien à tes amis.

Au premier lancement, l'appli te guide : profil, matières, emploi du temps, couleurs, clé IA gratuite.

L'IA de base est **Google Gemini** : crée ta clé gratuite sur https://aistudio.google.com/apikey.

### Activer la version web (une seule fois)
1. Sur GitHub, ouvre ton dépôt, puis **Settings → Pages**.
2. Dans **Source**, choisis **GitHub Actions**.
3. Envoie un nouveau fichier (ou relance **Actions → Construire APK et logiciel Windows → Run workflow**) : l'adresse apparaît dans l'onglet **Actions**, à l'étape « Mettre le site en ligne ».

Tant que les Pages ne sont pas activées, l'étape web échoue en silence : l'APK et le logiciel Windows sont construits normalement.

## 🛠️ Pour les développeurs

Toute l'appli tient dans **un seul fichier** : `index.html`.
À chaque envoi sur `main`, GitHub Actions (`.github/workflows/`) fabrique automatiquement l'APK Android (Capacitor) et le logiciel Windows (Electron), puis les publie dans Releases.

Signature Android : ajoute la clé dans **Settings → Secrets and variables → Actions → `KEYSTORE_B64`** (contenu en base64 d'un keystore `androiddebugkey` / mot de passe `android`). Sans ce secret, l'APK est signé avec une clé temporaire.

Contributions bienvenues : ouvre une *issue* ou une *pull request* 🙌

## 📄 Licence

MIT : libre d'utiliser, modifier et partager.
