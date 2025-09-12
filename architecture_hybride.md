# Architecture de Communication NeuroGrid

## 🎯 Vue d'Ensemble

Pour NeuroGrid, la **communication entre les composants** utilise une **architecture hybride stratifiée** qui adapte le protocole selon le type d'interaction et optimise l'expérience utilisateur sur chaque plateforme.

## 🔧 Architecture de Communication Recommandée

### **Approche Hybride Stratifiée**

Pour NeuroGrid, je recommande une **architecture hybride** qui adapte le protocole selon le type d'interaction :

## 📡 Protocoles par Type de Communication

### **WebSockets - Communication Temps Réel**
**Usage** : Mises à jour en temps réel, notifications instantanées
- **NeuroGrid-NL** (Web) : WebSockets pour les mises à jour live de NeuroCity
- **NeuroGrid-DMS** (Mobile) : WebSockets pour le suivi en temps réel des drones
- **Synchronisation** : État du jeu, position des véhicules, événements

**Avantages** :
- Communication bidirectionnelle continue
- Latence ultra-faible pour l'immersion
- Parfait pour les jeux en temps réel

### **REST API - Actions Structurées**
**Usage** : Opérations CRUD, authentification, gestion de ressources
- **Authentification** des joueurs
- **Gestion de flotte** (création, modification, suppression)
- **Système économique** (transactions, contrats)
- **Progression** du joueur (statistiques, achievements)

**Avantages** :
- Simplicité d'implémentation et de debug
- Scalabilité naturelle (stateless)
- Cache-friendly pour les données moins volatiles

### **TCP Sockets - Terminal SSH**
**Usage** : NeuroGrid-Terminal pour l'expérience "hacker" authentique
- **Interface ligne de commande** native
- **Sessions persistantes** pour l'immersion
- **Sécurité renforcée** par SSH

## 🏗️ Architecture Détaillée

### **NeuroGrid-Core (Serveur Central)**

'''
┌─────────────────┐
│ NeuroGrid-Core  │
├─────────────────┤
│ Game Engine     │ ← Logique métier, temps réel
│ REST API        │ ← Actions structurées
│ WebSocket Hub   │ ← Temps réel bidirectionnel
│ SSH Server      │ ← Terminal authentique
│ Database        │ ← Persistance des données
└─────────────────┘
'''

### **Communication par Client**

**NeuroGrid-Terminal** (SSH) :
- **SSH TCP** : Session persistante sécurisée
- **Commandes texte** → **Réponses JSON** via tunnel SSH

**NeuroGrid-DMS** (Android) :
- **REST API** : Actions (login, CRUD flotte, transactions)
- **WebSockets** : Mises à jour temps réel (position drones, notifications)

**NeuroGrid-NL** (Web) :
- **REST API** : Chargement initial, actions utilisateur
- **WebSockets** : NeuroLink temps réel, état de NeuroCity

## 📋 Détail des Interactions par Version

### **🖥️ NeuroGrid-Terminal (SSH)**

#### **SSH uniquement - Session Persistante**
Terminal ←─────SSH─────→ Core
(Port 22/2222)

**Interactions SSH :**
- **Authentification** : Clés SSH + login utilisateur
- **Interface commandes** : Parsing de commandes texte
- **Réponses temps réel** : Output streaming des résultats
- **Session state** : Maintien du contexte utilisateur

**Exemple de flux :**
$ neurogrid drone list
→ SSH: {"action": "drone_list", "user": "player1"}
← SSH: {"status": "ok", "drones": [...]}

### **📱 NeuroGrid-DMS (Android)**

#### **Approche Hybride : REST + WebSockets**

**REST API** (Actions Structure) :
DMS ─────HTTPS────→ Core/api/v1/
←────JSON─────

**WebSockets** (Temps Réel) :
DMS ←────WSS─────→ Core/ws/dms
←───Events───→

#### **Répartition REST vs WebSocket :**

