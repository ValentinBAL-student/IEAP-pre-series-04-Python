# IEAP – Pre-series 04 – Python

Group assignment for the **pre-series 04** of the Python course
(M1 STAPS IEAP – parcours Sport, Santé et Intelligence Artificielle (2SIA), Université de Montpellier).

The goal is to generate a known 3D signal, estimate its time derivative and its tangential speed with numerical methods, check the results against the analytical solution, and display them in an interactive plot.

## Group members

| Member | GitHub | In charge of |
|---|---|---|
| Valentin BALBINE | [@ValentinBAL-student](https://github.com/ValentinBAL-student) | Generate a known signal · Interactive plot (plotly) + HTML export |
| Zoé SAUGE | [@zoesauge](https://github.com/zoesauge) | Time derivative of the signal |
| Damien CLANET | [@damienclanet080805-netizen](https://github.com/damienclanet080805-netizen) | Tangential speed of the signal |

## Contents of the notebook

1. **Generate a known signal**: a 1 Hz sinusoid (amplitude 1) on x, y and z, with a π/4 phase shift between axes. The time vector is a column vector. 2D and 3D plots are made with numpy and matplotlib.
2. **Time derivative of the signal**: analytical derivative of a sine wave and of the signal along each axis, comparison of the forward and central differences (with references), one function per method, and a check of the numerical results against the analytical derivative.
3. **Tangential speed of the signal**: difference between tangential velocity (vector) and tangential speed (scalar), formulas for 3D and nD movements, a `tangential_speed(signal, time)` function, and a test cell with `assert` statements (1D to nD signals, non-uniform sampling, rotation invariance, invalid inputs).
4. **Interactive plot**: the signal and its tangential speed plotted with plotly. The plot can be zoomed in the notebook, in the exported HTML and in a standalone HTML file.
5. **Export**: the notebook is converted to HTML with `nbconvert` for submission on Moodle.

## Files

| File | Description |
|---|---|
| [`IEAP-pre-series-04.ipynb`](IEAP-pre-series-04.ipynb) | Jupyter notebook with all the answers (code + explanations) |
| [`IEAP-pre-series-04.html`](IEAP-pre-series-04.html) | HTML export of the notebook (the file submitted on Moodle) |
| [`signal_tangential_speed.html`](signal_tangential_speed.html) | Standalone interactive plot (signal + tangential speed) |
| [`LICENSE`](LICENSE) | MIT license |

## Viewing the interactive plot

GitHub's notebook preview does **not** run JavaScript, so the plotly figure appears empty when the notebook is opened on GitHub.
To see and zoom the plot, download `signal_tangential_speed.html` or `IEAP-pre-series-04.html` and open it in a web browser. Both files work offline, since plotly.js is embedded in them.

## Running the notebook

**Requirements:** Python 3, Jupyter (or VS Code with the Jupyter extension), and the following packages:

```bash
pip install numpy matplotlib plotly nbformat nbconvert
```

**Steps:**

1. Open `IEAP-pre-series-04.ipynb` and run all cells.
2. Save the notebook (Ctrl+S).
3. Run the last cell to export the notebook to `IEAP-pre-series-04.html`. The export uses the saved version of the notebook.

**Troubleshooting:**

- *The plotly figure does not appear* / `Mime type rendering requires nbformat>=4.2.0`: install `plotly` and `nbformat`, restart the kernel and run all cells again.
- `'jupyter' is not recognized as an internal or external command`: the `jupyter` command is not on the PATH. Run the export with the kernel's own Python instead:
  ```python
  import sys
  !"{sys.executable}" -m nbconvert --to html IEAP-pre-series-04.ipynb
  ```

## Workflow

Each section was developed on its own branch and merged into `main` through a pull request reviewed by the group:

| Branch | Section |
|---|---|
| `01-plot-a-known-signal` | Generate a known signal |
| `section2-derivative` | Time derivative of the signal |
| `03-Estimate-the-tangential-speed-of-the-signal` | Tangential speed of the signal |
| `04-create-an-interactive-plot` | Interactive plot (plotly) |

## Reference

Assignment: *IEAP-Python-Series04-pre*, Denis Mottet, Université de Montpellier (2026).
