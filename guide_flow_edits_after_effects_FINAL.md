# Guide complet et exhaustif : Flow Edits sur After Effects

*Version finale fusionnée : synthèse des 6 tutoriels fournis, audités et recoupés avec un second guide indépendant. Conçu pour être donné à un agent chargé de produire des flow edits. Toutes les valeurs numériques sont des exemples tirés des tutos : points de départ à adapter à chaque clip, jamais des règles.*

## Sources (référencées entre crochets dans tout le document)

| Tag | Tuto | Contenu principal |
|---|---|---|
| **[1]** | « Edit in the flow style » (clips de clip musical) | Minimax + Offset, time remap, slide transition, warp transition, calque scale, flicker de tension, presets Impact |
| **[2]** | « Flow tutorial for beginners » (Naruto/Boruto) | Impact frames, Twixtor, caméra, S_Flicker, one-framer, BCC Lens Blur, sound design |
| **[3]** | « How to make flow edits » (pipeline pas à pas) | Tint, Motion Tile, masque, glitchs, color grading, clignotement d'opacité |
| **[4]** | « Flow edit transitions » | 4 recettes de transitions sur calques d'ajustement (Hotspots, Optical Flares, wipe Minimax, Glow) |
| **[5]** | « Quick tutorial » (Maki) | Philosophie du flow, continuité de mouvement, S_Shake de fond, warp simple |
| **[6]** | « Ep 1 » (How to actually edit in the flow style) | Sourcing, réglages de comp, Twixtor Pro, Card Dance, Warp Bubble, Time Slice, Bulge, Dissolve Shake, SFX |

**Légende des plugins** : **[AE]** natif After Effects (gratuit) · **[SAPPHIRE]** Boris FX Sapphire · **[BCC]** Boris Continuum · **[VC]** Video Copilot (Optical Flares) · **[DG]** Deep Glow · **[PRESET]** Ultimate Impact Bundle (payant) · **[TWIXTOR]** RE:Vision Twixtor Pro.

---

## 0. Consignes à l'agent

1. Lire d'abord les sections 1 à 4 (philosophie, setup, clips, pipeline) : elles dictent l'ordre de travail.
2. Les sections 5 à 12 sont des catalogues : techniques, effets avec valeurs, recettes de transitions.
3. **Toutes les valeurs numériques sont des points de départ.** Les tutos répètent que les réglages dépendent du clip : ajuster à l'œil.
4. Un flow edit = clips qui s'enchaînent par le mouvement + keyframes adoucis par des graphes + effets d'appoint + sound design. Aucun élément seul ne suffit.
5. Les plugins payants ont des alternatives en section 14 (certaines hors tutos, signalées comme telles).
6. Les limites connues de ce guide sont en section 17 : à lire avant de prétendre reproduire une courbe ou un preset exactement.

---

## 1. Concepts fondamentaux du flow

1. **Le flow, c'est d'abord le raccord entre clips, pas les effets** [5]. Il vient de la sélection des clips, des transitions et d'un mouvement qui continue d'un clip au suivant. Si deux clips s'enchaînent déjà bien sans rien, le flow existe : un peu de scale, position et opacité suffisent [5].
2. **Les effets ne portent pas l'edit : ils renforcent le mouvement déjà présent** [5]. Même un simple one-framer fonctionne si le flow existe.
3. **Continuité du mouvement** : la direction, la vitesse ou le zoom de fin du clip A se prolongent dans le clip B (un perso frappe vers la gauche → le clip suivant a un mouvement vers la gauche) [2][5].
4. **Rythme en vitesse variable** : chaque clip alterne très rapide → ralenti au point de raccord → ré-accélération (time remap + courbes) [1][2][3].
5. **Impact frames** : frames où « quelque chose de fort » se passe (coup, geste, changement). On garde ces frames, on supprime les frames « vides » [2].
6. **Tout est courbé** : aucun keyframe linéaire ; toujours Easy Ease puis graph editor. « Pas de mouvement rigide dans un flow edit » [6].
7. **Clips avec beaucoup de mouvement**, cinématiques et esthétiques ; un clip statique rend mal [1][6].
8. **Le scale est l'un des éléments les plus importants** : zoom/dézoom sur presque chaque clip, calé sur les transitions [1].
9. **Subtilité** : flickers, hotspots et shakes doivent être à peine visibles mais ressentis [1][2][6].
10. **Le sound design apporte la profondeur** et une grande part du rendu propre/pro/cinématique [2][6].
11. **Expérimenter** : tester, regarder, ajuster ; ne pas s'arrêter au premier résultat [2][6].
12. **Transitions courtes, effets empilés** : 1 à ~10 frames par transition, effets sur calques d'ajustement empilables [1][4].

