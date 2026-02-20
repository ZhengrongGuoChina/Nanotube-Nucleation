# Nanotube Nucleation

**Carbon Nanotube Cap Structure Generator**

## Introduction

**Graphene-Topology** (Zhengrong Guo 2024-2025) is a C++ header-only library for graphene topology analysis and carbon nanotube cap generation. **Nanotube-Nucleation** provides a Qt-based graphical interface for cap structure generation and visualization. This tool enables researchers to design, analyze, and visualize carbon nanotube cap structures.

### Features

| Feature | Description |
|---------|-------------|
| **Precise Topology Control** | Define pentagon positions in graphene lattice using 12 chiral indices |
| **3D Visualization** | Interactive 3D visualization of generated structures |
| **Advanced Analysis** | Tools for symmetry analysis and lattice coordination verification |
| **Multiple Export Formats** | XYZ, MOL2, LAMMPS, POSCAR, PDB |

## Cap Structure Fundamentals

A carbon nanotube cap is defined by **six pentagons** embedded in a hexagonal graphene lattice. Each pentagon position is specified by two chiral indices (nᵢ, mᵢ), resulting in **12 indices total**:

```
Cap Structure: [(n₁, m₁), (n₂, m₂), (n₃, m₃), (n₄, m₄), (n₅, m₅), (n₆, m₆)]
```

- Each (nᵢ, mᵢ) tuple specifies pentagon position in rotational lattice coordinates
- Coordinates define topological arrangement within graphene sheet
- Allows systematic exploration of all possible cap configurations

## Chirality Connection: Vector Sum Rule

The chirality of the resulting carbon nanotube is determined by the **vector sum** of all pentagon positions:

```
n = Σ nᵢ = n₁ + n₂ + n₃ + n₄ + n₅ + n₆
m = Σ mᵢ = m₁ + m₂ + m₃ + m₄ + m₅ + m₆
```

where **(n, m)** is the chiral vector of the resulting nanotube.

> **Implementation Note:** Pentagon positions are specified in rotational sub-lattice coordinates, representing topological relationships. For computational efficiency, all nᵢ-values must be positive, while mᵢ-values may be positive or negative. This convention enables systematic discovery of all cap configurations while maintaining computational tractability.

## Usage

### Basic Workflow

1. **Define Cap Structure**: Enter 12 chiral indices in the input fields. Click `Generate Cap` to create the initial cap structure.

2. **3D Visualization**: The generated cap structure appears in the interactive 3D viewer. Use mouse controls to rotate, zoom, and pan.

3. **Nanotube Growth**: Specify hexagon incorporation parameters. Click `Grow` to extend the cap into a complete carbon nanotube.

4. **Save and Export**: Save structures in various formats via **File → Save**, or render 3D views to PNG images using **File → Render**.

### Mouse Controls (3D Viewer)

| Action | Control |
|--------|---------|
| Rotate | Left mouse button + drag |
| Pan | Right mouse button + drag |
| Zoom | Mouse wheel |
| Reset View | Middle mouse button |

### Export Formats

| Format | Extension | Description |
|--------|-----------|-------------|
| XYZ | `.xyz` | Simple coordinate format |
| MOL2 | `.mol2` | Tripos molecular format |
| LAMMPS | `.lammps` | LAMMPS data file |
| POSCAR | `.poscar` | VASP structure file |
| PDB | `.pdb` | Protein Data Bank format |

## Advanced Tools

### Network Homotopic Topology Tool

This tool performs **homotopic edge migration** on carbon network edges. By managing a closed path of topological vectors, it provides precise control over hexagon addition locations, enabling detailed manipulation of lattice connectivity and edge configurations.

**Use cases:**
- Studying catalyst residue effects on cap formation
- Systematic exploration of growth pathways

### Cap Search by Chirality

This tool systematically searches **all possible cap configurations** for a given nanotube chirality. Due to symmetry considerations, all possible chiral representations must be explored, with hash algorithms used to remove duplicates.

> **Note:** This process can be computationally intensive, especially for larger chiral indices.


## Theoretical Framework

This software implements the theoretical framework for **deterministic nucleation and chirality control** in nanotube synthesis.

### Primary Reference

> Zhengrong Guo, "Toward a Deterministic Nucleation Theory for Chirality‑Controlled Nanotube Synthesis", *arXiv:2510.25425v2* [cond-mat.mes-hall]

## License

**Copyright © 2025-2026 Zhengrong Guo**

This software is provided for **academic and research purposes**.

## Acknowledgements

- Qt interface developed with assistance from **DeepSeek AI**
- LCBOPII potential implementation based on Los & Fasolino papers

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Contact

For questions or collaboration opportunities, please contact:
- **Email:** zhengrong_guo@yulinu.edu.cn
- **Institution:** Yulin University


