# data-science-portfolio

The GitHub Pages site for my data science portfolio: **https://mc66514.github.io/data-science-portfolio/**

| | |
|---|---|
| Author | GUO XIAOCHEN (MC66514), Class G |
| Course | CISC7204 Analysis of Media and Opinion Data, University of Macau |
| Entry file | `index.md` — GitHub Pages serves it as the website home page |
| Featured project | [data-science-project](https://github.com/Mc66514/data-science-project) |
| Status | completed |

## What is in this repository

```
data-science-portfolio/
├── index.md        # the website: introduction, skills, project showcase
├── figures/        # the two figures embedded in index.md
├── _config.yml     # GitHub Pages / Jekyll configuration (theme: minima)
└── README.md
```

## How it is published

Settings → Pages → *Build and deployment* → **Deploy from a branch** → branch `main`,
folder `/ (root)` → Save. GitHub then builds `index.md` with Jekyll and serves the result at
`https://mc66514.github.io/data-science-portfolio/`.

Images are referenced with relative paths (`figures/...`), so they resolve correctly both on the
live site and when the repository is viewed on github.com.
