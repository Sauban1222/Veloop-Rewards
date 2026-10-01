# VELOOP Rewards

VELOOP Rewards is a responsive React dashboard for exploring reward opportunities across the VELOOP ecosystem. Its five banner experiences cover referrals, balance conversion, bonus activities, captcha tasks, and Gem redemption. The current project is a front-end showcase; production wallet, exchange, and task APIs are not connected.

## Banners

- **Refer & Earn** — Invite friends, review reward highlights, and share a referral link or code.
- **Swap Center** — Illustrates conversion between supported VE and SVE balances.
- **Bonus VEs** — Highlights eligible bonus activities with a vault, meter, and task list.
- **Captcha Tasks** — Shows a captcha verification flow with Gem rewards.
- **Exchange Center** — Illustrates one-way Gem redemption into a VE balance payout.

## Technology Stack

- React 19
- Vite 7
- Bootstrap 5
- CSS Modules for component and dashboard styles
- Lucide React for consistent interface icons
- Native CSS illustrations and animations; no remote image assets are required

## Local Development

Requirements: Node.js 20.19+ or 22.12+, and npm.

Install the locked dependencies:

```sh
npm ci
```

Start the development server:

```sh
npm run dev
```

Create and preview a production build:

```sh
npm run build
npm run preview
```

Vite prints the local URL for each server command.

## Project Structure

```text
.
├── index.html
├── package.json
├── package-lock.json
├── vite.config.js
└── src/
    ├── App.jsx
    ├── main.jsx
    ├── assets/
    ├── components/
    │   ├── BonusVEsBanner/
    │   │   ├── BonusVEsBanner.jsx
    │   │   └── BonusVEsBanner.module.css
    │   ├── CaptchaTasksBanner/
    │   │   ├── CaptchaTasksBanner.jsx
    │   │   └── CaptchaTasksBanner.module.css
    │   ├── ExchangeCenterBanner/
    │   │   ├── ExchangeCenterBanner.jsx
    │   │   └── ExchangeCenterBanner.module.css
    │   ├── ReferEarnBanner/
    │   │   ├── ReferEarnBanner.jsx
    │   │   └── ReferEarnBanner.module.css
    │   └── SwapCenterBanner/
    │       ├── SwapCenterBanner.jsx
    │       └── SwapCenterBanner.module.css
    ├── pages/
    │   └── RewardsDashboard.jsx
    └── styles/
        ├── App.module.css
        └── global.css
```

## Responsive Design and Motion

The dashboard stacks all five full-width banners vertically inside Bootstrap `.container-fluid` wrappers. Banner layouts adapt to the available container width, so illustrations and copy reflow in narrow columns as well as on phones. Their viewport-aware minimum heights target 330–520px on mobile, 380–540px on tablet, and 410–450px on desktop. The global page background is `#161827`.

Buttons and links use smooth hover, active, and focus transitions. The Swap Center and Exchange Center include subtle flow animations; the intro also uses a short entrance animation. Motion is reduced when the user enables `prefers-reduced-motion`.

## Asset Paths and Deployment

Run `npm run build` and configure the hosting provider with:

| Setting | Value |
| --- | --- |
| Build command | `npm run build` |
| Publish/output directory | `dist` |

Vite bundles imported CSS and JavaScript into fingerprinted files under `dist/assets/`; the generated `dist/index.html` references those files from the site root. This default Vite base path works for standard root-domain Vercel and Netlify deployments. If deploying under a URL subpath, set Vite's `base` option to that subpath before building. Add future images or fonts under `src/assets/` and import them from source files so Vite can fingerprint and bundle them. The current illustrations are CSS and markup, so they do not depend on external or hard-coded local asset URLs.

## Live Demo

Not deployed yet. Add the published Vercel or Netlify URL here when available, for example: `https://your-project.vercel.app`.

## GitHub Repository

No Git repository or remote is configured in this workspace yet. After creating and pushing the repository, add its URL here, for example: `https://github.com/owner/repository`.