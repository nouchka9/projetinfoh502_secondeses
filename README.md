# BallShadowPCF - Jeu 3D avec Ombres PCF

## Description

BallShadowPCF est un jeu 3D développé dans le cadre du cours INFOH502 à l'Université Libre de Bruxelles. Le projet simule une balle rebondissant sur un terrain de basketball avec des effets d'ombres réalistes utilisant la technique PCF (Percentage Closer Filtering), un skybox pour l'environnement, et une caméra contrôlable.

## Caractéristiques

✅ **Fonctionnalités implémentées :**
- Fenêtre OpenGL 3.3 avec GLFW
- Rendu 3D avec shaders personnalisés
- Système d'ombres PCF (Percentage Closer Filtering)
- Chargement de modèles 3D avec Assimp (.obj, .fbx)
- Gestion des textures
- Caméra contrôlable avec souris et clavier
- Skybox environnemental
- Système de score
- Physique de rebond de la balle
- Interface ImGui pour les paramètres
- Éclairage Phong avec spéculaire

🚧 **En cours de développement :**
- Animations avancées

## Technologies utilisées

- **OpenGL 3.3** - Rendu graphique
- **GLFW** - Gestion fenêtre et entrées
- **GLAD** - Chargement des extensions OpenGL
- **Assimp** - Chargement des modèles 3D
- **GLM** - Mathématiques 3D
- **ImGui** - Interface utilisateur
- **STB Image** - Chargement des textures

## Structure du projet

```
BallShadowPCF/
├── assets/
│   ├── environments/         # Textures skybox (6 faces cubemap)
│   ├── models/              # Modèles 3D (.obj, .fbx)
│   └── textures/            # Textures diverses
├── libs/                    # Bibliothèques externes
│   ├── assimp/
│   ├── glfw/
│   ├── glad/
│   ├── glm/
│   └── imgui/
├── src/                     # Code source
├── build/                   # Fichiers de compilation
├── CMakeLists.txt
└── README.md
```

## Prérequis

- **macOS 10.15+** ou **Linux** ou **Windows**
- **CMake 3.15+**
- **Compilateur C++17** (GCC 8+, Clang 9+, MSVC 2019+)
- **OpenGL 3.3+**

## Installation et compilation

### 1. Cloner le projet

```bash
git clone https://github.com/nouchka9/projetinfoh502_secondeses.git
cd projetinfoh502_secondeses
```

### 2. Compiler le projet

```bash
# Nettoyer le build précédent
rm -rf build

# Configurer avec CMake
cmake -B build

# Compiler
cmake --build build

# Optionnel: compilation en mode Release pour de meilleures performances
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
```

### 3. Exécuter

```bash
# Depuis la racine du projet
./build/main

# Ou depuis le dossier build
cd build
./main
```

## Contrôles

### Caméra
- **W, A, S, D** - Déplacements avant/arrière/gauche/droite
- **Flèches directionnelles** - Rotation de la caméra
- **Souris** - Look around (si activé)

### Interface
- **Tab** - Afficher/masquer l'interface ImGui
- **Échap** - Quitter l'application

### Paramètres ImGui
- Position et rotation des objets
- Paramètres d'éclairage
- Configuration des ombres
- Mode de rendu (avec/sans ombres)

## Problèmes connus

1. **Chemins des assets :** Les chemins sont actuellement codés en dur pour macOS. Adapter selon votre environnement.
2. **Performance :** Les ombres PCF peuvent impacter les performances sur du matériel ancien.
3. **Textures manquantes :** Certains modèles peuvent ne pas avoir leurs textures si les chemins ne sont pas correctement configurés.

## Résolution de problèmes

### Erreur de compilation
- Vérifiez que CMake 3.15+ est installé
- Assurez-vous d'avoir un compilateur C++17

### Modèles non chargés
- Vérifiez que les fichiers sont dans `assets/models/`
- Contrôlez les logs de la console pour les erreurs Assimp

### Textures manquantes
- Placez les textures dans `assets/textures/`
- Vérifiez que les chemins dans le code correspondent à votre structure

### Skybox noir
- Assurez-vous que les 6 images du skybox sont dans `assets/environments/`
- Noms requis : `px.png`, `nx.png`, `py.png`, `ny.png`, `pz.png`, `nz.png`

## Structure des shaders

Le projet utilise plusieurs shaders spécialisés :

- **Shadow Mapping** - Génération de la shadow map
- **Model Rendering** - Rendu des objets avec ombres PCF
- **Skybox** - Rendu du cube environnemental
- **Debug** - Rendu simple sans ombres

## Auteur

** Nguejeannette**  
Université Libre de Bruxelles - INFOH502  
Année académique 2024-2025

## Licence

Ce projet est développé dans un cadre éducatif pour le cours INFOH502.

## Liens utiles

- [Repository GitHub](https://github.com/nouchka9/projetinfoh502_secondeses)
- [Learn OpenGL - Shadow Mapping](https://learnopengl.com/Advanced-Lighting/Shadows/Shadow-Mapping)
- [Assimp Documentation](https://assimp-docs.readthedocs.io/)