---

## 2. Setup du projet

| Paramètre | Valeur | Source |
|---|---|---|
| Format | Jamais carré. Plutôt large ; réduire la hauteur pour un cadrage « cinéma » (bandes noires) | [6] |
| Frame rate | 12 à 24 fps ; **24 fps = cadence cinéma** (recommandé) ; 20 fps utilisé dans [4], accepté dans [6] | [4][6] |
| Durée de comp (exemple) | 10 s | [3] |
| Création | Ctrl+N, ou « New Composition from Footage » | [3][6] |

- Le frame rate de la comp sert aussi de valeur In/Out FPS pour Twixtor (section 6).
- Mise à l'échelle d'un clip : touche **S** [6]. Des bords noirs ou blancs peuvent apparaître avec certains effets (Card Dance, Warp) : scaler le clip pour combler [6].
- Nommer les calques (« scale », « flicker », « minimax ») [1].
- **Sauvegarder souvent** : After Effects plante ou bugue dans plusieurs tutos [2][3][6].

---

## 3. Sélection et sourcing des clips

- **Clips à mouvement marqué** (caméra, personnage, action) [1].
- **Clips qui « se lient »** : fin de l'un et début de l'autre partagent une direction, une forme ou un rythme [2][5].
- **Clips cinématiques et esthétiques**, agréables à l'œil [6].
- **Sources citées** : Clip Portal (clips aléatoires), Artgrid (clips cinématiques, effets « low shutter »), Envato (sound effects) [6]. Chaînes YouTube de référence : Haz, Dirt [6]. Recherche utile : « low shutter effects » [6].
- **Matière utilisée dans les tutos** : anime (Naruto/Boruto [2], Maki [5]), clips de vidéos musicales [1], clips cinématiques [6].
- Choisir les clips en cherchant leurs **frames d'impact** : avancer jusqu'à la frame où ça bouge, supprimer celles où rien ne se passe [2].
- Couper le clip précisément à l'instant utile (Ctrl+Shift+D).

---

## 4. Pipeline de travail recommandé

1. **Créer la comp** (section 2), importer et couper les clips.
2. **Repérer les impact frames** ; décaler/couper jusqu'à ce que le mouvement arrive [2].
3. **Séquencer** les clips : *Keyframe Assistant → Sequence Layers* après découpe [2].
4. **Pré-composer chaque clip** : Ctrl+Shift+C, « Move all attributes into the new composition » [3][6]. On peut y revenir (double-clic) pour modifier scale, time remap, graphes [6].
5. **Twixtor** sur les clips à mouvement faible/modéré (section 6) [2][6].
6. **Time remap + graphes + motion blur** (section 5) [1][2][3][6].
7. **Continuité de mouvement** : scale/position/caméra (section 7) [2][5][6].
8. **Transitions** sur calques d'ajustement (section 9) [tous].
9. **Flickers, one-framers, frames retirées, shakes** (section 10) [2][3][5].
10. **Étalonnage et netteté** (section 11) [3].
11. **Sound design** (section 12) [2][6].
12. **Pré-composer l'ensemble** si besoin pour appliquer un effet global (ex. Time Slice) [6].
13. Visionner, itérer, nettoyer les courbes.

**Principes d'organisation**
- Empiler des calques d'ajustement (un par effet ou fonction) : faciles à superposer, déplacer, dupliquer [6].
- Pré-composer tout sauf le calque global (shake, hotspots) ; on peut imbriquer plusieurs niveaux et retourner modifier à l'intérieur [6].
- Copier-coller un calque d'ajustement pour le réutiliser [6].
- Copier-coller les effets d'un calque à un autre : Ctrl+A dans le panneau d'effets, Ctrl+C, Ctrl+V [1][3].
- **U** affiche les keyframes ; **U U** (double appui) affiche toutes les propriétés modifiées d'un calque [6].

