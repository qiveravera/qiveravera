# QIVERA VERA — Contexte Projet

## La Marque
- **Nom** : QIVERA VERA
- **Créateur** : Lionel Mogade
- **Domaine** : qiveravera.com
- **Univers** : Sportswear premium / prêt-à-porter style athlétique
- **Positionnement** : Marque française émergente, qualité premium, identité forte

## Stack Technique
- **Storefront** : Shopify Hydrogen (Remix / React)
- **Hébergement** : Shopify Oxygen
- **CI/CD** : GitHub Actions → Oxygen (workflow déjà en place)
- **Branche prod** : main / shopify-setup-oxygen-workflow-qwu2

## État Boutique Shopify (27 Mai 2026)
- **21 produits** en statut DRAFT — SEO en cours
- **35 alt texts SEO** mis à jour (Collection L'Éclipse)
- **Collections** : L'Éclipse, Prêt-à-porter, Accessoires
- API Shopify Admin REST 2024-01 opérationnelle

## Objectif Business
Lionel est en reconversion, souhaite vivre de la boutique en ligne. Priorités :
1. Storefront fonctionnel et performant
2. Automatisation marketing (email, social, SEO)
3. Prospection et acquisition clients
4. Rivaliser avec les meilleures boutiques sportswear DTC

## Concurrents de Référence
- **Gymshark** — email automation, UGC, communauté
- **Represent Clothing** — drops limités, scarcité planifiée
- **Lululemon** — communauté, data, LTV client
- **Pas Normal Studios** — premium SEO, niche ciblée
- **OFF-WHITE, A-COLD-WALL** — positionnement haut de gamme

## Agents IA disponibles

| Agent | Rôle | Session |
|-------|------|---------|
| **Claude Code** | Automatisation Shopify, SEO, scripts | Brev.dev cloud |
| **Antigravity** | GitHub, infrastructure, architecture | PC local Lionel |

### Règle de collaboration
- Claude Code crée → demande à Antigravity de pousser si 403
- Antigravity a accès GitHub direct via MCP
- Pour relayer : `"Message pour Antigravity : [message]"`
- En cas de conflit → **Lionel tranche**

## Skills Disponibles
- `/qivera-agent` : Agent senior automatisation boutique
  → voir `.claude/skills/qivera-agent.md`

## Variables d'Environnement Requises
```bash
SHOPIFY_SHOP_URL=qiveravera.myshopify.com
SHOPIFY_ADMIN_API_ACCESS_TOKEN=<voir .env Lionel>
SHOPIFY_API_VERSION=2024-01
```

## Fix Technique En Attente
> `requirements.txt` (branche `openclaw` de QIVERA-VERA-Holding-Repository)
> ```diff
> - python-telegram-bot==20.3
> + python-telegram-bot>=21.0
> ```
> → Débloque le déploiement Vercel `qivera-vera-os`

---
*Mémoire projet — Claude Code session Brev.dev + Antigravity — 27 Mai 2026*
