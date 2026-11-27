# POLARIS tutorial notebooks

Teaching notebooks for preparing POLARIS inputs and working with synthetic observations.

## Notebooks

| Notebook | Purpose |
| --- | --- |
| [Grid-hdf5.ipynb](polarisTutor/Grid-hdf5.ipynb) | Extract a region from an AREPO snapshot and prepare a Voronoi grid and a Cartesian line-emission task. |
| [combine.ipynb](polarisTutor/combine.ipynb) | Combine Cartesian velocity-channel FITS files into PPV cubes and inspect the results. |
| [POLARIS_HEALPix_to_IQU.ipynb](polarisTutor/POLARIS_HEALPix_to_IQU.ipynb) | Convert the example native dust HEALPix output into an explicit I/Q/U/V FITS table and display the four Stokes maps. The historical filename is retained. |

## Start

```bash
python -m pip install -r requirements.txt
jupyter lab
```

The original grid notebook additionally requires the simulation-specific `arepy` and `sf3dmodels` packages. Install the versions appropriate to your simulation separately; they are not bundled here. POLARIS itself must also be installed separately.

Update the local snapshot, grid, gas-species, template-header, input and output paths before use. Run notebook cells in order. Input snapshots and simulation outputs are not included. Saved execution outputs have been cleared from the published copies.

## Scope and conventions

- These are teaching/research notebooks, not a fully automated or engine-certified pipeline.
- `Grid-hdf5.ipynb` and `combine.ipynb` retain the original executable code, including experiment-specific regions, velocity ranges, crops, and optional exploratory cells. Review these settings and cells for your dataset.
- The HEALPix conversion is for the example single-wavelength native RING dust output in Jy/pixel. It converts to MJy/sr, keeps total I without background subtraction, and does not interpolate or smooth the FITS data.
- The example longitude transformation and Q/U sign changes follow this workflow's native coordinate convention. V retains its native POLARIS sign; do not assume these conventions apply to every POLARIS configuration.
- The resulting table retains native pixel identifiers, which are not standard Galactic HEALPix indices. Use the explicit longitude and latitude columns.
- Existing output files may be overwritten by the notebook code.
