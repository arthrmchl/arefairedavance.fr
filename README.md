# arefairedavance.fr
[![Netlify Status](https://api.netlify.com/api/v1/badges/7994371a-80d0-4631-bfaa-79d0ad515065/deploy-status)](https://app.netlify.com/projects/arefairedavance/deploys)

Repository du site **à refaire d’avance**, un blog consacré à la critique culturelle : cinéma, jeux vidéo et podcast.

Le site est généré avec **Hugo** et utilise le thème **PaperMod**.
Le déploiement est automatisé via **Netlify** et publié sur le domaine :

https://arefairedavance.fr

---

# Présentation

**à refaire d’avance** est un blog personnel dédié à l’analyse critique de la culture populaire.

Les contenus publiés comprennent :

* critiques de films
* analyses de jeux vidéo
* essais culturels
* épisodes de podcast

Le site est construit comme un **site statique**, ce qui permet :

* des performances élevées
* une maintenance simple
* une surface d’attaque minimale (absence de backend)

---

# Stack technique

* **Static Site Generator** : Hugo (Extended)
* **Thème** : PaperMod
* **Recherche interne** : Fuse.js
* **Déploiement** : Netlify
* **Domaine** : arefairedavance.fr

---

# Architecture du projet

```text
.
├── archetypes/        # Modèles pour nouveaux contenus
├── content/           # Contenu du site
│   ├── articles/
│   └── podcast/
├── layouts/           # Templates Hugo personnalisés
├── static/            # Assets statiques
├── themes/            # Thème PaperMod (submodule Git)
├── hugo.yaml          # Configuration principale Hugo
└── README.md
```

---

# Installation

## Prérequis

* **Hugo Extended** ≥ 0.110
* Git

Installation possible via :

```bash
brew install hugo
```

ou

```bash
sudo apt install hugo
```

---

# Développement local

Cloner le repository :

```bash
git clone https://github.com/arthrmchl/arefairedavance.fr.git
cd arefairedavance.fr
```

Initialiser les submodules (thème) :

```bash
git submodule update --init --recursive
```

Démarrer le serveur de développement :

```bash
hugo server
```

Le site sera accessible à :

```
http://localhost:1313
```

Le serveur recharge automatiquement les pages lors des modifications.

---

# Génération du site

Pour générer la version statique :

```bash
hugo --minify
```

Les fichiers générés seront placés dans :

```
/public
```

Ce dossier est utilisé uniquement pour le build et **n’est pas versionné dans le dépôt**.

---

# Ajouter un article

Créer un nouvel article :

```bash
hugo new articles/mon-article.md
```

Exemple de frontmatter :

```yaml
title: "Titre de l’article"
date: 2026-01-01
summary: "Résumé court de l’article"
tags: ["cinéma"]
draft: true
```

Une fois l’article prêt à être publié :

```
draft: false
```

---

# Personnalisation du thème

Le thème **PaperMod** peut être surchargé via :

```
layouts/
```

Hugo utilise un mécanisme de **lookup order** permettant de remplacer
