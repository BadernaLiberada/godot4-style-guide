
# Godot 4 Style Guide
Heavenly (yeah) inspired in Allar Unreal Style Guide: https://github.com/Allar/ue5-style-guide/tree/main

I'm an artist so I won't cover code, there are already several examples for that on the internet.
## Asset Prefixes

Each asset type follows a prefix system to ensure quick identification and project consistency, It could be possible to just use suffixes (.skeleton) but Godot is inconsistent when it comes to that.
Below is the list of some prefixes:

| Asset Type                         | Prefix   | Sufix                        | Example                          |
|---------------------------------------|-----------|-------------------------------|----------------------------------|
| **AI Behaviour Tree**                 | `BT_`     |                               | `BT_Patrol.tres`                |
| **AI Behaviour Tree Action**          | `BTA_`    |                               | `BTA_AttackEnemy.tres`          |
| **AI Blackboard**                     | `BB_`     |                               | `BB_EnemyBehaviour.tres`        |
| **Animation Library**                 | `AL_`     |                               | `AL_PlayerAnims.animlib`        |
| **Animation**                         | `A_`      |                               | `A_Run.tscn`                    |
| **Audio Stream**                      | `AS_`     |                               | `AS_Explosion.ogg`              |
| **Curve**                             | `C_`      |                               | `C_HealthCurve.tres`            |
| **Environment**                       | `ENV_`    |                               | `ENV_Skybox.tres`               |
| **Font**                              | `F_`      |                               | `F_OpenSans.ttf`                |
| **GDScript**                          | `GD_`     |                               | `GD_CharacterMovement.gd`       |
| **Material**                          | `M_`      |                               | `M_GlobalCharacter.tres`        |
| **MeshLibrary**                       | `ML_`     |                               | `ML_ModularPieces.meshlib`      |
| **Particle "ˢʸˢᵗᵉᵐ"**                 | `PS_`     |                               | `PS_Birds.tscn`                 |
| **Plugin**                            | `PL_`     |                               | `PL_CustomInspector.gd`         |
| **Resource**                          | `R_`      |                               | `R_LivingEntity.tres`           |
| **Shader Code**                       | `SH_`     |                               | `SH_CellShading.gdshader`       |
| **Shader Visual**                     | `VS_`     |                               | `VS_TerrainTriplanar.tres`      |
| **Scene**                             | `SC_`     |                               | `SC_MainMenu.tscn`              |
| **Skeletal Mesh**                     | `SK_`     |                               | `SK_ShadowTheHedgehog.fbx`      |
| **Static Mesh**                       | `SM_`     |                               | `SM_Tree1.fbx`                  |
| **Sprite**                            | `SPR_`    |                               | `SPR_Character.png`             |
| **2D artists help me**                            | `I really`    |                               | `never used 2D in godot`             |
| **Texture**                           | `T_`      | `_D`, `_R`, `_N`, `_M`, `_AO`, `_ORM`     | `T_ShadowTheHedgehog_D.png`     |
| **Theme**                             | `TH_`     |                               | `TH_MainMenu.tres`              |
| **Tile Map**                          | `TM_`     |                               | `TM_Level1.tscn`                |
| **Tile Set**                          | `TS_`     |                               | `TS_Forest.tres`                |

If ur asking why there's behaviour tree, open now the assetlib and download **LimboAI!!**
## Example Project Content Structure

```
|-- Art
|   |-- Animations
|   |	'-- AS_Run.tscn
|   |-- Characters
|   |	'-- ShadowTheHedgehog
|   |      |-- SK_ShadowTheHedgehog.fbx
|   |	   |-- M_ShadowTheHedgehog.tres
|   |	   '-- T_ShadowTheHedgehog_D.png
|   '-- Environment
|	|-- Foliage
|	|   |-- SM_Flower1.fbx
|	|   '-- T_Flower1_D.png
|	'-- GerudoValley
|	    '-- SM_Store.fbx
|-- Core
|   |-- AI
|   |	|-- Actions
|   |	|   |-- BTA_Patrol.tres
|   |	|   '-- BTA_WalkToPoint.tres
|   |	|-- BlackBoard
|   |	|   '-- BB_EnemyVariables.tres
|   |	'-- BehaviourTree
|   |       '-- BT_EnemyAI.tres
|   |-- Characters
|   |	|-- Player
|   |	|   '-- SC_Player.tscn
|   |	'-- Enemies
|   |-- GameplayMechanics
|   |	|-- GD_CharacterMovement.gd
|   |	|-- GD_CombatSystem.gd
|   |	'-- GD_CameraSystem.gd
|   |-- Engine
|   |	|-- GD_DialogSystem.gd
|   |	'-- GD_GameInstance.gd
|   |-- Interactables
|   |-- Pickups
|   |-- Plugins
|   |-- Resources
|   |	|-- R_LivingEntity.tres
|   |	|-- R_Equipment.tres
|   |	'-- R_SaveFile_tres
|   '-- Weapons
|	'-- GD_RangedWeapon.gd
|-- Docs
|   |-- README.md
|   '-- DesignDocumentation.md
|-- Maps
|   '-- SC_MainMenu.tscn
|-- MaterialLibrary
|   |-- M_GlobalCharacter.tres
|   |-- SH_CellShading.gdshader
|   '-- VS_TerrainTriplanar.tres
|-- Placeables
|   |-- SC_Sign.tscn
|   '-- SC_Chest.tscn
|-- Sound
|   |-- SFX
|   |	|-- A_Explosion.ogg
|   |	'-- Environment
|   |       '-- A_Waterfall.ogg
|   |-- Music
|   |	'-- A_ClubClassics.ogg
|   '-- Voiceovers
|-- UI
|   |-- MainMenu
|   |	'-- T_TitleScreen.png
|   |-- InGame
|   |	|-- SC_LifeBar.tscn
|   |	'-- T_LifeBar.png
|   '-- Themes
|   	|-- TH_Inventory.tres
|   	'-- TH_MainMenu.tres
'-- VFXLibrary
    |-- CommonTextures
    |	'-- T_Star.png
    '-- ParticleSystems
    	|-- PS_Birds.tscn
	|-- PS_FireTrail.tscn
	|-- LevelUp
	|   |-- T_LevelUp.png
	|   '-- PS_LevelUp.tscn
	'-- ShadowTheHedgehog
	    '-- PS_HecklerKochMP5A3.tscn
```

I hope this gives you a general idea of ​​how to separate workspaces, after all, those who are going to work with UI sometimes don't need to open the programmer's folder and vice versa.
