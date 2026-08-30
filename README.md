# Sabina Stefan Oller — Quarto personal website

This repository contains a Quarto portfolio designed for GitHub Pages. Its public navigation is intentionally concise:

- Home
- Research / Projects
- Google Scholar
- Downloadable CV

The selected-publications and web-CV source pages are retained in the project but are not shown in the primary navigation.

The draft is intentionally positioned around current machine-learning work. MANTIS and therapeutic-target-discovery research lead; earlier OCT, vascular-imaging, and EEG work remains available as previous research. The visual direction is deliberately personal and editorial: a short first-person introduction, an existing public headshot, and text-led lists in place of portfolio cards or company-style feature sections.

## Preview locally

Install [Quarto](https://quarto.org/docs/download/) and run:

```bash
quarto preview
```

The production build is created with:

```bash
quarto render
```

## Recommended GitHub repository

The working default is:

```text
sstefan01/sabinastefan.com
```

If a different repository name is preferred, no site code needs to change. Create the repository on GitHub, then from this folder run:

```bash
git init
git add .
git commit -m "Create Quarto personal website"
git branch -M main
git remote add origin https://github.com/sstefan01/sabinastefan.com.git
git push -u origin main
```

In GitHub, open **Settings → Pages** and select **GitHub Actions** as the source. Every push to `main` will then rebuild and publish the site.

## Custom domain: www.sabinastefan.com

The repository includes a `CNAME` file as a portable record of the intended domain. Because this project uses a custom GitHub Actions workflow, GitHub requires the domain to be set in the repository’s Pages settings; the file alone does not configure it.

After the GitHub Pages deployment works at its temporary `github.io` address:

1. In **Settings → Pages**, enter `www.sabinastefan.com` under **Custom domain**.
2. At the DNS provider, set the `www` record to:

   | Type | Host | Value |
   |---|---|---|
   | CNAME | `www` | `sstefan01.github.io` |

3. To make the apex domain (`sabinastefan.com`) redirect correctly too, add GitHub’s apex records:

   | Type | Host | Value |
   |---|---|---|
   | A | `@` | `185.199.108.153` |
   | A | `@` | `185.199.109.153` |
   | A | `@` | `185.199.110.153` |
   | A | `@` | `185.199.111.153` |

   Optional IPv6 records:

   | Type | Host | Value |
   |---|---|---|
   | AAAA | `@` | `2606:50c0:8000::153` |
   | AAAA | `@` | `2606:50c0:8001::153` |
   | AAAA | `@` | `2606:50c0:8002::153` |
   | AAAA | `@` | `2606:50c0:8003::153` |

4. Wait for GitHub to verify the records, then enable **Enforce HTTPS**.

Keep the Google Sites version live until the GitHub Pages URL has been checked. The DNS change is the final cutover and can be reversed by restoring the old records.

## Content to update before launch

- Confirm the full publication list and any accepted/in-press wording.
- Replace the included CV PDF whenever a newer version is available.
- Publication citations retain the author name “Sabina Stefan,” while the site identity uses “Sabina Stefan Oller.”
- Confirm whether to keep the headshot reused from the current Google Site and whether any project figures should be added.
- Confirm the repository name and DNS provider before the domain cutover.