---

## 5. Time remap et courbes (le cœur du flow)

### 5.1 Méthode de base [1][3][6]
1. Sélectionner le clip (pré-composé), **Ctrl+Alt+T** (Time Remap). Deux keyframes apparaissent.
2. Keyframe au début ; aller à la fin réelle du clip source, keyframer ; puis **déplacer le keyframe de fin** là où le clip doit finir dans la timeline (le clip est alors très accéléré).
3. Sélectionner tous les keyframes, **F9** (Easy Ease), ouvrir le **Graph Editor**.
4. Remodeler la courbe (5.2).
5. Activer le **motion blur** : interrupteur du calque **et** interrupteur global de la comp. Rendu propre, sans lag [1].

### 5.2 Formes de courbe [1][3][6]
- **Standard** : très rapide au début, ralentit proprement au milieu (au raccord), ré-accélère à la fin. Réalisation : tirer fortement la poignée du premier point vers le haut et celle du dernier vers le bas [1].
- **Lent puis très rapide** (variante) : départ très lent puis accélération ; maintenir **Ctrl** pour verrouiller les poignées [3].
- **Variante pic** : un pic de vitesse puis un simple ralenti ; peut mieux rendre sur certains clips [1].
- Basculer **Speed Graph** (le plus utilisé) / **Value Graph**. Coins serrés, milieu adouci [6].
- Pour un clip déjà en slow motion : courbe plus raide au début et keyframes plus rapprochés [6].

### 5.3 Règles d'espacement [6][3]
- **Keyframes rapprochés = mouvement plus rapide ; espacés = plus lent.**
- **Alt + glisser** sur un groupe de keyframes pour espacer/serrer proportionnellement [3].
- Variation typique en pourcentage de vitesse : ~130–150 % → ~20 % (stopwatch, puis Easy Ease, courbe nette) [6].

### 5.4 Astuce « frames aléatoires via time remap » [1]
Ctrl+Alt+T, avancer d'une frame, sélectionner un keyframe de remap au hasard, avancer d'une frame, en choisir un autre. 3 frames suffisent pour créer deux frames très différentes à associer au point de transition.

### 5.5 Édition de keyframes
- **F9** ou clic droit > Keyframe Assistant > Easy Ease [1][6].
- **Copier/coller des keyframes** (Ctrl+C / Ctrl+V sur le curseur de temps) : aller-retour rapide (valeur → pic → valeur initiale) [3][4].
- Sans graph editor : F9 suffit parfois (flicker de tension) [1].

---

## 6. Twixtor (lissage du mouvement)

