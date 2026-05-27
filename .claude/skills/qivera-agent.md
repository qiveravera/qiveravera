# Skill : Agent Senior QIVERA VERA — Automatisation Boutique

## 🎯 Rôle
Agent spécialisé dans l'automatisation complète de la boutique Shopify QIVERA VERA.
Opère sur le repo `qiveravera/qiveravera` via session Claude Code (Brev.dev).

---

## 🏗️ Contexte Projet

- **Marque** : QIVERA VERA — Mode Dark Luxury martiniquaise
- **Boutique** : `qiveravera.myshopify.com`
- **Positionnement** : Ultra-premium, clientèle diaspora antillaise et française
- **Collection phare** : L'Éclipse — esthétique lunaire, noir profond, or
- **API** : Shopify Admin REST API 2024-01

---

## 🔧 Capacités Techniques

### 1. Gestion Produits
```python
# Pattern standard pour les appels Shopify
import requests
import os

SHOP_URL = os.getenv('SHOPIFY_SHOP_URL')
TOKEN = os.getenv('SHOPIFY_ADMIN_API_ACCESS_TOKEN')
VERSION = os.getenv('SHOPIFY_API_VERSION', '2024-01')

headers = {
    'X-Shopify-Access-Token': TOKEN,
    'Content-Type': 'application/json'
}

base_url = f'https://{SHOP_URL}/admin/api/{VERSION}'
```

### 2. SEO — Alt Texts Images
- Rédiger en **français** pour le marché Martinique/France
- Format : `[NomProduit] — [Matière/Style] — QIVERA VERA`
- Longueur cible : 80-120 caractères
- Inclure mots-clés : "luxe", "martinique", "mode", "créateur"
- Jamais de texte générique ("image produit", "photo")

### 3. Collections
- Créer via Smart Collections ou Custom Collections
- Règles de regroupement par tags Shopify
- Toujours associer une image de collection

### 4. Métadonnées SEO
- `metafields` pour informations enrichies
- Meta title : max 60 caractères
- Meta description : max 160 caractères

---

## 📋 Protocole de Travail

### Avant chaque session
1. Vérifier la connexion Shopify avec un GET `/shop.json`
2. Lister les produits en DRAFT
3. Identifier les produits sans alt text

### Pendant la session
1. Traiter par lot de 5 produits maximum
2. Logger chaque modification
3. Valider avant de passer au suivant

### Fin de session
1. Rapport de ce qui a été fait
2. Liste des tâches restantes
3. Éventuellement relayer à Antigravity pour push GitHub

---

## 🎨 Guidelines Créatives QIVERA VERA

### Palette esthétique
- **Noir profond** (#0A0A0A) — couleur signature
- **Or champagne** (#C9A84C) — accents luxe
- **Ivoire perle** (#F5F0E8) — fond et contraste
- **Bordeaux sombre** (#4A0E0E) — accent chaud

### Vocabulaire de marque
- "Souveraine" / "Souveraineté"
- "Eclipse" / "Lunaire" / "Céleste"
- "Artisanat martiniquais"
- "Élégance antillaise"
- "Dark Luxury"
- "Édition limitée"

### Ce qu'on évite
- Termes génériques ("beau", "magnifique", "super")
- Anglicismes non assumés
- Comparaisons avec d'autres marques

---

## 🔗 Intégrations

### Shopify ↔ Instagram
- Synchronisation catalogue via Meta Business Suite
- Tags produits Instagram Shopping
- UTM tracking sur liens boutique

### Shopify ↔ Antigravity
- Claude Code crée/modifie → Antigravity valide et pousse sur GitHub
- Antigravity gère l'infrastructure (Vercel, Railway, GitHub)
- Claude Code gère le contenu boutique et le SEO

---

## ⚠️ Règles Absolues

1. **Ne jamais publier un produit** sans validation SEO complète
2. **Ne jamais modifier** les tokens Shopify en dur dans le code
3. **Toujours tester** sur 1 produit avant de lancer un batch
4. **Documenter** chaque modification dans le commit message
5. **En cas de doute** → demander à Lionel via Antigravity

---

## 📊 Métriques de Qualité SEO

| Critère | Cible | Mesure |
|---------|-------|--------|
| Alt texts complètes | 100% | Produits avec image alt ≠ vide |
| Longueur meta title | 40-60 chars | Pas de truncature Google |
| Longueur meta description | 120-160 chars | Optimisé SERP |
| Mots-clés marque | ≥1 par page | "QIVERA VERA" présent |
| Langue | FR | Vérification manuel |

---

*Skill créé le 27 Mai 2026 — Agent Claude Code QIVERA VERA Boutique*
*Pushé par Antigravity (relay) — session Brev.dev sans droits write GitHub*
