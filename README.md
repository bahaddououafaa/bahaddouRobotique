# bahaddouRobotique
rendu du projet 
# Convoi de Robots Thymio – Simulation Webots

## Description du Projet

Ce projet consiste à simuler un convoi de trois robots Thymio dans Webots :

- 1 robot **Obstiné** (leader)
- 2 robots **Timid** (suiveurs)

Le robot Obstiné est contrôlé au clavier, tandis que les deux robots Timid le suivent automatiquement à l’aide de leurs capteurs de proximité.

---

## onctionnement des Personnalités

### Robot Obstiné (Leader)

Le robot leader est contrôlé par les flèches du clavier :

- Flèche Haut : avancer
- Flèche Gauche : tourner à gauche
- Flèche Droite : tourner à droite

Le code contrôle directement les vitesses des deux moteurs pour effectuer les mouvements.

---

### Robots Timid (Suiveurs)

Les robots Timid utilisent leurs 7 capteurs de proximité horizontaux :

- Capteurs 0-1 → gauche
- Capteur 2 → centre
- Capteurs 3-4 → droite

Le comportement implémenté :

1. Si l’obstacle (leader) est détecté à gauche → le robot tourne à gauche.
2. Si détecté à droite → le robot tourne à droite.
3. Si détecté devant → le robot avance.
4. Si trop proche → il ralentit ou s’arrête.
5. Si le leader n’est plus détecté → le robot avance en mode recherche.

Une adaptation dynamique de la vitesse a été ajoutée :
- Plus le leader est loin, plus le robot Timid accélère.
- Plus le leader est proche, plus il ralentit.

Cela permet de maintenir une distance stable dans le convoi.

---

##Tests Réalisés

### Test 1 : Test Individuel des Robots

Chaque robot a été testé séparément :

- Test du robot Obstiné seul pour vérifier le contrôle clavier.
- Test du robot Timid seul pour vérifier la détection par capteurs et le suivi d’un obstacle.

🎥 Vidéo 1 : Test individuel des robots.

---

### Test 2 : Test du Convoi Complet

Simulation avec :
- 1 Obstiné contrôlé au clavier
- 2 Timid en mode suiveur

Objectif :
Vérifier que les robots Timid suivent correctement le leader dans différentes situations :
- Avancement en ligne droite
- Virage à gauche
- Virage à droite
- Variation de vitesse

 Vidéo 2 : Démonstration complète du convoi.

---

## Détails Techniques du Code

- Utilisation des capteurs `prox.horizontal`
- Calcul de la détection gauche / centre / droite
- Ajustement des vitesses moteurs avec `setVelocity()`
- Utilisation de seuils :
  - `STOP_TH`
  - `DETECT_TH`
- Ajustement dynamique de la vitesse pour maintenir la distance

---

## Lancer la Simulation

1. Ouvrir Webots
2. Charger le fichier world
3. Cliquer sur "Play"
4. Utiliser les flèches pour contrôler le leader

