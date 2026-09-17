# #Canada @ Undernet

The website for **#Canada** on the Undernet IRC network — a bilingual (English / Français)
Canadian channel. Live at **[undernet.xyz](https://undernet.xyz)**.

[Français ci-dessous](#français)

---

## What's in here

| File | What it is |
| --- | --- |
| `index.html` | The site — landing page, connection guide, client picker, webchat, rules, FAQ |
| `docs.html` | Documentation for **OhCanada**, the channel bot (runs [lmao.tcl](https://github.com/DooubleTap/lmao.tcl)) |
| `CNAME` | GitHub Pages custom domain (`undernet.xyz`) |

Both pages are standalone HTML — CSS and JS are inline, no build step, no dependencies,
no external requests except the client links and the webchat iframe. Open the file in a
browser and what you see is what ships.

## Features

- **Bilingual, for real.** Every string on the page exists in English and French
  (`data-en` / `data-fr` attributes). The EN/FR switch in the header swaps them live and
  remembers the choice in `localStorage`; first-time French-language browsers get French.
- **Webchat on demand.** A KiwiIRC client embeds directly in the page, pre-pointed at
  `#Canada` — but only loads after the visitor clicks, so nobody is silently connected to
  IRC by opening the homepage.
- **Copy-paste connection commands** for `/server`, `/nick` and `/join`.
- **Filterable client list** — Windows, macOS, Linux, web & mobile.
- **Bot documentation** linked throughout and shipped in the same repo.
- Responsive down to phone width, and honours `prefers-reduced-motion`.

## Editing

Everything lives in one file per page. To change copy, edit the element's text **and** its
`data-en` / `data-fr` attributes — the language switch reads from those, so a change made
only to the visible text will be overwritten the moment someone toggles the language.

```html
<h3 data-en="Pick a client" data-fr="Choisis un client">Pick a client</h3>
```

Design tokens (colours, fonts, radii) are CSS custom properties at the top of each file's
`<style>` block. `index.html` and `docs.html` share the same palette — change both if you
change one.

## Local preview

```sh
git clone https://github.com/DooubleTap/undernet-canada.git
cd undernet-canada
python -m http.server 8000     # then open http://localhost:8000
```

Opening `index.html` directly from the filesystem works too.

## Deploying

The repo is served by GitHub Pages from the default branch with the domain in `CNAME`.
Push to the branch and the site updates.

## Channel

```
Server    irc.undernet.org   (ca.undernet.org for the Canadian round-robin)
Ports     6660-6669, 7000    (Undernet does not offer TLS)
Channel   #Canada
Bot       OhCanada
```

## Contributing

Fork, branch, commit in the imperative mood (`Add FAQ entry about bouncers`), open a PR.
Keep both languages in sync — a PR that adds English-only copy will be asked for the
French.

## License

MIT

---

# Français

[Back to English](#canada--undernet)

Le site web de **#Canada** sur le réseau IRC Undernet — un canal canadien bilingue
(anglais / français). En ligne à **[undernet.xyz](https://undernet.xyz)**.

## Contenu du dépôt

| Fichier | Description |
| --- | --- |
| `index.html` | Le site — page d'accueil, guide de connexion, choix de clients, webchat, règles, FAQ |
| `docs.html` | La documentation d'**OhCanada**, le robot du canal (basé sur [lmao.tcl](https://github.com/DooubleTap/lmao.tcl)) |
| `CNAME` | Domaine personnalisé pour GitHub Pages (`undernet.xyz`) |

Les deux pages sont autonomes : le CSS et le JS sont intégrés, aucune étape de compilation,
aucune dépendance.

## Fonctionnalités

- **Vraiment bilingue.** Chaque texte existe en anglais et en français (attributs
  `data-en` / `data-fr`). Le sélecteur EN/FR les échange en direct et retient le choix dans
  `localStorage`; les navigateurs configurés en français arrivent directement en français.
- **Webchat à la demande.** Un client KiwiIRC s'intègre dans la page, déjà pointé sur
  `#Canada` — mais il ne se charge qu'après un clic, pour que personne ne soit connecté à
  IRC sans le vouloir.
- **Commandes de connexion copiables** : `/server`, `/nick`, `/join`.
- **Liste de clients filtrable** — Windows, macOS, Linux, web et mobile.
- **Documentation du robot** liée partout et hébergée dans le même dépôt.
- Adaptatif jusqu'à la largeur d'un téléphone, et respecte `prefers-reduced-motion`.

## Modification

Pour changer un texte, modifie le contenu visible **et** les attributs `data-en` /
`data-fr` — le sélecteur de langue lit ces attributs, donc une modification faite
uniquement sur le texte visible sera écrasée au premier changement de langue.

## Aperçu local

```sh
git clone https://github.com/DooubleTap/undernet-canada.git
cd undernet-canada
python -m http.server 8000     # puis ouvrir http://localhost:8000
```

## Le canal

```
Serveur   irc.undernet.org   (ca.undernet.org pour l'adresse canadienne)
Ports     6660-6669, 7000    (Undernet n'offre pas de TLS)
Canal     #Canada
Robot     OhCanada
```

## Contribution

Fork, branche, commits à l'impératif, puis une pull request. Garde les deux langues
synchronisées — une PR avec du texte uniquement en anglais se fera demander le français.

## Licence

MIT