**REST API :**
- `POST /auth/login` - Connexion utilisateur
- `GET /fleet/drones` - Liste des drones
- `POST /fleet/drone` - Créer nouveau drone
- `PUT /fleet/drone/{id}` - Modifier drone
- `DELETE /fleet/drone/{id}` - Supprimer drone
- `GET /contracts/available` - Contrats disponibles
- `POST /contracts/{id}/accept` - Accepter contrat

**WebSockets :**
- `drone.location.update` - Position temps réel
- `drone.status.changed` - Changement d'état
- `contract.completed` - Mission terminée
- `notification.new` - Nouvelles notifications
- `market.price.update` - Fluctuations économiques

### **🌐 NeuroGrid-NL (Web)**

#### **Approche Hybride : REST + WebSockets**

**REST API** (Données Statiques) :
Browser ─────HTTPS────→ Core/api/v1/
←────JSON─────

**WebSockets** (NeuroLink Temps Réel) :
Browser ←────WSS─────→ Core/ws/neurolink
←───Events───→

#### **Répartition REST vs WebSocket :**

**REST API :**
- `GET /user/profile` - Profil utilisateur
- `GET /city/districts` - Données des districts
- `GET /fleet/overview` - Vue d'ensemble flotte
- `POST /research/upgrade` - Améliorer équipement
- `GET /factions/status` - Relations factions

**WebSockets :**
- `city.events.live` - Événements de NeuroCity
- `neurolink.traffic` - Trafic réseau temps réel
- `player.interactions` - Interactions autres joueurs
- `economy.fluctuations` - Changements économiques
- `faction.activities` - Activités des factions

## 🔄 Patterns de Communication

### **Authentification Unifiée**
Tous les clients utilisent le **même système d'auth** :
Login via REST → JWT Token

JWT utilisé pour WebSocket handshake

SSH utilise clés + validation JWT

### **Synchronisation d'État**
Action Client → REST API → Database Update
↓
WebSocket Broadcast → Autres clients

### **Gestion des Erreurs**
- **REST** : Codes HTTP standards (400, 401, 500)
- **WebSocket** : Messages d'erreur structurés JSON
- **SSH** : Codes retour Unix + messages explicites

## 🚀 Avantages de Cette Architecture

### **Performance Optimisée**
- **WebSockets** : Latence minimale pour l'immersion temps réel
- **REST** : Cache et optimisation pour les données statiques
- **SSH** : Sécurité maximale pour l'expérience terminal

### **Scalabilité**
- **REST stateless** : Scale horizontalement facilement
- **WebSockets** : Clustering possible avec Redis pour la synchronisation
- **Séparation des préoccupations** : Chaque protocole pour son usage optimal

### **Développement**
- **Standards établis** : Pas de réinvention de la roue
- **Écosystème riche** : Bibliothèques matures disponibles
- **Debug facilité** : Outils existants pour chaque protocole

### **Optimisations Spécifiques**

**Mobile (DMS) :**
- **Polling réduit** grâce aux WebSockets
- **Cache local** des données REST
- **Compression** des messages WebSocket

**Web (NL) :**
- **Lazy loading** des ressources REST
- **Reconnexion automatique** WebSocket
- **State management** côté client

**Terminal :**
- **Commandes batch** pour réduire latence
- **Output buffering** pour sessions lentes
- **Historique local** des commandes

## 🔐 Considérations Techniques

### **Sécurité**
- **Authentification centralisée** via JWT/OAuth2
- **HTTPS/WSS** pour toutes les communications web
- **SSH keys** pour l'accès terminal

### **Gestion des États**
- **Serveur autoritaire** pour éviter la triche
- **Prédiction côté client** pour la réactivité mobile/web
- **Synchronisation périodique** pour la cohérence

---

Cette architecture **hybride** vous donne le meilleur des mondes : la performance temps réel où nécessaire, la simplicité REST pour les opérations standard, et l'authenticité SSH pour l'expérience hacker immersive !
