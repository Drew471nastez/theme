# Foundation

This repository is a Storelib website. Storelib writes the whole theme here, and a push to `main` comes back into the site as a draft within seconds. Nothing is live until the creator presses Publish.

Start with AGENTS.md if you are an AI agent (Claude Code and Codex read it on their own).

## What is where

| Path | What it is | Read back by Storelib |
| --- | --- | --- |
| config/settings.json | The theme settings' values: colours, fonts, logo, menus. A `config/settings_data.json` in the usual theme shape, `{ "current": { ... } }`, is taken the same way, and what it leaves out stays as it is. | Yes |
| config/settings_schema.json | What the theme settings are: a list of groups of settings. Reorder groups and settings, add your own, change a label, a default or a range, and Theme settings in the builder follow. A Storelib setting keeps its id, type and group. A section reads a setting you add as `theme.settings.<id>`. | Yes |
| templates/<page>.json | Each page's own sections, their settings and blocks, in order. `home.json` is the home page. | Yes |
| sections/header-group.json, footer-group.json | The header and footer, once, for every page. | Yes |
| sections/*.storelib | Every section: Storelib's built-in ones and this site's own. | Yes |
| sections/<type>.json | A built-in section Storelib draws itself. Its schema is here to read. | No |
| blocks/*.storelib | Theme blocks any section can hold. | Yes |
| README.md, AGENTS.md, CLAUDE.md, storelib.json | Written by Storelib each time it sends the theme. | No |

Anything else in this repository is yours, and Storelib leaves it alone.

## Changing a built-in section

Edit it in place, for example `sections/hero.storelib`. Storelib keeps your version as this site's own copy and draws it on this site only; every other Storelib site keeps the built-in one. In the builder it is marked Edited in GitHub, with Reset to Storelib's version. A built-in Storelib draws itself (a `sections/<type>.json` here) changes the same way: write `sections/<type>.storelib` with the same setting ids.

This site has its own copy of 58 built-in files: `sections/about_founder.storelib`, `sections/about_image.storelib`, `sections/about_timeline.storelib`, `sections/back_to_top.storelib`, `sections/blocks_section.storelib`, `sections/breadcrumbs.storelib`, `sections/collection_featured.storelib`, `sections/collections_grid.storelib`, `sections/community_card.storelib`, `sections/contact.storelib`, `sections/course_curriculum.storelib`, `sections/cta_banner.storelib`, `sections/cta_image.storelib`, `sections/cta_simple.storelib`, `sections/faq_accordion.storelib`, `sections/faq_columns.storelib`, `sections/faq_cta.storelib`, `sections/features_cards.storelib`, `sections/features_grid.storelib`, `sections/features_image.storelib`, `sections/hero.storelib`, `sections/hero_centered.storelib`, `sections/hero_product.storelib`, `sections/hero_split.storelib`, `sections/image_grid.storelib`, `sections/main_account.storelib`, `sections/main_login.storelib`, `sections/main_password.storelib`, `sections/main_wishlist.storelib`, `sections/media_collage.storelib`, `sections/media_gallery.storelib`, `sections/media_map.storelib`, `sections/media_video.storelib`, `sections/mobile_bottom_bar.storelib`, `sections/multirow.storelib`, `sections/not_found.storelib`, `sections/page_content.storelib`, `sections/popup.storelib`, `sections/pricing_table.storelib`, `sections/product_featured.storelib`, `sections/product_grid.storelib`, `sections/product_spotlight.storelib`, `sections/promo_announcement.storelib`, `sections/promo_countdown.storelib`, `sections/promo_newsletter.storelib`, `sections/proof_featured.storelib`, `sections/proof_logos.storelib`, `sections/proof_testimonials.storelib`, `sections/reviews_all.storelib`, `sections/reviews_badge.storelib`, `sections/reviews_carousel.storelib`, `sections/reviews_product.storelib`, `sections/reviews_widget.storelib`, `sections/search.storelib`, `sections/testimonials.storelib`, `sections/text_columns.storelib`, `sections/text_image.storelib`, `sections/text_rich.storelib`.

## Adding a section

Add `sections/<type>.storelib` (lower case, digits, `_` and `-`). To put it on a page, add it to that page's `templates/<page>.json` in the same push, or leave that to the creator in the builder. The format is at https://storelib.com/developers/sections, and the schema settings at https://storelib.com/developers/schema.

## When a push does not work

Each push gets a commit status named Storelib, and a comment on the commit lists every file that was not taken, with the line and what to fix. The other files in the same push are still taken. The builder shows the same list on GitHub in Website settings, Connections.
