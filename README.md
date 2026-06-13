<p align="center">
  <img src="https://img.shields.io/badge/UCAD-École%20Supérieure%20Polytechnique-blue?style=for-the-badge" alt="ESP UCAD">
  <img src="https://img.shields.io/badge/Master%201-SSI%20%7C%20Programmation%20S%C3%A9curis%C3%A9e-red?style=for-the-badge" alt="M1 SSI">
</p>

<p align="center">
  <img src="https://img.shields.io/github/v/release/Cheikhdg14/SecureBank?style=flat-square&color=emerald" alt="Release">
  <img src="https://img.shields.io/github/stars/Cheikhdg14/SecureBank?style=flat-square&color=blue" alt="Stars">
  <img src="https://img.shields.io/badge/Node.js-v20%20LTS-green?style=flat-square&logo=node.js" alt="Node.js Version">
  <img src="https://img.shields.io/badge/Database-PostgreSQL-blue?style=flat-square&logo=postgresql" alt="PostgreSQL">
</p>

---

# 🛡️ SecurBank - Logiciel Bancaire Sécurisé

**SecurBank** est une application bancaire distribuée à succursales multiples, conçue avec une architecture client-serveur hautement sécurisée. Elle permet à des clients d'accéder à leurs comptes et d'effectuer des opérations financières depuis n'importe quel site de l'entreprise, tout en garantissant une traçabilité complète, une authentification forte et le chiffrement des données.

---

## 👥 L'Équipe du Projet
Ce projet est réalisé dans le cadre du cours de **Programmation Sécurisée (Partie 1)** dispensé par **Mr Doudou FALL** à l'École Supérieure Polytechnique (ESP) de Dakar.

| Nom & Prénom | Adresse e-mail | Rôle |
| :--- | :--- | :--- |
| **Khadidiatou FAYE** | faye50938@gmail.com | Chef de projet |
| **Fatou NDOUR** | fatoundour@esp.sn | Développeur Backend |
| **Cheikh Ahmed Tidiane DIENG** | cheikhahmedtidianedieng1@esp.sn | Développeur Front-end |
| **Mamadou Koné NDOUR** | mamadounndour@gmail.com | Sécurité & Tests |

---

## ⚙️ Stack Technique & Langages
* **Runtime :** JavaScript / Node.js (v20 LTS)
* **Framework API :** Express.js
* **Base de données :** PostgreSQL (via le pilote natif `pg`)
* **Outils d'Équipe :** 
  * Gestion de versions : **GitHub** (Workflow par branches avec revues de code systématiques)
  * Réunion de suivi : Tous les samedis de 20h00 à 23h00 (Google Meet) avec compte-rendu hebdomadaire.

---

## 🔐 Éléments de Sécurité Essentiels

Le système met en œuvre des mécanismes rigoureux pour répondre aux critères fondamentaux de la sécurité de l'information :

| Pilier de Sécurité | Intégration et Implémentation dans SecurBank |
| :--- | :--- |
| **Authentification Forte** | Identifiant + mot de passe haché avec `bcrypt` (work factor / coût de 12). Gestion de session via des jetons **JWT** signés en `HMAC-SHA256` et invalidés à la déconnexion. |
| **Autorisation (DAC)** | Contrôle d'accès discrétionnaire strict géré par des middlewares Express.js selon 3 rôles distincts : **Client**, **Agent** et **Administrateur**. |
| **Audit & Non-répudiation** | Journal d'audit persistant et immuable. Chaque action sensible enregistre l'acteur, l'horodatage UTC, l'IP source, l'état avant/après et un **hash SHA-256 chaîné** pour prévenir toute falsification. |
| **Confidentialité & Intégrité** | Données financières hautement sensibles (soldes, transactions) chiffrées au repos en **AES-256-GCM** en base de données. Flux réseau chiffrés de bout en bout via **HTTPS (TLS 1.3)** renforcé par les en-têtes `helmet`. |

---

## 🚀 Fonctionnalités Principales

### 👤 Espace Client
* Inscription et authentification sécurisée.
* Consultation du solde et de l'historique des transactions en temps réel.
* Réalisation de virements internes sécurisés et gestion des bénéficiaires.

### 💼 Espace Personnel Bancaire (Agents & Admin)
* **Agents :** Gestion opérationnelle des comptes clients (Création, blocage et déblocage de comptes).
* **Administrateurs :** Droits de supervision complets sur l'ensemble de l'infrastructure et de la gestion des utilisateurs de la plateforme.

---