- **Quand** : clips à mouvement faible à modéré. Éviter sur les clips à très fort mouvement/impact (rendu très mauvais) [2]. Superflu sur les clips déjà en slow motion : le supprimer [6].
- **Mise en place** : pré-composer le clip, appliquer Twixtor (Pro de préférence) ; pré-composer à nouveau si on enchaîne [2][6].
- **Réglages Twixtor Pro** [6] :
  - In FPS = Out FPS = frame rate de la comp (ex. 24).
  - Frame Interp : **Blend**.
  - Warping : **Inverse with Smart Blend** (au lieu d'Inverse).
  - Motion Blur Compensation : **1 à 2** (2 utilisé).
- Copier-coller les réglages d'un clip à l'autre [6].
- Piloter ensuite la **vitesse** (Speed %) : keyframer ~130 % → ~20 % en quelques frames, Easy Ease, courbe nette ; rapprocher les keyframes si le début est trop lent [6].
- Ordre du tuto Naruto : sélection des frames → pré-compo → Twixtor → pré-compo → time remap [2]. Pour les réglages détaillés, [2] renvoie aux tutos YouTube « Twixtor flow tutorial ».

---

## 7. Scale, position, caméra, continuité de mouvement

### 7.1 Continuité entre deux clips [5]
- **Clip 1** : scale 100 % qui monte (zoom in) + position qui glisse légèrement vers la droite.
- **Clip 2** : l'inverse : démarre zoomé, dézoome en **continuant la même direction**.
- Un peu d'**opacité** pour fondre les deux clips.

### 7.2 Scale/position d'entrée [6]
- Avancer de quelques frames, keyframer scale (S) et position (P) ; au début, scaler et décaler le clip sur le côté.
- Easy Ease tous les keyframes. Pour la position : clic droit sur Position → **Separate Dimensions**, supprimer l'axe inutilisé, travailler la courbe de X.
- Courbe : très rapide au départ, sortie douce (jamais rigide).

### 7.3 Calque « scale » (sur chaque clip) [1]
- Calque d'ajustement avec **Transform [AE]**, **motion blur activé**.
- Keyframes : ~**132** au début du clip ; **100** au début de la transition ; ~**145** à la fin de la transition ; **100** peu après.
- Courbes **très raides** sur les chutes/impacts, plus douces sur les mouvements subtils.
- Nommer le calque « scale ».

### 7.4 Caméra virtuelle [2]
- Null ou animation Position + Scale pour **suivre l'action** (coup vers la gauche → le cadre accompagne vers la gauche), puis zoom sur le visage/le point d'impact. Faire arriver le clip du côté opposé en zoomant.
- Courbe de vitesse marquée puis ease out ; tester plusieurs cadrages avant de garder le meilleur.

### 7.5 Scale sur la fin d'un clip [6]
- Dans la précomp, scaler le clip pour que le cadre finisse sur le sujet (ex. la lune) ; Easy Ease + Speed Graph aligné sur la courbe de la transition précédente.
- Si besoin, scaler le clip en amont pour ne pas voir les bords.

---

## 8. Catalogue des effets (paramètres de départ)

### 8.1 Natifs After Effects
| Effet | Usage et réglages | Source |
|---|---|---|
| **Minimax** | Direction **Horizontal uniquement** (jamais H+V). Radius élevé (≈100–200) → ≈0–20. Fait « pop » les bords et accélère visuellement le mouvement. Souvent sans courbe particulière. Dupliquable (Ctrl+D) | [1][3][4][6] |
| **Offset** | **Au-dessus** de Minimax. Keyframer Shift Center To. Sur 2 frames pour une slide | [1] |
| **Warp (Fisheye)** | Style Fisheye ; Bend 0 → −100 → 0 | [1][5] |
| **Transform** | Calque scale, motion blur activé | [1] |
| **Tint** | Amount 100 → 0 sur quelques frames (flash) | [3] |
| **Motion Tile** | Augmenter l'output, cocher **Mirror Edges**, animer la position, courbe nette | [3] |
| **Mask + Feather** | Masque (Q), **Invert**, Mask Feather (F) élevé, pour un clip en incrustation | [3] |
| **Bulge** | Amount 0 → ~68 au centre de la transition → 0 (ripple léger) ; motion blur | [6] |
| **Displacement Map** | Effet « fondant » ; alternative à Card Dance, à utiliser seulement si la scène s'y prête | [6] |
| **Wave Warp** | Wave Height 0 → ~240 sur un one-framer | [5] |
| **Brightness & Contrast** | Contraste ~100 → 0 ; ou luminosité qui monte puis redescend (copier-coller les keyframes) | [3][4] |
| **Hue/Saturation** | Master Saturation −100 au milieu, 0 aux extrémités | [4] |
| **Exposure** | 2–3 → 0 pour un fondu lumineux d'entrée (optionnel) | [6] |
| **Echo** | ~2 échos, Echo Time réglable, fade-out possible ; proche du « low shutter » | [6] |
| **Glow (défaut)** | Threshold ~20 → 0 | [4] |
| **Card Dance** | Voir 9.8. Gratuit, catégorie Simulation | [6] |
| **Directional Blur** | 90°, Length 80 → 25 (ou → 0), keyframé | [1][3] |
| **Sharpen + Unsharp Mask** | Netteté | [3] |
| **Lumetri Color** | Étalonnage (ou Looks si disponible) | [3] |

### 8.2 Sapphire
| Effet | Réglages et usage | Source |
|---|---|---|
| **S_Hotspots** | Threshold keyframé (0,33 → 0 ; 0,1 puis 0 pour la tension) ; Blur Input 10 → 0. Assombrit/éclaircit, dissout, rend « cinématique ». Repli gratuit : Luma Key (moins bon) | [1][4][6] |
| **S_Flicker** | Amplitude 0 → 3–5, démarrer 5–7 frames avant la fin du clip, courbe très lente. Effet favori, presque invisible. Version « à peine visible » : amplitude ~0,09 | [1][2] |
| **S_Shake** | Keyframé pour l'impact ; **second calque** à amplitude/fréquence basses, **non keyframé**, comme micro-vibration constante | [5] |
| **S_ShakeDissolve / « dissolve shake »** | Amplitude 0 → 10 → 0 ; Dissolve % plus haut au début et à la fin ; Easy Ease ; courbe pas trop serrée | [6] |
| **S_WarpBubble** | Amplitude → 0 en quelques frames ; fréquence basse (ex. 3,41) ; distorsion subtile. Si bords visibles : scaler ou copier l'effet sur un autre calque | [6] |
| **S_TimeSlice** | Slice Direction ~180, Interpret Frames activé, ~3 tranches ; dissolution douce ; rotation d'entrée possible | [6] |

### 8.3 BCC
| Effet | Usage | Source |
|---|---|---|
| **BCC Swish Pan** (transcrit « switch pan ») | One-framer sur calque d'ajustement d'une frame | [2] |
| **BCC Lens Blur / Fast Lens Blur** | Scale 0 → ~50, courbe lente mais pas trop ; réglage R Scale réduit au besoin | [2][3] |
| **BCC Directional Blur** | Blur Amount keyframé qui revient à 0 | [3] |

### 8.4 Autres plugins et presets
| Effet | Usage | Source |
|---|---|---|
| **Deep Glow** [DG] (payant) | Exposure ~0,15 ; Input pour la sensibilité ; « pas indispensable si tu ne l'as pas » | [1][3] |
| **Optical Flares** [VC] | Render Mode **Over Original**, Brightness ~1400 → 0 sur ~6 frames, suivre le sujet frame par frame | [4] |
| **Presets Ultimate Impact Bundle** [PRESET] | Extreme Ripple (très populaire), Distortion Impact (utilisé presque à chaque edit), presets « dragon jump » ; glisser-déposer sur un calque d'ajustement | [1] |
| **Glitchs** (Chromatic Glitch Bar, Analog Glitch Skin Lines) | Mode **Add** ou **Color Dodge**, 1–2 frames, séquencés très rapidement, opacité réduite si trop fort | [3] |
| **Eye flare / lens flare léger** | Optionnel sur le clip | [2] |

---

## 9. Recettes de transitions (pas à pas)

Point commun : **calque d'ajustement** (Ctrl+Alt+Y) raccourci à la durée de la transition (Ctrl+Shift+D), motion blur activé, keyframes → Easy Ease (F9) → courbes retravaillées.

### 9.1 Minimax + Offset (« transition super populaire ») [1]
1. Calque d'ajustement de **2 frames**.
2. **Minimax** : Horizontal uniquement (Radius ~200 en H+V est moche).
3. **Offset** placé **au-dessus** de Minimax.
4. Keyframer Shift Center To (décalé au début, puis retour) et le Radius (haut → ~20).

### 9.2 Slide transition (la plus riche, peu intuitive) [1]
1. **Frames aléatoires** : entre les deux clips, 3–4 frames toutes très différentes (Ctrl+Shift+D successifs), pas forcément très visibles.
2. **Slide de départ** : calque de 2 frames, **Offset**, Shift Center ≈ 1000 sur 2 frames.
3. **Slide de sortie** : dupliquer (Ctrl+D), placer à la fin de la transition, valeur opposée (≈ 820).
4. **Calque de consolidation** sur toute la transition :
   - **S_Hotspots** : Threshold 0,33 → 0.
   - **Directional Blur** : 90°, Length 80 → 25.
   - **Minimax** (H) : Radius ~86, keyframe au milieu, ~20 à la fin.
5. **Warp** Fisheye, Bend −100, sur 1 frame (« starter »).
6. **Calque scale** (7.3).
7. **Tension avant la transition** (9.10).
8. Finition : preset **Extreme Ripple** [PRESET].

### 9.3 Warp transition [1][5]
- **Détaillée [1]** : Warp Fisheye, motion blur. Bend 0 au début → ~25 un peu avant le milieu (« pop in ») → **−100 au point de transition** → 0 plusieurs frames après. Courbes très raides sur les pics, plus douces ailleurs. Ajouter deux frames aléatoires (5.4, 3 frames) au point de transition ; puis S_Hotspots (Threshold), Deep Glow (Exposure ~0,15), Minimax (H, Radius ~100) ; copier ces effets sur la frame aléatoire. Accentuer avec **Distortion Impact** [PRESET]. En fin de séquence, sur le calque scale : Threshold de S_Hotspots plus haut en fin de transition, Amplitude de S_Flicker de 0 à très haut, courbes retravaillées ; dupliquer le calque Minimax.
- **Simple [5]** : calque de la durée de la transition, Warp Fisheye, Bend 0 → −100. Dupliquer sur le clip suivant et **inverser les keyframes** (−100 → 0) ; Easy Ease. **Solid d'1 frame** entre les clips, stylisé avec Wave Warp (Height 0 → ~240) + un one-framer.

### 9.4 Flash d'entrée S_Hotspots + blur [4]
Calque à la durée du cut : S_Hotspots, Threshold keyframé jusqu'à 0 à la dernière frame ; Blur Input 10 → 0 ; Easy Ease + courbe.

### 9.5 Optical Flares [4]
Calque ~6 frames : Optical Flares [VC], Render Mode **Over Original**, lumière sur le sujet, Brightness 1400 → 0, Easy Ease, position ajustée frame par frame pour suivre le sujet.

### 9.6 Wipe directionnel (Minimax + contraste + saturation) [4]
Calque ~8 frames :
- Minimax H : Radius 0 → ~100 (milieu) → 0.
- Brightness & Contrast : Contrast ~100 au pic, 0 en début/fin.
- Hue/Saturation : Master Saturation −100 au milieu, 0 en début/fin.
- Easy Ease + courbe de vitesse retouchée.

### 9.7 Variante Glow / duplication [4]
Dupliquer le wipe directionnel, le placer sur le cut suivant, ajouter **Glow** (Threshold ~20 → 0 aux extrémités).

### 9.8 Card Dance (effet « fonte / sable mouvant ») [6]
1. **Card Dance** [AE] sur un calque d'ajustement.
2. **Rows ≈ 450**, **Columns ≈ 350** (ou **Columns Follows Rows** pour voir les pixels).
3. **Back Layer** et **Gradient Layer 1** = clip A. **Z Position** : source = **Intensity 1**.
4. Keyframer **Multiplier** : 0 → ~2 au changement de scène → 0 ; augmenter si pas assez intense.
5. **Camera Position Z** keyframé pour reculer puis revenir, de façon à remplir l'écran et éviter un dézoom bizarre ; revenir à la valeur initiale (selon le clip).
6. Courbe : **Speed Graph**, poignées resserrées vers l'intérieur → effet quicksand/rebond ; rapprocher les keyframes pour plus de vitesse.
7. Pré-composer ensuite, puis ajouter au besoin Time Slice (9.9), Warp Bubble, Bulge (9.11), Dissolve Shake, Hotspots.

### 9.9 Time Slice [6]
S_TimeSlice sur la précomp : direction ~180, Interpret Frames, ~3 tranches ; rotation d'entrée possible ; scaler le clip d'arrivée pour finir sur le bon sujet (7.5).

### 9.10 Tension avant une transition [1]
1. Zone calme : keyframes S_Hotspots Threshold = 0 et S_Flicker Amplitude = 0.
2. **Une frame avant** la transition : Threshold ~0,1, Amplitude ~0,09.
3. **Une frame après** : Amplitude = 0. F9 suffit.
4. Résultat : léger assombrissement, tension à peine visible.

### 9.11 Bulge, Warp Bubble, Displacement Map [6]
Voir le catalogue 8 ; Bulge : Amount 0 → 68 → 0 au centre de la transition ; Warp Bubble : amplitude → 0 sur quelques frames.

### 9.12 Motion Tile / overlay masqué [3]
- Motion Tile + Mirror Edges, position animée, courbe nette.
- Second clip en overlay : position animée, masque inversé + feather élevé, keyframes de position au même endroit pour la dernière partie, courbe nette.

---

## 10. Flickers, one-framers, frames retirées, shakes

- **S_Flicker de fin de clip** : démarrer 5–7 frames avant la fin, 0 → 3–5, courbe très lente ; si trop visible, réduire [2]. On peut empiler **deux S_Flicker** [2].
- **One-framer** [2][3][5] : calque d'ajustement d'**1 frame** + effet fort (BCC Swish Pan, glitch, Wave Warp, Distortion Impact, preset). Les tutos insistent : avoir de bons one-framers. Presets : panneau Effects & Presets > User Presets ; puis ajuster les réglages. Possibilité d'ajouter une montée d'amount en fin de calque [3].
- **Retirer des frames** [2] : couper 2+ frames « vides » d'un clip pour l'agresser ; décaler jusqu'à la prochaine frame de mouvement ; combler le saut par un **flicker d'opacité** (keyframes 0/100).
- **Flicker d'opacité** [3] : 0 → 100 → 0 → 100 frame par frame, puis copier-coller ; Alt + glisser pour espacer.
- **Frames aléatoires** [1] : 1 à 3 frames très différentes à la transition.
- **Shake de fond** [5] : S_Shake sur un second calque, amplitude/fréquence basses, non keyframé.
- **Dissolve Shake** [6] : amplitude 0 → 10 → 0, Easy Ease, courbe pas trop serrée ; copier-coller le calque ; on peut augmenter le dissolve % au début.
- **Glitchs en overlay** [3] : voir 8.4.

---

## 11. Étalonnage et finition [3]

- **S_Hotspots** pour un rendu plus cinématique [3][6] ; **Deep Glow** : Input +, Exposure − [3].
- **Lumetri Color** (ou Looks ; Looks fait planter certains PC [3]) : look cohérent, ajuster l'exposition.
- **Sharpen + Unsharp Mask** pour la netteté perçue.
- **Brightness & Contrast** animé sur les impacts ; **Directional Blur** keyframé qui revient à 0.
- Appliquer le même grade à chaque clip (copier les effets) ; baisser l'opacité du calque d'étalonnage s'il est trop fort.
- Les modifications doivent rester presque invisibles mais rendre l'ensemble plus qualitatif [3].
- Activer le motion blur dès qu'il y a beaucoup de mouvement [1][6].

---

## 12. Sound design [2][6]

- Les SFX **donnent la profondeur** et le rendu pro/cinématique ; le flow ne fonctionne pas sans [6].
- **Sources** : Envato, packs de créateurs (Discord), **enregistrements maison** (voix, bruitages) : être créatif et expérimental [6].
- **Types** : punch/hit (coup), swing/whoosh (mouvement de bras), impact (cuts forts) [2]. *Riser* et *swish* sont des ajouts hors tutos.
- **Placement** : sur la frame d'impact ou au début du mouvement ; synchroniser avec flickers et frames d'impact ; superposer plusieurs sons possible.
- **Mixage** [2] : baisser les SFX trop forts (≈ −4 dB, puis −6 dB pour mieux entendre le punch) ; tester plusieurs sons et garder le plus convaincant ; fade-out lent sur un whoosh.

---

## 13. Raccourcis After Effects

| Raccourci | Action |
|---|---|
| Ctrl+N | Nouvelle composition |
| **Ctrl+Alt+Y** | Nouveau calque d'ajustement (Ctrl+Y = solid ; les tutos disent « Ctrl Y » par abus) |
| Ctrl+Shift+D | Couper un calque au curseur |
| Ctrl+D | Dupliquer |
| Ctrl+Shift+C | Pré-composer (Move all attributes) |
| Ctrl+Alt+T | Time Remap |
| F9 | Easy Ease |
| U / U U | Afficher les keyframes / toutes les propriétés modifiées |
| S / P / T / Q / F | Scale / Position / Opacité / Masque / Mask Feather |
| Ctrl+A puis Ctrl+C / Ctrl+V | Copier-coller des effets (panneau d'effets) |
| Ctrl+C / Ctrl+V sur la timeline | Copier-coller des keyframes |
| Ctrl + glisser (graph editor) | Verrouiller/symétriser les poignées |
| Alt + glisser (keyframes) | Espacer ou serrer proportionnellement |

---

## 14. Alternatives et solutions de repli

*Seuls Luma Key, Glow natif, Lumetri et la remarque sur Deep Glow viennent des tutos ; le reste est une suggestion hors tutos.*

| Payant | Alternative |
|---|---|
| S_Hotspots | Luma Key [6] ; hors tutos : Curves/Levels animés |
| Deep Glow | Glow natif [4] |
| Looks | Lumetri [3] |
| Twixtor Pro | Hors tutos : Pixel Motion / Optical Flow natif |
| Optical Flares | Hors tutos : Lens Flare natif keyframé |
| Presets Impact | Hors tutos : Offset + Minimax + Bulge/Warp + Directional Blur + Transform (recettes de la section 9) |
| Sapphire/BCC en général | Offset + Minimax + Warp + Directional Blur + Transform, tous natifs |

---

## 15. Erreurs à éviter

- Courbes raides non retravaillées (rendu rigide) [6].
- Minimax en H+V [1].
- Twixtor sur clips à très fort mouvement/impact [2].
- Clips statiques [1].
- Trop d'effets sur des clips qui ne s'enchaînent pas : le flow vient d'abord du choix des clips [5].
- Effets trop visibles : flickers, hotspots, shakes doivent rester subtils [1][2][6].
- SFX trop forts ou désynchronisés [2].
- Trou visible après retrait de frames sans keyframe d'opacité [2].
- Bords/bandes visibles : scaler [6].
- Oublier le motion blur sur les transitions rapides [1].
- Format carré [6].
- Ne pas sauvegarder (plantages) [2][3][6].

---

## 16. Checklist de production

1. Comp non carrée, 20–24 fps, durée adaptée.
2. Clips à fort mouvement, directions compatibles, impact frames repérées.
3. Pré-comps + Twixtor si pertinent.
4. Time remap + courbes lisses + motion blur.
5. Scale/position qui prolongent le mouvement ; calque scale par clip.
6. Transitions par calques d'ajustement (Minimax/Offset, Warp, Hotspots, Card Dance, Optical Flares…).
7. Flickers, one-framers, frames retirées + flicker d'opacité, shake de fond.
8. Étalonnage + netteté.
9. SFX synchronisés, volumes équilibrés.
10. Visionner, itérer ; vérifier que chaque effet renforce le mouvement plutôt que de le remplacer.

---

## 17. Limites et ambiguïtés de transcription

- **Courbes exactes non décrites** : les tutos disent « match my graph » ; les formes sont à l'écran, pas dans les transcriptions. Ce guide donne la logique (nette sur les pics, douce ailleurs), pas les valeurs de poignées. Pour reproduire une courbe précise : captures d'écran du Graph Editor.
- **Non expliqués** : « low shutter » (seul Echo est cité comme équivalent), « hyper slide », réglages de BCC Swish Pan, des glitchs et des presets Impact (« jouer avec les réglages »).
- **Noms d'effets déformés** : « Minimax » = Minimax [AE] ; « Offset » = Distort > Offset ; « Twixster » = Twixtor ; « CC car dance » = Card Dance ; « PCC/BCC switch pan » = très probablement Swish Pan ; « S flicker / S hotspots / S warp bubble / S time slice / dissolve shake » = Sapphire (noms exacts à vérifier) ; « Chris X » (tuto 3) = probablement Deep Glow, non vérifié.
- **Raccourcis** : « Ctrl twice » (tuto 1) correspond probablement à la création d'un calque d'ajustement ; « Ctrl T » = Ctrl+Alt+T ; dans le tuto 6 la touche « Q » citée pour afficher les keyframes est une erreur : c'est **U**.
- **Valeurs mal transcrites** : certaines valeurs de Minimax/Glow du tuto 4 sont ambiguës (début/fin) : respecter la logique 0 → pic → 0. Camera Z de Card Dance (tuto 6) : valeur dépendante du clip.
- **Presets payants** non reproductibles sans le bundle : utiliser les recettes manuelles.
- **Hors périmètre** : promotions, giveaways, liens Discord/Instagram.
