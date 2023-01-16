## Mise place d'une solution de "SIEM : Security Information and Event Management" : ELK 

### Table of contents
* [Tâche 1 : Utilisation de Elastic Security pour SIEM](https://github.com/Amine-er/SIEM-ELK#t%C3%A2che-1--utilisation-de-elastic-security-pour-siem)
```python
Étape 1 : Création d’un déploiement Elastic Cloud
Étape 2 : Ajout de l'intégration Network Packet Capture sur la machine
Étape 3 : Installation de Elastic Agent sur la machine
Étape 4 : Affichage des données
```
* [Tâche 2 : Surveillance les applications et les systèmes avec Elastic Observability](https://github.com/Amine-er/SIEM-ELK#t%C3%A2che-2--surveillance-les-applications-et-les-syst%C3%A8mes-avec-elastic-observability)
```python
Étape 1 : Ajout de Elastic Agent et l'intégration d'Elastic Agent System
Étape 2 : Surveillance les journaux et les métriques de l'hôte
```
<h3 align="left">Demo:</h3>
<p align="left">
<a href="https://www.youtube.com/watch?v=lYFLM_g00po&ab_channel=STRI_2023" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" alt="https://www.youtube.com/watch?v=lYFLM_g00po&ab_channel=STRI_2023" height="30" width="40" /></a>
</p>

### Tâche 1 : Utilisation de Elastic Security pour SIEM
Elastic Security combine Elastic SIEM, dont le moteur de détection automatise la détection des menaces afin que vous puissiez rapidement enquêter et répondre aux menaces, et Endpoint Security dans une solution unique qui unifie la prévention, la détection et la réponse sur l'ensemble de votre réseau.
Dans cette tache on va voir la configuration d'une intégration afin que nous puissions
collecter des données auprès de nos hôtes.

##### Étape 1 : Création d’un déploiement Elastic Cloud
Un déploiement Elastic Cloud nous offre toutes les fonctionnalités de la Suite Elastic en tant que service hébergé. Pour tester notre déploiement, on va créer d’abord un compte.

![image](https://user-images.githubusercontent.com/60274428/212709601-ad811c77-2bb2-4f56-9fcd-55d53ef7d08b.png)

On se connecte après à notre déploiement cloud, qui nous mènera à Kibana Home.

![image](https://user-images.githubusercontent.com/60274428/212709661-f9c7eda0-9fad-4d77-a3e2-69bf99916235.png)

##### Étape 2 : Ajout de l'intégration Network Packet Capture sur la machine
La surveillance de notre trafic réseau est essentielle pour obtenir une observabilité et sécuriser notre environnement, garantissant des niveaux élevés de performances et de sécurité.
On va choisir l’intégration Network Packet Capture qui permet de capture le trafic réseau entre nos serveurs d'applications, décode les protocoles de couche d'application courants et enregistre les champs intéressants pour chaque transaction.

![image](https://user-images.githubusercontent.com/60274428/212709735-5bc5e7e3-5ee0-47d2-8d7a-da40b81ef81e.png)

On clique sur Ajouter une capture de paquets réseau et on configure l'intégration.

![image](https://user-images.githubusercontent.com/60274428/212709768-3249af86-7b82-475f-8c1a-58f90043e50b.png)

##### Étape 3 : Installation de Elastic Agent sur la machine
Un agent unique facilite et accélère le déploiement de la surveillance sur l'ensemble de notre infrastructure. Cette intégration est optimisée par Elastic Agent donc il faut l’installer.
On tape les commandes suivantes pour installer Elastic Agent sur Windows.

![image](https://user-images.githubusercontent.com/60274428/212709822-1b25c2bf-7e8a-4d1b-8569-691239664b24.png)
![image](https://user-images.githubusercontent.com/60274428/212709849-f3dbb05e-17f0-45b6-860c-b2f83cb9327a.png)
![image](https://user-images.githubusercontent.com/60274428/212709874-0b638353-84be-4aba-85c4-93483dc3abb4.png)
![image](https://user-images.githubusercontent.com/60274428/212709894-4c31d2ab-b3aa-462a-8c09-46417b6ba136.png)

##### Étape 4 : Affichage des données
Une fois l'agent élastique ajouté et l'installation de l'intégration est terminée, on peut maintenant afficher les données. Les actifs de l’intégration sont classés par des tableaux de bord, recherches enregistrées et visualisations.
Dans le menu de navigation principal, on accède à la gestion Intégrations, puis on sélectionne l’onglet Assets. Et après on peut choisir Les actifs de l’intégration qui on veut visualiser.

![image](https://user-images.githubusercontent.com/60274428/212710281-46e1b5dd-5e54-4b28-a0e0-40160e9f6122.png)

Les images suivantes montrent le tableau de bord Network Packet Capture DNS Overview, qui fournit une vue d'ensemble visuelle des métriques de demande et de réponse DNS.

![image](https://user-images.githubusercontent.com/60274428/212710336-8f43020a-f9ce-4550-a289-2f2fef788cac.png)
![image](https://user-images.githubusercontent.com/60274428/212710437-3f0910ef-9ca1-444c-a95b-3b0e3af0d95b.png)
![image](https://user-images.githubusercontent.com/60274428/212710486-3851308d-848b-4317-acbf-e13e2463d606.png)

Les images suivantes montrent le tableau de bord [Network Packet Capture] DHCPv4, qui montre une vue d'ensemble visuelle des types de messages DHCP et le transfert des données.

![image](https://user-images.githubusercontent.com/60274428/212710518-b4b16a56-9b34-4a5f-aa07-4a3b44bde90d.png)
![image](https://user-images.githubusercontent.com/60274428/212710559-bc1a7137-dcf3-49a8-98cf-faf45ae08d6d.png)
![image](https://user-images.githubusercontent.com/60274428/212710587-d6fbf17d-ed8e-49f8-9f0f-3673588472d3.png)


### Tâche 2 : Surveillance les applications et les systèmes avec Elastic Observability
Dans cette Tache, nous allons déployer la Suite Elastic, installer un agent Elastic pour collecter des journaux et des métriques, et visualiser les informations de ces journaux et métriques collectés avec l’intégration System sur Linux Ubuntu.

##### Étape 1 : Ajout de Elastic Agent et l'intégration d'Elastic Agent System
Dans la page d'accueil de Kibana on sélectionne Ajouter des intégrations et nous choisissons l’intégration System.

![image](https://user-images.githubusercontent.com/60274428/212712979-c9eca5d3-dc21-434b-a2f1-cbb493e29794.png)

Après on va configurer la stratégie d'intégration système en choisissant les types de journaux, d'événements et de métriques à collecter.

![image](https://user-images.githubusercontent.com/60274428/212713047-60486835-a107-4c9d-a6c1-7c42f03d56e5.png)

Maintenant on va télécharger, installer et inscrivez Elastic Agent sur notre hôte Ubuntu en utilisant les commandes suivantes.

![image](https://user-images.githubusercontent.com/60274428/212713099-32a96bf3-bf07-4b4a-9caf-4e4cf2be32d3.png)
![image](https://user-images.githubusercontent.com/60274428/212713160-717a8cd8-6548-4cf5-89bc-a6d0f98a0093.png)
![image](https://user-images.githubusercontent.com/60274428/212713281-28122d8e-6edd-4bb9-9d13-74946bc2567b.png)

##### Étape 2 : Surveillance les journaux et les métriques de l'hôte
Maintenant que les données circulent, on Affiche les actifs pour accéder aux tableaux de bord liés à l'intégration du système.

![image](https://user-images.githubusercontent.com/60274428/212713468-e1eb9394-5f79-4ad8-a838-644510a51281.png)

Nous ouvrons le tableau de bord de présentation de l'hôte [Metrics System] Host overview par exemple pour afficher les mesures de performances de notre système hôte.

![image](https://user-images.githubusercontent.com/60274428/212713512-9dffd7e3-98a1-49df-830f-f5217cd70746.png)
![image](https://user-images.githubusercontent.com/60274428/212713555-ca3ff373-55c3-4b2d-b7c3-c3c145edb726.png)

On peut voir aussi le tableau de bord de présentation de [Logs System] Syslog qui contient généralement la plus grande quantité d'informations par défaut sur le système Ubuntu. Il se trouve dans /var/log/syslog.

![image](https://user-images.githubusercontent.com/60274428/212713615-8d303b09-9123-4c9a-bbc1-ee4c6c6ec9cc.png)
