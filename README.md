# Neoclassical Growth Model Phase Diagram
An interactive visualization of the phase diagram for the neoclassical (Ramsey-Cass-Koopmans) growth model.

## Quick start

1. Download `neo_growth_phase_diagram.html`.
2. Open it in your browser (Chrome, Firefox, Edge, Safari).
3. Use the left sidebar to set parameters, show/hide curves, and add paths.

> No server, Python, or build step required. Everything runs client‑side in the browser.

## Model
Assumes Cobb-Douglas production function and CRRA utility. The continuous-time dynamics are:

$$\dot{k} = A k^{\alpha} - c - (n+g+\delta)k$$

$$k(0) = k_0$$

$$\frac{\dot{c}}{c} = \frac{1}{\theta}\left[\alpha A k^{\alpha-1} - \delta - \rho\right] - g$$

$$\lim_{t \to \infty} \left\{ k(t) \exp\left(-\int_0^t [\rho - (1-\theta)g - n] ds\right) \right\} = 0$$

### Model Variables
- $k$: Capital per effective labor
- $c$: Consumption per effective labor
- $k^*$: Steady-state capital per effective labor
- $c^*$: Steady-state consumption per effective labor
- $k^{gr}$: Golden rule capital level
- $\bar{k}$: Capital level where $\dot{k}=0$ intersects the k-axis ($c=0$)

### Model Parameters
Fully adjustable economic parameters:
- $A$: Technology level
- $\alpha$: Capital elasticity of output
- $\delta$: Depreciation rate
- $\rho$: Discount rate
- $n$: Population growth rate
- $g$: Technology growth rate
- $\theta$: CRRA utility parameter
- $k_0$: Initial capital stock

## Dependencies

* **Plotly.js** `2.35.2` (MIT) for interactive plotting.
  CDN: `https://cdn.plot.ly/plotly-2.35.2.min.js`
* **MathJax v3 (tex‑svg)** (Apache‑2.0) for LaTeX rendering.
  CDN: `https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js`

Everything else is HTML, CSS, and vanilla JavaScript (ES2015+). No frameworks.

### Offline use

If you need to run fully offline, download the two scripts above and reference them locally in the HTML:

```html
<script src="./plotly-2.35.2.min.js"></script>
<script src="./tex-svg.js" id="mathjax"></script>
```

## Tips and troubleshooting

* If a path seems truncated at large $k$, press **Fit to data** to widen the view.
* For noisy saddle legs, lower **Saddle epsilon (k)** or increase saddle $T$.
* Very large $dt$ can reduce accuracy; prefer increasing $T$ first.

## Contributing

Issues and PRs are welcome.

## License

MIT (see `LICENSE`).
