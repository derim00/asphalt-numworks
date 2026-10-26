# Asphalt: Urban GT 2 – Édition NumWorks

Port NumWorks par **yamii** (Discord : `cjnw`) – serveur : https://discord.gg/sti2d

Un remake arcade d'*Asphalt: Urban GT 2* (Nintendo DS) écrit en C pour la calculatrice NumWorks.
Il a été entièrement reconstruit pour la calculatrice. Le ROM DS (32 Mo, en vraie 3D) ne peut pas tourner sur une NumWorks.

**Fichier à installer :** `output/asphalt-urban-gt2.nwa` (environ 645 Ko, sous la limite de 2 Mo)

## Installation
1. Branche la NumWorks (N0110 / N0115 / N0120, firmware Epsilon récent) en USB.
2. Va sur <https://my.numworks.com/apps> avec Chrome ou Edge et choisis le fichier `.nwa`.
   Tu peux aussi utiliser `npx nwlink@1.0.0 install-nwa output/asphalt-urban-gt2.nwa`.
3. L'app « Asphalt GT2 » apparaît dans le menu Home.

## Commandes
| Touche | Action |
|---|---|
| ← → | Diriger |
| ↓ | Freiner |
| ↑ (ou OK / EXE en accélération auto) | Nitro |
| OK / EXE | Accélérer (si l'accélération auto est désactivée) |
| Retour | Pause |
| Maison | Quitter |

## Contenu
- **6 villes** : Rio de Janeiro, Paris, Las Vegas, Shanghai, La Havane et New York. Chacune a son ciel, son monument, ses décors et son circuit (virages et collines).
- **4 modes** : Course (jusqu'à 8 pilotes), Duel, Contre-la-montre (checkpoints) et Chasse aux flics.
- **Carrière** de 12 épreuves avec des médailles. La **course rapide** est entièrement configurable.
- **Nitro** (bouteilles à ramasser sur la route) et **TAKEDOWNS** (fonce dans les voitures en nitro).
- Indice **WANTED** avec poursuites policières, trafic urbain, argent et mini-carte.
- **Garage** : 6 voitures, 10 couleurs, améliorations Moteur / Nitro / Pneus.
- **Codes de sauvegarde** à 11 chiffres. Les apps NumWorks ne peuvent pas écrire de fichiers, donc ce code garde ta progression.

## Compiler soi-même
```
sudo apt install gcc-arm-none-eabi
python3 tools/gen_assets.py   # régénère les sprites (Python 3 + Pillow + numpy)
make                          # produit output/asphalt-urban-gt2.nwa
host/build.sh && host/shots.sh demo "5:ok" "40"   # version PC de test (captures PPM/PNG)
```
