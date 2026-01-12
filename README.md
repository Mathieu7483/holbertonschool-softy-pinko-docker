<p align="center"\>
<img src="https://github.com/Mathieu7483/Aiko78-Photgraphy/blob/main/img/cr---moi-une-page-de-garde-pour-un-projet--docker-.png"\>
</p>

# Softy Pinko - Docker Infrastructure

## 📝 Description

Ce projet porte sur la conteneurisation et l'orchestration d'une infrastructure logicielle complète à l'aide de **Docker** et **Docker Compose**.

L'objectif est de déployer une architecture robuste et scalable comprenant :

1. Un **Proxy Inverse (Reverse Proxy)** faisant office de point d'entrée unique.
2. Un **Répartiteur de charge (Load Balancer)** utilisant l'algorithme *Round Robin*.
3. Deux **serveurs API (Back-end)** pour traiter les requêtes dynamiques.
4. Un **serveur Front-end** dédié au contenu statique.

Cette approche garantit l'isolation des environnements, la portabilité de l'application et une gestion simplifiée des dépendances.

## 🛠️ Contenu du projet

Le dépôt est structuré par tâches, suivant l'évolution de la construction de l'infrastructure :

| Tâche | Dossier / Fichier | Description |
| --- | --- | --- |
| **0** | `task0/Dockerfile` | Création d'une image de base Ubuntu mise à jour affichant "Hello, World!". |
| **1** | `task1/` | Configuration et conteneurisation du service **Back-end** (Python/Flask ou Node.js selon l'implémentation). |
| **2** | `task2/` | Configuration et conteneurisation du service **Front-end** (serveur de fichiers statiques). |
| **3** | `task3/` | Mise en réseau des conteneurs Front-end et Back-end pour permettre la communication interne. |
| **4** | `docker-compose.yml` | Orchestration multi-conteneurs pour lancer l'ensemble des services avec une seule commande. |
| **5** | `proxy/` | Configuration de **Nginx** en tant que Reverse Proxy pour router le trafic vers le bon service. |
| **6** | `Scale` | Mise en place de la haute disponibilité en dupliquant les serveurs API via Docker Compose. |

## 🏗️ Prérequis

Pour déployer cette infrastructure, les outils suivants sont indispensables :

* **Docker Desktop** (version 4.x ou supérieure recommandée).
* **Docker Engine** (version 20.10.x+).
* **Docker Compose** (version 2.x+).
* **OS :** Ubuntu 20.04 LTS (pour la compatibilité des scripts et images).

## 🚀 Installation et Déploiement

### 1. Construction d'une image spécifique (Exemple Tâche 0)

```bash
cd task0
docker build -t softy-pinko:task0 .
docker run -it --rm softy-pinko:task0

```

### 2. Déploiement complet (Docker Compose)

Pour lancer l'intégralité de l'infrastructure (Proxy, Front, Back-end x2) :

```bash
docker-compose up -d --build

```

### 3. Vérification de la répartition de charge

Vous pouvez tester le **Round Robin** en interrogeant l'API à plusieurs reprises :

```bash
curl http://localhost:8080/api

```

Le proxy doit alterner les réponses entre les deux instances du serveur API.

## ✒️ Auteur

**Mathieu**

[Mathieu GODALIER](https://github.com/Mathieu7483) - Élève en programmation à la Holberton School

## ⚖️ Licence

Ce projet est sous licence **MIT**.

## 🙏 Remerciements

* **Holberton School** pour le curriculum.
* **Derek Webb** pour la conception de ce projet d'infrastructure.

