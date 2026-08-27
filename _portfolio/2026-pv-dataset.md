---
title: "Comprehensive Multi-Technology PV Operational and Environmental Characterization Dataset"
collection: portfolio
permalink: /portfolio/2026-pv-dataset
excerpt: "A 4-year, 1.7M+ sample dataset synchronizing PV electrical and environmental measurements from an outdoor solar lab in Lima, Peru.<br/><img src='/images/portfolio/pv-dataset/pv_lab_a.jpg' width='400'>"
date: 2026-02-01
# organizer: "TODO: organizer name"
header:
  teaser: "/images/portfolio/pv-dataset/pv_lab_a.jpg"
link: "https://ieee-dataport.org/documents/comprehensive-multi-technology-pv-operational-and-environmental-characterization-dataset"
tags:
  - Solar Energy
  - Dataset
  - Machine Learning
  - Photovoltaics
---

## Overview

A comprehensive, open dataset for data-driven photovoltaic (PV) research, published on IEEE DataPort. It comprises **over 1.7 million samples collected across four years (2022–2025)** at the Outdoor Photovoltaic Research Laboratory of the Pontificia Universidad Católica del Perú (PUCP) in Lima, Peru (12°04′ S, 77°04′ W).

The dataset synchronizes PV performance and ambient measurements across **20 modules/configurations spanning multiple PV technologies** (mono- and bifacial; PERC, HIT, HJT, TOPCon, and others), making it well suited to train and benchmark AI-driven, technology-agnostic models for energy management and fault diagnosis.

**Authors:** Salvador Yabar, Michael Garcia Huamaní, Carlos Paragua-Macuri.

## What's in the dataset

- **Electrical data** derived from measured current–voltage (I–V) curves: voltage, current, and power at the maximum power point (Vmpp, Impp, Pmpp), short-circuit current (Isc), open-circuit voltage (Voc), series and shunt resistances (Rs, Rsh), and fill factor (FF).
- **Environmental data:** irradiance at multiple orientations (horizontal, tilted 15°/20°, vertical east/west, reflected, diffuse), spectral distribution, module and ambient temperature, relative humidity, air density, absolute pressure, and wind speed/direction.
- **Two files:** `PV_dataset.csv` (>1.7M time-series records) and `module_metadata.csv` (datasheet and installation info for the 20 modules/configurations), joinable on `module_name`.

## Measurement setup

Data was collected with a custom capacitive-load I–V curve tracer synchronized to a full monitoring system, sequentially measuring up to 15 modules at 5-minute intervals per module. Instrumentation includes EKO MS-80 pyranometers, an EKO MS-711 spectroradiometer (300–1100 nm), Class B PT100 module-temperature sensors, a Lufft WS500-UMB weather station, and Keysight 34465A digital multimeters.

<figure>
  <img src="/images/portfolio/pv-dataset/pv_lab_a.jpg" alt="Monofacial and bifacial PV test stations at the PUCP outdoor solar laboratory">
  <figcaption>Outdoor PV test stations at PUCP, including monofacial modules at a 20° north-facing tilt.</figcaption>
</figure>

<figure>
  <img src="/images/portfolio/pv-dataset/pv_lab_b.jpg" alt="Bifacial PV test stations at the PUCP outdoor solar laboratory">
  <figcaption>Bifacial PV module test stations (tilted 15° north-facing and vertical east–west configurations).</figcaption>
</figure>

## Tools & Technologies

Python 3.11, Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn. The processing pipeline (raw-data extraction, curation, and sample use cases) is provided as Jupyter notebooks.

## Links

- 📊 **IEEE DataPort:** [Dataset page](https://ieee-dataport.org/documents/comprehensive-multi-technology-pv-operational-and-environmental-characterization-dataset)
- 🔗 **Data DOI:** [10.21227/N4Y0-9T54](https://doi.org/10.21227/N4Y0-9T54)
- 💻 **Processing code:** [github.com/slava-yr/PUCP-Inti-Data](https://github.com/slava-yr/PUCP-Inti-Data)
- 🔗 **Code DOI:** [10.5281/zenodo.18665161](https://doi.org/10.5281/zenodo.18665161)
- 📄 **Accompanying data descriptor (unpublished draft):** [Download PDF](/files/PV_Dataset/PV_Dataset_Data_Descriptor.pdf)

**License:** [Creative Commons Attribution 4.0 (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
