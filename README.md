## Overall
QM7b dataset is an extension of the QM7 dataset for multitask learning where 13 additional properties
(e.g., polarizability, HOMO and LUMO eigenvalues, excitation energies) have to be predicted at different levels of theory (ZINDO, SCS, PBE0, GW). Additional molecules comprising chlorine atoms are also included, totaling **7211** molecules.

The dataset is composed of two multidimensional arrays **X (7211 x 23 x 23)** and **T (7211 x 14)** representing the inputs (Coulomb matrices) and the labels (molecular properties) and one array names of size 14 listing the names of the different properties.

## Features (Nightly Build)
- Original Entries from QM7b Dataset
- SMILES Strings for Easy Indexing
- Fully Recovered xyz Coordinates
- Transformed JSON Data Structure
- Directly Readable Using Pymatgen

# Data Structure
### JSON dictionary
- Below is the example of the 1st entry- methane molecule in the QM7b dataset
- Full cartesian coordinates are recovered and readable as IMolecule objects in Pymatgen
- QM7b properties are appended at the end of the dictionary
#### Methane ([H]C([H])([H])[H]) Entry

```json
    {
        "@module": "pymatgen.core.structure",
        "@class": "IMolecule",
        "charge": 0,
        "spin_multiplicity": 1,
        "sites":
        [
            {
                "name": "C",
                "species":
                [
                    {
                        "element": "C",
                        "occu": 1
                    }
                ],
                "xyz":
                [
                    0.9981,
                    -0.0026,
                    -0.0046
                ],
                "properties":
                {}
            },
            {
                "name": "H",
                "species":
                [
                    {
                        "element": "H",
                        "occu": 1
                    }
                ],
                "xyz":
                [
                    2.0944,
                    -0.0024,
                    0.0042
                ],
                "properties":
                {}
            },
            {
                "name": "H",
                "species":
                [
                    {
                        "element": "H",
                        "occu": 1
                    }
                ],
                "xyz":
                [
                    0.6324,
                    1.0308,
                    0.0042
                ],
                "properties":
                {}
            },
            {
                "name": "H",
                "species":
                [
                    {
                        "element": "H",
                        "occu": 1
                    }
                ],
                "xyz":
                [
                    0.6256,
                    -0.5297,
                    0.8815
                ],
                "properties":
                {}
            },
            {
                "name": "H",
                "species":
                [
                    {
                        "element": "H",
                        "occu": 1
                    }
                ],
                "xyz":
                [
                    0.6401,
                    -0.5092,
                    -0.9086
                ],
                "properties":
                {}
            }
        ],
        "ae_pbe0": -420.9337343048892,
        "e1_zindo": 36.7680730972,
        "ea_zindo": -3.98613,
        "emax_zindo": 39.6946262426,
        "homo_gw": -14.1341,
        "homo_pbe0": -10.9488,
        "homo_zindo": -16.013,
        "ip_zindo": 15.72523,
        "lumo_gw": 1.087,
        "lumo_pbe0": 0.1323,
        "lumo_zindo": 4.162,
        "p_pbe0": 2.534576,
        "p_scs": 2.43222,
        "SMILES": "[H]C([H])([H])[H]"
    }
```

### Property Rundown
- Keys and units of the values
- Documentation was absent in original QM7b
- **Nightly, 1 key missing**

|  Key            | Description                    | Unit  |
| ------------- | ------------------------------ |    ----  |
| `ae_pbe0`      | Atomization Energy       |  kcal/mole  |
| `e1_zindo`   |  First Excitation Energy   |  eV  |
| `ea_zindo`   |Electron Affinity| eV|
|`emax_zindo` | Maximal Absorption Intensity|  a.u.   | 
|`homo_gw`|HOMO at GW level |eV|
|`homo_pbe0`|HOMO at PBE0 level |eV|
|`homo_zindo`|HOMO at ZINDO level |eV|
|`ip_zindo` | Ionization Potential | eV|
|`lumo_gw`|LUMO at GW level |eV|
|`lumo_pbe0`|LUMO at PBE0 level |eV|
|`lumo_zindo`|LUMO at ZINDO level |eV|
|`p_pbe0`|Polarizability at PBE0 level |eV|
|`p_scs`|Polarizability at SCS level |eV|
|`SMILES`|SMILES representation | -  |
### References

- @article{blum,
  author  = {L. C. Blum and J.-L. Reymond},
  title   = {970 Million Druglike Small Molecules for Virtual Screening in the Chemical Universe Database {GDB-13}},
  journal = "J. Am. Chem. Soc.",
  volume  = 131,
  pages   = 8732,
  year    = 2009
}

- @article{1367-2630-15-9-095003,
  author={Gr{\'e}goire Montavon and Matthias Rupp and Vivekanand Gobre and Alvaro Vazquez-Mayagoitia and Katja Hansen and Alexandre
Tkatchenko and Klaus-Robert M{\"u}ller and O Anatole von Lilienfeld},
  title={Machine learning of molecular electronic properties in chemical compound space},
  journal={New Journal of Physics},
  volume={15},
  number={9},
  pages={095003},
  url={http://stacks.iop.org/1367-2630/15/i=9/a=095003},
  year={2013}
}

- https://github.com/BingqingCheng/linear-regression-benchmarks

### The End
