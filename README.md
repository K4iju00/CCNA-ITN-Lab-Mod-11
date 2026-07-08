# CCNA Lab - Module 11 : Adressage IPv4 et Premier Ping

Ce dépôt contient un laboratoire pratique d'initiation à l'adressage IPv4 et à la configuration de base des équipements à l'aide de Cisco Packet Tracer.

## 📌 Objectifs du Lab
- Construire une topologie simple interconnectant deux réseaux distincts.
- Attribuer des adresses IPv4 statiques et des masques de sous-réseau (Classe C).
- Configurer les interfaces de routage via l'interface en ligne de commande (CLI).
- Valider la connectivité de bout en bout via des requêtes ICMP (Ping).

## 🗺️ Topologie Réseau
*(Prends une capture d'écran de ton Packet Tracer, nomme-la `topologie.png` et place-la dans ce dossier)*
![Topologie du réseau](./topologie.png)

## 💻 Tableau d'Adressage

| Équipement | Interface | Adresse IP | Masque de sous-réseau | Passerelle par défaut |
| :--- | :--- | :--- | :--- | :--- |
| **Router** | G0/0 | 192.168.1.1 | 255.255.255.0 | N/A |
| **Router** | G0/1 | 192.168.2.1 | 255.255.255.0 | N/A |
| **PC-A** | NIC | 192.168.1.10 | 255.255.255.0 | 192.168.1.1 |
| **PC-B** | NIC | 192.168.2.10 | 255.255.255.0 | 192.168.2.1 |

## 🛠️ Commandes Configuration Routeur (CLI)
```text
Router> enable
Router# configure terminal
Router(config)# interface g0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface g0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# no shutdown


---

### 2. La procédure pour tout envoyer en ligne

Crée d'abord un nouveau dépôt **public ou privé** sur ton compte GitHub, nomme-le par exemple `CCNA-Module-11-Lab`. Ne coche *pas* la case "Add a README file" (puisqu'on vient d'en créer un). 

Ouvre ton terminal dans le dossier où se trouvent ton fichier Packet Tracer, ton `README.md` et ton image `topologie.png`, puis suis ces étapes dans l'ordre :

<Sequence>
{/* Reason: L'ordre des commandes Git est crucial. Initialiser, lier le dépôt distant puis pousser dans le bon ordre évite des conflits fatals. */}
  <Step subtitle="Dans ton terminal" title="Initialiser le dépôt local">
    Transforme ton dossier local en dépôt Git avec la commande :
    ```bash
    git init
    ```
  </Step>
  <Step subtitle="Préparation du commit" title="Ajouter et valider les fichiers">
    Indexe tous tes fichiers (`.pkt`, `.md`, `.png`) et crée ton premier point de sauvegarde :
    ```bash
    git add .
    git commit -m "Initial commit: Ajout du lab Module 11 et de la doc"
    ```
  </Step>
  <Step subtitle="Envoi sur le cloud" title="Lier à ton GitHub et pousser">
    Configure la branche principale et lie ton terminal à ton dépôt GitHub distant (remplace l'URL par la tienne) :
    ```bash
    git branch -M main
    git remote add origin https://github.com/TON_PSEUDO/CCNA-Module-11-Lab.git
    git push -u origin main
    ```
  </Step>
</Sequence>
