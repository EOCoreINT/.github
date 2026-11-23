<div align="center">

# EOCoreINT

**Open research software for Earth observation, from satellite data access to physics-informed radar interferometry.**

[![Website](https://img.shields.io/badge/Website-eocoreint.com-e9660e?style=flat-square)](https://www.eocoreint.com)
[![GitHub](https://img.shields.io/badge/GitHub-EOCoreINT-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/EOCoreINT)
[![X](https://img.shields.io/badge/X-@EOCoreINT-000000?style=flat-square&logo=x&logoColor=white)](https://twitter.com/EOCoreINT)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-EOCoreINT-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/company/eocoreint)
[![License: MIT](https://img.shields.io/badge/License-MIT-2ea44f?style=flat-square)](#license)

</div>

---

EOCoreINT is an open-source research initiative founded by **Samuel Appiah Kubi**, a geospatial engineer from Ghana. We build and validate methods for measuring the Earth's surface from space, with a focus on **InSAR ground-deformation monitoring**, and we release them as tested, documented Python software.

Our work starts from a practical gap: the algorithms exist, but for many institutions in Africa and the Global South the tools to run them do not. They are expensive, tied to one operating system, or scattered across scripts that cannot be reproduced. We close that gap in two ways:

- **Open infrastructure:** software that installs with `pip`, runs natively on Windows as well as Linux, and takes a user from a box on the map to a validated result.
- **Open research:** new methods, physics-informed machine learning for radar interferometry, tested against established baselines on real data and published with their limits stated.

## Research focus

| Theme | Question we work on |
|---|---|
| **Physics-informed InSAR** | Can deep learning respect the physics of the measurement, so that a network's answer is always consistent with the wrapped phase it was given? |
| **Phase unwrapping** | Where do classical cost-flow unwrappers such as SNAPHU fail, and can a learned, physically constrained model complement them locally? |
| **Scatterer selection in low coherence** | Can graph neural networks choose reliable measurement points where classical persistent-scatterer criteria leave too few? |
| **Reproducible EO pipelines** | Can every result be traced to its inputs, settings and software version, and repeated exactly? |
| **Geohazards and subsidence** | Landslides, mining and groundwater-driven subsidence, especially in under-monitored regions. |

**How we validate.** Every method is compared against an established baseline (for example SNAPHU, SBAS) on synthetic data with known truth and on real Sentinel-1 stacks, with independent data such as GNSS where it exists. We report where a method does *not* outperform the baseline as well as where it does.

## Projects

| Project | What it does | Status |
|---|---|---|
| **[pygeofetch](https://github.com/EOCoreINT/pygeofetch)** | One Python API and command line for searching, checking and downloading satellite data from 22+ providers (Copernicus, NASA, USGS, JAXA and others), with a pure-Python Sentinel-1 InSAR processing chain that runs natively on Windows. Records the provenance of every product. | ✅ Stable, public |
| **[pyunwrap](https://github.com/EOCoreINT/pyunwrap)** | Physics-informed deep learning for InSAR phase unwrapping (*AmbiguityNet*): predicts integer cycle counts so that the output always re-wraps to the input phase. Designed as a local complement to SNAPHU and tested on real Sentinel-1 data. | 🔬 Research preview |
| **[ps-gnn](https://github.com/EOCoreINT/ps-gnn)** | Persistent-scatterer selection as node classification on a spatial graph (graph attention networks on k-NN / Delaunay graphs), aimed at low-coherence areas. | 🔬 Research preview |
| **[pygeovision](https://github.com/EOCoreINT/pygeovision)** | Geospatial AI toolkit: segmentation, detection, change detection and embedding models with an audited model registry. | 🔬 Research preview |

**Research previews** are under active validation. Their repositories open once the method has passed validation and the associated paper is submitted, so that the public version is the one that was tested. Until then, researchers can request access (see below).

## Case studies

- **[Mexico City subsidence](https://github.com/EOCoreINT/mexico-subsidence-project):** 67 Sentinel-1 scenes (≈ 500 GB), SBAS time-series inversion of one of the fastest-subsiding cities on Earth, processed end to end with pygeofetch.

More case studies are added as their analyses are completed and checked.

## Publications

Manuscripts describing **pygeofetch** (software) and **pyunwrap** (phase unwrapping) are in preparation. This section will list them with DOIs when they appear. If you use our software before then, please cite the repository and the version you used.

## Reproducibility

- Each project ships a test suite, and the results in our papers come from tagged releases.
- Processing records (`provenance.yaml`) store the settings, input fingerprints and software versions of each run.
- Synthetic benchmarks with known truth ship with the code, so claims can be checked without our data.

## Collaborate with us

We welcome:

- **Validation partners:** run our methods on your data (Sentinel-1 SLC stacks, NISAR, ALOS-2, GNSS) and compare with your own processing.
- **Research collaborations:** joint studies, student projects and benchmarks, from universities, space agencies and monitoring institutions.
- **Contributors:** bug reports, documentation, new data providers and processing steps. Start with the open issues in [pygeofetch](https://github.com/EOCoreINT/pygeofetch/issues).

**Access to research previews:** open an issue in [EOCoreINT/.github](https://github.com/EOCoreINT/.github/issues/new/choose) with the *Research preview access request* form. Tell us your institution, the repository, your use case, your data and your GitHub username.

## Learning

Free courses at **[eocoreint.com](https://www.eocoreint.com)**, from satellite-data fundamentals to InSAR time series and physics-informed neural networks, built on the same open tools.

## Acknowledgements

Our work depends on open data and open science: the European Space Agency and the Copernicus Programme, NASA Earthdata and the Alaska Satellite Facility, USGS, JAXA, ISRO, INPE, Microsoft Planetary Computer and Earth on AWS, and the open-source geospatial community (GDAL, rasterio, PyTorch, SNAPHU, ISCE and many others).

## License

Our public projects are released under the **MIT License** unless a repository states otherwise.

<div align="center">

*Built in Africa, for open science everywhere.*

</div>
