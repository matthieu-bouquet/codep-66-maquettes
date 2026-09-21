# Stack technique — site CODEP 66

Décisions pour l’implémentation du site (après phase maquettes HTML).

## Référence architecture

S’inspirer de [les-archers-de-bompas](https://github.com/matthieu-bouquet/les-archers-de-bompas) (structure `src/`, Sanity `studio/`, Cloudflare Pages, webhooks rebuild), **sans recopier les versions figées** du club Bompas.

## Frontend

| Choix | Détail |
|--------|--------|
| **Astro** | **Version 7** (dernière majeure au moment du projet). Ne pas initialiser en Astro 6. |
| **CSS** | Tailwind CSS 4 avec `@theme` dans `src/styles/global.css` |
| **Contenu riche** | Portable Text Sanity → HTML côté build / SSR selon routes |
| **SEO** | `@astrojs/sitemap`, métadonnées par page |

Lors du scaffold : `npm create astro@latest` (ou équivalent) en visant **Astro 7**, puis aligner `@astrojs/cloudflare` et les autres intégrations sur les versions compatibles indiquées par la doc Astro 7.

## CMS

- **Sanity** — Studio dédié CODEP (`studio/`)
- Types prévus (évolution Bompas) : actualités, bureau, documents (CR / officiels), **clubs** (annuaire + fiche sans site externe), paramètres site

## Hébergement & ops

- **Cloudflare Pages** + adapter **`@astrojs/cloudflare`**
- **Turnstile** si formulaire contact
- **Resend** (optionnel) pour e-mails transactionnels
- Webhook Sanity → rebuild Cloudflare à chaque publication

## Node

- Suivre la version minimale recommandée par Astro 7 au moment de l’init (à fixer dans `.nvmrc` à la création du repo).

## Maquettes

Phase actuelle : HTML standalone dans `design/mockups/` (pas de build Astro).

---

*Dernière mise à jour : septembre 2026 — décision Astro 7 validée avec le porteur projet.*
