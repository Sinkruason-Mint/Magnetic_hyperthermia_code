# Magnetic Hyperthermia Simulation

A comprehensive Python-based simulation of magnetic hyperthermia treatment for cancer therapy, designed to run in Jupyter notebooks and Google Colab.

## Overview

Magnetic hyperthermia is a cancer treatment technique where magnetic nanoparticles (typically magnetite Fe₃O₄) are injected into tumor tissue and heated using an alternating magnetic field (AMF). This simulation models the heat generation and temperature evolution using fundamental physical equations.

## Features

- **Physical Modeling**: Implements accurate physics-based equations for magnetic hyperthermia
  - Specific Absorption Rate (SAR) calculations using Linear Response Theory (LRT)
  - Néel and Brownian relaxation mechanisms
  - Bio-heat equation for temperature evolution
  
- **Parametric Studies**: Analyze the effect of various parameters:
  - Magnetic field amplitude and frequency
  - Nanoparticle size and concentration
  - Tissue properties and heat loss
  
- **Visualization**: Comprehensive plots including:
  - SAR vs. frequency and magnetic field
  - Temperature evolution over time
  - Parametric sensitivity analyses

## Physical Equations

### 1. Specific Absorption Rate (SAR)

Using Linear Response Theory:

```
SAR = π μ₀ χ₀ H² f × (2πfτ) / (1 + (2πfτ)²)
```

Where:
- `μ₀` = permeability of free space (4π × 10⁻⁷ H/m)
- `χ₀` = equilibrium magnetic susceptibility
- `H` = magnetic field amplitude (A/m)
- `f` = frequency (Hz)
- `τ` = relaxation time (s)

### 2. Temperature Evolution

Bio-heat equation (simplified):

```
ρ Cₚ dT/dt = SAR × c_NP - k(T - T₀)
```

Where:
- `ρ` = tissue density (kg/m³)
- `Cₚ` = specific heat capacity (J/kg·K)
- `c_NP` = nanoparticle concentration (kg/m³)
- `k` = heat loss coefficient
- `T₀` = body temperature (37°C)

## Usage

### Google Colab (Recommended)

1. Open the notebook in Google Colab:
   - Go to [Google Colab](https://colab.research.google.com/)
   - Upload `magnetic_hyperthermia_simulation.ipynb`
   - Or use: File → Upload notebook

2. Run all cells sequentially (Runtime → Run all)

3. Modify parameters as needed:
   - Particle diameter (10-25 nm typical)
   - Magnetic field (5-30 kA/m)
   - Frequency (100-500 kHz)
   - Nanoparticle concentration (1-10 kg/m³)

### Local Jupyter Notebook

1. Install required packages:
```bash
pip install numpy matplotlib scipy
```

2. Launch Jupyter:
```bash
jupyter notebook magnetic_hyperthermia_simulation.ipynb
```

3. Run the cells sequentially

## Parameters

### Default Configuration

| Parameter | Value | Unit | Description |
|-----------|-------|------|-------------|
| Particle diameter | 15 | nm | Magnetite nanoparticle size |
| Magnetic field | 15 | kA/m | AMF amplitude |
| Frequency | 300 | kHz | AMF frequency |
| NP concentration | 5.0 | kg/m³ | Nanoparticle concentration in tissue |
| Treatment time | 30 | minutes | Duration of hyperthermia |
| Target temperature | 43 | °C | Therapeutic target |

### Material Properties (Magnetite Fe₃O₄)

- Saturation magnetization: 446 kA/m
- Anisotropy constant: 13.5 kJ/m³
- Density: 5200 kg/m³

## Clinical Considerations

### Therapeutic Window
- **Target range**: 41-46°C
- **Optimal**: 43°C
- **Treatment duration**: 30-60 minutes

### Safety Limits
- **Brezovich criterion**: H × f < 5×10⁹ A·m⁻¹·s⁻¹
- Maximum tolerable field-frequency product to avoid eddy current heating in healthy tissue

## Results

The simulation provides:

1. **SAR calculations**: Power absorption by nanoparticles
2. **Temperature profiles**: Time evolution of tissue temperature
3. **Optimization plots**: SAR vs. frequency and field amplitude
4. **Parametric studies**: Effect of particle size and concentration

## Scientific Background

### Key Phenomena

1. **Néel Relaxation**: Internal magnetization rotation
   - Dominant for small particles (< 15 nm)
   - Exponentially dependent on particle volume

2. **Brownian Relaxation**: Physical particle rotation
   - Dominant for larger particles
   - Depends on viscosity and hydrodynamic volume

3. **Heat Transfer**: Balance between generation and loss
   - Heat generation: SAR × concentration
   - Heat loss: Blood perfusion, thermal conduction

## References

1. Rosensweig, R. E. (2002). "Heating magnetic fluid with alternating magnetic field." *Journal of Magnetism and Magnetic Materials*, 252, 370-374.

2. Hergt, R., & Dutz, S. (2007). "Magnetic particle hyperthermia—biophysical limitations of a visionary tumour therapy." *Journal of Magnetism and Magnetic Materials*, 311(1), 187-192.

3. Carrey, J., Mehdaoui, B., & Respaud, M. (2011). "Simple models for dynamic hysteresis loop calculations of magnetic single-domain nanoparticles." *Journal of Applied Physics*, 109(8), 083921.

4. Dutz, S., & Hergt, R. (2014). "Magnetic particle hyperthermia—a promising tumour therapy?" *Nanotechnology*, 25(45), 452001.

## License

This code is provided for educational and research purposes.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## Author

Created for magnetic hyperthermia research and education.