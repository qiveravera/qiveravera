# CLAUDE.md — QIVERA VERA Boutique Shopify
# ⚠️ CE FICHIER EST LA SOURCE DE VÉRITÉ DU REPO `qiveravera/qiveravera`
# Lu par Claude Code et Antigravity — NE PAS SUPPRIMER

## 🏪 Contexte du Projet

Ce repo est le **hub central de l'écosystème QIVERA VERA** — marque de mode Dark Luxury martiniquaise.

- **Boutique Shopify** : `qiveravera.myshopify.com` (21 produits, collections créées)
- **Collection phare** : L'Éclipse (référence artistique lunaire, noir profond)
- **Marché** : Martinique + diaspora française — positionnement ultra-premium

---

## 🤖 Architecture Agentique

Ce repo est orchestré par **deux agents IA complémentaires** :

| Agent | Rôle | Session |
|-------|------|---------|
| **Claude Code** | Automatisation Shopify, SEO, déploiements | Brev.dev cloud |
| **Antigravity** | Architecture, GitHub, infrastructure, relais | PC local Lionel |

### Règle de collaboration inter-agents
- Claude Code crée les fichiers et demande à Antigravity de les pousser si le proxy git bloque
- Antigravity ne modifie jamais le code Shopify sans validation Claude Code
- En cas de conflit → **Lionel tranche**

---

## 🛍️ État de la Boutique Shopify

### Collections créées
- L'Éclipse
- Prêt-à-porter
- Accessoires

### Statut produits
- 21 produits en statut **DRAFT** — en cours de finalisation SEO
- Alt texts en cours de rédaction (session en cours)
- Publication prévue après validation SEO complète

---

## ⚙️ Configuration Technique

```bash
# Variables d'environnement requises
SHOPIFY_SHOP_URL=qiveravera.myshopify.com
SHOPIFY_ADMIN_API_ACCESS_TOKEN=<voir .env local Lionel>
SHOPIFY_API_VERSION=2024-01
```

### API Shopify utilisée
- Admin REST API `2024-01`
- Endpoints : `/products`, `/collections`, `/metafields`

---

## 🚦 Règles de Développement

1. **Langue** : Français pour les commentaires et le contenu boutique
2. **Secrets** : Ne jamais hardcoder — lire depuis `.env`
3. **Produits** : Toujours en DRAFT jusqu'à validation SEO + visuels
4. **SEO** : Alt texts obligatoires sur toutes les images produit
5. **Bots Telegram** : Voir `CLAUDE.md` du repo `QIVERA-OPENCLAW` pour les règles absolues

---

## 🛠 Commandes Utiles Claude Code

```bash
# Lister les produits Shopify
python scripts/list_shopify_products.py

# Mettre à jour les alt texts
python scripts/update_alt_texts.py

# Vérifier le statut des collections
python scripts/check_collections.py
```

---

## 📋 Roadmap Immédiate

- [ ] Alt texts SEO — Collection L'Éclipse (en cours)
- [ ] Alt texts SEO — Reste du catalogue
- [ ] Publication des 21 produits (après SEO)
- [ ] Configuration Shopify Markets (Martinique / France métro)
- [ ] Intégration Instagram Shopping

---
*Créé par Antigravity (relay Claude Code) — 27 Mai 2026*
