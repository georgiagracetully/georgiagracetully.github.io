# georgiagracetully.github.io

Source for my personal website, [georgiagracetully.github.io](https://georgiagracetully.github.io), built with Jekyll using the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template (a fork of Minimal Mistakes).

## Contents

- `_pages/about.md` – home page
- `_portfolio/` – project write-ups (shown under **Projects**)
- `_posts/` – blog posts
- `files/` – CV and project PDFs
- `notebooks/` – Jupyter notebooks and data behind the figures on the project pages:
  - `making_plots/` – cryo-EM heterogeneity clustering of ROOL particles (Summer Project 1)
  - `eternabench_chemmapping_simulation/` – RibonanzaNet vs. 1M7 chemical mapping profiles (Summer Project 2)
  - `sm_data/` – RibonanzaNet-SM small-molecule fine-tuning analysis (Fall Project 1)

Code for fine-tuning RibonanzaNet on EternaBench riboswitch data lives in [RNET-EB](https://github.com/georgiagracetully/RNET-EB).

## Running locally

```bash
bundle install
bundle exec jekyll serve -l -H localhost
```

Then open http://localhost:4000. See the [Academic Pages docs](https://academicpages.github.io/) for details.

## License

Site template: MIT (see `LICENSE`).
