# Bravo!

**A story of loyalty, love, and reunion.**

*Bravo!* is a story-driven tabletop adventure about beloved toys—called Champions—who awaken after the children they love have gone. The Champions set out across a world made for humans to find the twins again.

This repository contains the browser-based companion for the campaign. It is an in-development prototype, not a finished release.

## Current build

**v5.50** includes Scenes 00–06, Champion selection and sheets, a GM interface, player views, and synchronized GM roll requests and results for up to six selected Champions. Requests and results are shared across devices through Cloudflare Worker and D1. Some other game state remains local to the browser.

## Playtesting with GitHub Pages

1. Put the v5.50 campaign HTML at the repository root and rename it `index.html`.
2. In **Settings → Pages**, deploy from the `main` branch and `/(root)`.
3. Deploy the matching Cloudflare Worker (`Bravo_Worker_v5_50.js`) and additive D1 migration (`Bravo_v5_50_D1_Additive_Migration.sql`) separately. Keep the existing Worker bindings and secrets.
4. Open the published site on the GM's desktop. Connect to the campaign and generate a player join code.
5. Open the Player View link on each player's device, choose an available Champion, and join with the player code. Only the GM should use the private GM test token.

The frontend currently calls `https://bravo-api.atomiclndry.workers.dev`. Cross-device features require the matching Worker and D1 schema to be deployed; GitHub Pages alone does not provide synchronization.

**Security:** Never commit API keys, test tokens, player join codes, or private campaign data. Anything embedded in a public GitHub Pages HTML file can be inspected by visitors.

## Licensing

We want *Bravo!* to be easy to play, study, remix, and build upon, with clear attribution and ownership boundaries:

- **Software:** HTML, CSS, JavaScript, and other original application code are offered under the [MIT License](https://opensource.org/license/mit). Retain the required copyright and license notices when redistributing the code.
- **Original creative works:** Campaign writing, worldbuilding, character descriptions, and artwork **owned by the rights holder and eligible for sublicensing** are offered under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). Give appropriate credit, link to the license, and indicate changes. Commercial adaptations are permitted.
- **Name and branding:** These licenses do **not** grant trademark rights to the *Bravo!* name, logo, or other identifying marks, or permission to imply official endorsement.
- **Third-party materials:** Music, fonts, images, and other third-party content are **not relicensed** by this README. Their own licenses and permissions govern their use.

If code and artwork are bundled into the same HTML file, the MIT grant applies to the **code**, while CC BY 4.0 applies only to the **eligible original creative material** described above. This separation does not override third-party rights.

## Status

Prototype / active playtesting. The v5.50 synchronization has been locally tested but should be verified on separate devices against the deployed Cloudflare backend.
