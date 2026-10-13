# 🚀 Featured Projects

> A selection of mobile applications and software projects I've built and contributed to across different domains. Most repositories are private; the descriptions below cover what each one does and how it's built.

---

## 🔒 Athar — mapping how organizations actually work

🌐 **[athar.omk-software.com](https://athar.omk-software.com)**

**Next.js · PostgreSQL · AI agents · SaaS · In development**

Athar runs AI-guided interviews with an organization's employees, turns what they say into workflow maps, and recommends a digital transformation plan backed by evidence. It's built for consultants and partners who run these studies for nonprofits and other organizations. Every recommendation cites a participant quote and a metric computed in code. Recommendations start with the cheapest change that works, such as a new practice or better use of existing tools, before anything gets built, and every report includes a "what works well" section.

- **Interviews:** a mobile-first chat with voice notes for participants, plus speech-to-text, process extraction and cross-interview merging that run as background jobs.
- **Multi-tenant by design:** each workspace is a tenant, and Postgres row-level security enforces isolation for every role. Org managers see only an anonymized "current picture" through dedicated SQL views, and an RLS test suite covers every table and role.
- **Provider-agnostic AI:** agents call one interface, so the provider and model for each agent (Anthropic, OpenAI or Google) come from config. Prompts are versioned per language, every output is validated with Zod, and an eval suite gates every new model or prompt.
- **White-label and multilingual:** each workspace sets its own name, logo, colors and email sender, including a mode that removes all vendor branding. Arabic RTL ships first, and adding a language needs only translations, prompts and evals, with no code changes.

*Next.js 16, TypeScript, Supabase/PostgreSQL with RLS, Drizzle, pg-boss workers, next-intl, Zod, Vitest and Playwright, Docker.*

---

## Lamm — a family of local-first mobile tools

Small, focused utilities that do their work on the device. No accounts, no uploads, no ads. Each app ships in English and Arabic with full RTL support, and they share one design system and one set of common building blocks.

<table>
<tr>
<td width="50%" valign="top">

### 🔒 lamm.photocleaner

**Flutter · Android · iOS**

Frees up storage by finding what the gallery hides: duplicate and near-identical photos, old screenshots, and oversized videos. Scanning runs entirely on the device, results are grouped for review, and every group shows how much space it returns before anything is deleted.

*Flutter, on-device media indexing, English/Arabic with RTL.*

</td>
<td width="50%" valign="top">

### 🔒 lamm.pdf

**Flutter · Android · iOS · In development**

A full PDF toolkit that never uploads a file: scan paper to PDF, fill and sign, reorder, merge and split, compress to a target size, make scans searchable with OCR including Arabic, protect with a password, watermark, number pages and redact. Signatures are stored encrypted in the device keystore, and every edit keeps a restorable version of the original.

*Flutter, PDFium rendering, platform OCR with a Tesseract fallback for Arabic.*

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🔒 lamm.qr

**Flutter · Android first, iOS next · In development**

A QR and barcode app built on two ideas: scanning stays free and safe, and generated codes have to actually scan. It reads every common 1D/2D format and understands what it read — Wi-Fi, contacts, events, product barcodes, GS1 batch and expiry data, EMVCo and SEPA payment codes, Saudi e-invoices — then offers the one action that makes sense. Links are risk-checked before they open. The designer adds logos, shapes and frames while a live scannability check decodes the result on every change, with SVG, PDF and print-sheet output.

*Flutter, custom QR renderer with Canvas/SVG/PDF parity, pure-Dart payload parsers.*

</td>
<td width="50%" valign="top">

### 🔒 lamm.kit

**Flutter package**

The shared foundation behind the apps: design tokens for both themes, localized components, the paywall and entitlement layer, settings, app lock, analytics and remote configuration. Versioned by tag so each app upgrades deliberately, and one brand fix reaches all of them.

*Flutter, Riverpod, RevenueCat, Firebase.*

</td>
</tr>
</table>

---

## Other projects

<table>
<tr>
<td width="50%" valign="top">

### 🔒 nestly-mobile

**Flutter · iOS & Android · Personal finance**

A personal finance app built around your payday cycle instead of the calendar month. It shows what you can safely spend until the next salary and warns you early when you drift off track, with expenses and income by category, budgets and savings goals, multiple wallets and currencies, and a spending forecast. Offline-first: everything works without a connection and syncs when you're back online.

*Flutter, Riverpod, GoRouter, Isar. English, Arabic (RTL) and Turkish.*

</td>
<td width="50%" valign="top">

### 🔒 nestly-backend

**NestJS · Prisma · PostgreSQL**

The API behind Nestly: authentication, cross-device data sync and app version control. Covers wallets, transactions, budgets, goals and users, with a sync endpoint that restores and merges data on a new device, rate limiting, a health check and Swagger docs.

*NestJS, Prisma, PostgreSQL, Firebase Admin auth, deployed on Railway.*

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🔒 ic_giving

**Kotlin · Jetpack Compose · Donations**

Digital giving platform for Islam Channel, covering donation and payment flows, deep links, push notifications, groups and chat.

*Kotlin, Jetpack Compose, Firebase.*

</td>
<td width="50%" valign="top">

### 🔒 Gomarhum-Flutter

**Flutter · Android & iOS · Social**

Cross-platform social app for the beauty industry, with posts, chat and community features.

*Flutter.*

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🔒 maydan-platform

**Web & mobile · Platform**

Platform for running Airsoft fields and game activities, serving both the operations side and the players.

*Web and mobile clients.*

</td>
<td width="50%" valign="top">

### 🔒 terminal-kadikoy

**Flutter · Android**

Mobile app for Kadıköy Terminal with push and local notifications, localization and location-based features.

*Flutter, Riverpod, Dio, Firebase Cloud Messaging.*

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🔒 drive-watch

**Flutter · IoT · Computer vision**

Driver monitoring project combining Raspberry Pi sensors and camera input with on-device machine learning.

*TensorFlow Lite, OpenCV, CNN-based processing, Flutter client.*

</td>
<td width="50%" valign="top">

&nbsp;

</td>
</tr>
</table>

---

### 🔐 A note on private repositories

Most of the work above lives in private repositories, so the source isn't publicly browsable. Happy to walk through architecture, decisions and trade-offs on request.
