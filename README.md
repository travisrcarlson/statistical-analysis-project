# Land Cleared by Humanitarian Demining in Colombia, Before and After the 2016 Peace Agreement

A statistical analysis in Python of Colombia's official record of humanitarian demining results (5,721 records, 2004–2023), testing whether more land was cleared each month after the 2016 peace agreement than before it.

I chose this question because, in my experience in humanitarian mine action, clearance can go on during a war but is far more effective in peace. Cleared land is not mined again behind the teams, deminers work with more safety and security, and security forces no longer needed for the fighting can take on peace support work such as clearance. This is the second project of my AI capstone on humanitarian mine action.

## Result
The median month cleared 31,722 m² of land in 2010–2016 and 118,107 m² in 2017–2023, about 3.7 times as much. A two-sided Mann–Whitney U test, set out before it was run, found the difference significant (U = 6,314, p < 0.001, rank-biserial correlation 0.79), and the same test on yearly totals agreed (exact p = 0.0006). The data show the rise, not its cause: the number of operators also doubled after 2016.

## What's in this repository
- `analysis.ipynb`: data checks, descriptive statistics, three visual models and their comparison, the hypothesis test and a summary.
- `desminado_humanitario.csv`: the raw dataset, unchanged.
- `figures/`: the three charts, written by the notebook.
- `Statistical_Analysis_Report.pdf` and `module_summary.pdf`: the report. The two files are identical; the brief uses both names.
- `requirements.txt`: the Python environment, from `pip freeze`.

## Dataset
*Situación de Desminado Humanitario en Colombia*, Presidencia de la República de Colombia, Portal Nacional de Datos Abiertos: https://www.datos.gov.co/Inclusi-n-Social-y-Reconciliaci-n/Situaci-n-de-Desminado-Humanitario-en-Colombia/jbqm-s5tn

- Snapshot: `desminado_humanitario.csv`, downloaded on 2026-10-18 from the portal's CSV export (rows last updated by the publisher on 2024-01-19); SHA-256 `eda568a71903f05d7468c582b3795dbd5a537a71c5413f84f72f0acbcffb6617`.
- Licence: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). The CSV file in this repository is shared under the same licence.

## How to run
Needs Python 3.13 and Git. `requirements.txt` was generated on Python 3.13.0.

```
git clone https://github.com/travisrcarlson/statistical-analysis-project.git
cd statistical-analysis-project
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook analysis.ipynb
```

On macOS or Linux, activate with `source .venv/bin/activate`. If PowerShell blocks the activation script, run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` once. In Jupyter, choose **Kernel > Restart Kernel and Run All Cells**.
