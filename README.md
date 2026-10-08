# Yale Applied Physics Funding Finder

Grants, fellowships, industry calls, user-facility time and student programs for the Yale Department of Applied Physics: quantum information, photonics, condensed matter and quantum materials, materials science, devices, energy and physical biology.

- **Live page (updated automatically):** https://chiaramingarelli.github.io/yale-applied-physics-funding-finder/
- **This repository:** a self-contained copy you can read, download or host yourself.

## Use it

`index.html` is a single file with all its data built in. Open it in a browser, or publish it with GitHub Pages (Settings → Pages → Deploy from branch → `main`, folder `/`).

The live page and any copy you host yourself have the same features, including:

- filters by research area, career stage, status, type and deadline window
- a **New** tag on programs added in the last 7 days ("New this week", or search for `new`)
- tick boxes to export only the programs you care about as a calendar file (`.ics`, with reminders 6 and 4 weeks before each deadline) or a CSV
- per-program **Google Calendar**, **Outlook** and **Apple Calendar** links

## Data

`data/programs.json` has 476 programs, each taken from the funder's or employer's own page or from an academic job board such as Academic Jobs Online. Main fields: `n` name, `f` funder, `c` type, `s` status (open, rolling or watch), `d` next deadline, `dt` deadline note, `a` award, `e` eligibility and notes, `u` official link, `stages` (ug undergraduates, gr graduate students, pd postdocs, tt tenure-track faculty, ten tenured faculty), `added` date added, `checked` date last checked, `unv` anything that could not be confirmed.

`engine/export_ap.py` builds the page's data from the shared catalog (rows tagged `ap`). `engine/export_mod.js` is the export and calendar-link code inlined in the page.

This site is rebuilt automatically from the shared catalog in [funding-finders](https://github.com/ChiaraMingarelli/funding-finders) and copied here automatically a few times a day, so this page can be several hours behind the shared catalog. Don't edit `index.html` or `data/programs.json` here; the next update replaces them. The catalog is rechecked every Monday, new postings are added on the other days of the week, and the "What changed" notes are kept current daily. Deadlines move, so check the funder's page before you commit to a date.

## License

The code (the scripts in the page and in `engine/`) is released under the [MIT License](LICENSE). The catalog (`data/programs.json`), the data embedded in the page and the page text are released under [CC BY 4.0](LICENSE-DATA), so you can reuse them with credit to Chiara Mingarelli. Program details come from each program's official posting; check there before relying on a date.
