---
version: alpha
name: LIFE OS — Cyberpunk Dark
description: Système de design de l'app LIFE OS de Romain Patry. Dark mode haute densité, esthétique cyberpunk futuriste. Conçu pour mobile-first (max 480px), interactions tactiles.
colors:
  background: "#050508"
  background-2: "#0a0b14"
  background-3: "#0e1019"
  primary: "#00f0ff"
  secondary: "#a855f7"
  accent: "#f97316"
  success: "#34d399"
  danger: "#f87171"
  info: "#38bdf8"
  surface-04: "rgba(255,255,255,0.03)"
  surface-06: "rgba(255,255,255,0.05)"
  surface-08: "rgba(255,255,255,0.07)"
  surface-10: "rgba(255,255,255,0.09)"
  surface-15: "rgba(255,255,255,0.12)"
  text-dim: "rgba(255,255,255,0.35)"
  text-mid: "rgba(255,255,255,0.55)"
  text-light: "rgba(255,255,255,0.80)"
  text-full: "#ffffff"
typography:
  display:
    fontFamily: Orbitron
    fontSize: 20px
    fontWeight: "700"
    letterSpacing: 0.1em
  headline:
    fontFamily: Orbitron
    fontSize: 15px
    fontWeight: "700"
    letterSpacing: 0.08em
  body:
    fontFamily: Rajdhani
    fontSize: 14px
    fontWeight: "400"
    lineHeight: 1.6
  label:
    fontFamily: Rajdhani
    fontSize: 9px
    fontWeight: "600"
    letterSpacing: 0.15em
  mono:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: "400"
rounded:
  sm: 8px
  md: 10px
  lg: 14px
  xl: 20px
  full: 9999px
spacing:
  xs: 4px
  sm: 8px
  md: 14px
  lg: 20px
  xl: 32px
components:
  card:
    background: "linear-gradient(135deg, {colors.surface-04}, rgba(255,255,255,0.015))"
    border: "1px solid {colors.surface-06}"
    borderRadius: "{rounded.lg}"
    padding: "{spacing.md}"
    backdropFilter: blur(8px)
  button-primary:
    background: "linear-gradient(135deg, rgba(0,240,255,0.08), rgba(168,85,247,0.06))"
    border: "1px solid rgba(0,240,255,0.2)"
    borderRadius: "{rounded.md}"
    color: "{colors.primary}"
    fontFamily: Orbitron
    fontSize: 11px
    letterSpacing: 0.15em
    padding: "12px 0"
  nav-bar:
    position: fixed bottom
    background: "linear-gradient(to top, {colors.background} 50%, transparent)"
    height: 60px
    paddingBottom: 20px
  input:
    background: "{colors.surface-04}"
    border: "1px solid {colors.surface-08}"
    borderRadius: "{rounded.md}"
    color: "{colors.text-full}"
    fontFamily: JetBrains Mono
    fontSize: 13px
    padding: "8px 10px"
---

## Vue d'ensemble

LIFE OS est un tracker de vie quotidienne pour mobile. L'esthétique est **cyberpunk futuriste dark mode** : fond quasi-noir, accents cyan électrique et violet, typographie sci-fi Orbitron pour les titres, Rajdhani pour le corps.

L'interface est conçue pour une utilisation rapide à une main. Tout est dense, lisible sur petit écran, avec des animations légères (fadeUp, glow sur les éléments actifs).

## Couleurs

La palette repose sur des fonds très sombres (#050508, quasi-noir) avec trois accents saturés :

- **Cyan (#00f0ff)** : couleur primaire d'interaction — tous les éléments actifs, focalisés, sélectionnés.
- **Violet (#a855f7)** : couleur secondaire — métriques secondaires, dégradés complémentaires.
- **Orange (#f97316)** : accent chaud — alertes, badges, mises en valeur exceptionnelles.
- **Vert (#34d399)** : succès, validation, objectifs atteints.
- **Rouge (#f87171)** : danger, erreur, trades négatifs.

Les surfaces utilisent des blancs semi-transparents (rgba 3% à 15%) pour créer de la profondeur sans alourdir visuellement.

## Typographie

Trois familles, chacune avec un rôle précis :

- **Orbitron** — Titres, headers, CTA. Futuriste, anguleux. Toujours en majuscules ou letter-spacing large.
- **Rajdhani** — Corps de texte, labels, navigation. Lisible, léger, tech sans être agressif.
- **JetBrains Mono** — Données chiffrées, valeurs, montants. Monospace pour l'alignement des colonnes.

Les labels de navigation et catégories utilisent letter-spacing très large (1.5px+) pour renforcer l'esthétique futuriste.

## Composants

### Cards (`.glass`)
Fond verre foncé avec `backdrop-filter: blur(8px)`. Bordure très subtile (5% blanc). Coins arrondis 14px. Jamais de fond plein opaque — toujours une transparence pour voir le fond derrière.

### Boutons primaires
Dégradé cyan/violet très atténué + bordure cyan faible opacité. Couleur du texte = cyan. Font Orbitron, letter-spacing large. Sur mobile : `transform: scale(0.98)` au tap.

### Navigation bottom bar
Fixée en bas, fond dégradé vers transparent. Icônes emoji 20px. Label 9px Rajdhani. Élément actif = cyan + glow drop-shadow + indicateur dot 14px.

### Inputs
Fond surface très sombre, bordure subtile. Au focus : bordure cyan faible opacité + box-shadow cyan.

## Effets et animations

- **fadeUp** : entrée de page (opacity 0→1 + translateY 10px→0, 300ms ease)
- **Glow** : `filter: drop-shadow(0 0 8px var(--cyan))` sur les icônes actives
- **Pulse** : opacity 1→0.6→1 pour les indicateurs d'activité
- **Spin** : rotation 360° pour les loaders

## Grille et layout

- Mobile-first. Max-width : **480px**, centré horizontalement.
- Padding global : **14px** horizontal.
- Contenu principal : padding-bottom **130px** pour la nav bar.
- Cards empilées verticalement avec gap **8px**.

## Règles d'usage pour les agents IA

1. Ne jamais utiliser de fond blanc ou clair — tout reste dark mode.
2. Les données numériques (prix, scores, stats) s'affichent toujours en JetBrains Mono.
3. Le cyan est UNIQUEMENT pour les éléments interactifs actifs — jamais décoratif pur.
4. Les titres de section en Orbitron avec letter-spacing minimum 2px.
5. Tout nouvel écran entre en animation fadeUp.
6. Les erreurs sont rouge (#f87171), jamais orange.
7. Le violet est complémentaire du cyan, jamais dominant.
