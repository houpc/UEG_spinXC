# UEG_spinXC - Finite-Temperature Spin Exchange-Correlation Kernel of the 3D UEG

Variational diagrammatic Monte Carlo data generated for **"Finite-Temperature Spin Exchange-Correlation
Kernel of the Uniform Electron Gas"** by Hou, Li, Deng, and Chen (2026).

Associated manuscript: arXiv:XXXX.XXXXX.

## Conventions

- Rydberg atomic units are used: `hbar = 2 m_e = e^2/2 = 1`.
- `r_s = (3 / 4 pi n)^(1/3)`, `theta = T / T_F`, and `T_F = k_F^2`.
- `k_F = (9 pi / 4)^(1/3) / r_s`; `N_F = k_F / (2 pi^2)`.
- Magnetization operator `M = (n_up - n_down) / 2`.
- Spin kernel `K_xc^-(q; theta) = chi_s^{-1}(q; theta)
  - chi_0^{-1}(q; theta)`.
- Local-field-factor convention: `K_xc^-(q; theta) = -[8 pi / q^2] G^-(q; theta)`.

The primary `data/` tables store `K_xc^-` in Rydberg Bohr^3.

## Files

```
data/                 Primary spin-kernel tables, one CSV per (r_s, theta).
data/convergence/     Auxiliary tables for the convergence checks.
```

The primary spin-kernel grid covers `r_s = 1, 2, 3, 4` and `theta =
1/16, 1/8, 1/4, 1/2, 1, 2, 4, 8`. The additional `r_s = 2`, `theta =
16` file is included as an extra response point.

## Main Tables

### `data/Kxc_rs{R}_theta{T}.csv`

| column | meaning |
| --- | --- |
| `q_over_kF` | momentum in units of `k_F` |
| `Kxc` | spin XC kernel `K_xc^-(q; theta)` in Rydberg Bohr^3 |
| `sigma_Kxc` | one-standard-deviation uncertainty, combining VDMC statistics and the last-order truncation estimate |
| `lambda_opt` | Yukawa screening scale selected by the principle of minimal sensitivity |

### `data/convergence/Kxc_convergence_rs4_theta{T}.csv`

Auxiliary data used for the convergence checks in the Supplemental
Material. Each row gives `K_xc^-` at `r_s = 4` for a specified `theta`,
momentum, screening scale `lambda`, and expansion order `order_N`.

## Citing

If you use this dataset, please cite:

Hou, P., Li, Z., Deng, Y., and Chen, K. *Finite-Temperature Spin
Exchange-Correlation Kernel of the Uniform Electron Gas*, arXiv:XXXX.XXXXX
(2026).

## License

CC0 1.0 Universal; see `LICENSE`.
