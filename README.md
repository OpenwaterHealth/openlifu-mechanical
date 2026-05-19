# openlifu-mechanical

Mechanical design files (CAD models, assemblies, and drawings) for the **Open-LIFU** open-source Low-Intensity Focused Ultrasound research platform.

Open-LIFU is an open hardware/software stack developed by [Openwater](https://www.openwater.health/openlifu) for focused-ultrasound research and neuromodulation. This repository hosts the mechanical artifacts you need to build, modify, or interface with the system — transducer housings, console enclosures, transmit modules, and verification-tank fixtures.

---

## Contents at a glance

| Folder / File                 | What's in it                                                 |
| ----------------------------- | ------------------------------------------------------------ |
| **`Configured Transducers/`** | 3D models of fully assembled ultrasound transducers, including housings and transmit electronics. Use these when you want a drop-in transducer model for system integration or simulation. |
| **`Key Part Assemblies/`**    | 3D models of major sub-assemblies — Console, Housings, Transmit Modules. Use these when you need a constituent piece rather than a complete transducer. |
| **`Verification Tank/`**      | Fixtures and interconnects for the [openlifu-verification-tank](https://github.com/OpenwaterHealth/openlifu-verification-tank) acoustic-field characterization system. |
| **Top-level `.zip` files**    | Standalone part assemblies. Each zip typically contains the native CAD source plus a neutral-format export (STEP). |

Each `.zip` archive is named with the Openwater internal part number and revision: `PPP-NNNNN-RevX.zip`.

---

## File / Part-Number Index

**Part-number convention (current best understanding — confirm with maintainers):**

- **`100-xxxxx`** — Top-level system / console assemblies
- **`700-xxxxx`** — Mechanical sub-assemblies (housings, brackets, transmit-module hardware)
- **`900-xxxxx`** — Test, verification, and characterization fixtures
  
Use this table to figure out what each file is **without opening it**. PNs are Openwater internal identifiers. Where descriptions are marked _TBD_ the maintainers will fill in details on the next pass — please open a PR or issue if you have authoritative info.

| Part Number | Rev  | File                                    | Category                                 | Description                                                  | Format        | Notes                                                        |
| ----------- | ---- | --------------------------------------- | ---------------------------------------- | ------------------------------------------------------------ | ------------- | ------------------------------------------------------------ |
| 100-00050   | Rev2 | `100-00050-Rev2.zip`                    | Console / System                         | Daisy Chain Cable, 2X, LIFU         | STEP + native | 100-series = top-level systems                               |
| 700-00012   | Rev3 | `700-00012-Rev3.zip`                    | Sub-assembly                             | Console, LIFU                                                        | STEP + native | 700-series = mechanical sub-assemblies                       |
| 700-00018   | Rev2 | `700-00018-Rev2.zip`                    | Sub-assembly                             | 1X Housing, LIFU                                                       | STEP + native |                                                              |
| 700-00021   | Rev2 | `700-00021-Rev2.zip`                    | Sub-assembly                             | 2X Housing, LIFU                                                        | STEP + native |                                                              |
| 700-00022   | Rev2 | `700-00022-Rev2.zip`                    | Sub-assembly                             | LIFU Strap Bundle                                                        | STEP + native |                                                              |
| 700-00039   | Rev3 | `700-00039-Rev3.zip`                    | Sub-assembly                             | 180 KHz TM, LIFU                                                        | STEP + native |                                                              |
| 700-00040   | Rev4 | `700-00040-Rev4.zip`                    | Sub-assembly                             | Transmit Module 400 KHz TM, LIFU                                                        | STEP + native |                                                              |
| 900-00016   | Rev1 | `Verification Tank/900-00016-Rev1.step` | Verification Tank fixture / interconnect | Open LIFU 2x Water Tank Testing Kit | STEP AP242    | 900-series = test/verification fixtures. Used with the [openlifu-verification-tank](https://github.com/OpenwaterHealth/openlifu-verification-tank) software stack. |

---

## Opening the files

These files are vendor-neutral CAD exports — you do **not** need a paid CAD seat to open them.

- **STEP (`.step`, `.stp`)** — opens in just about every mechanical CAD package. Free options: [FreeCAD](https://www.freecad.org/), [Onshape](https://www.onshape.com/) (free for public documents), [KiCad's 3D viewer](https://www.kicad.org/) (for STEP). For a quick look without installing anything, try [ViewSTL](https://www.viewstl.com/) (drag and drop).
- **Native source files** (if included in the zip) — Openwater authors most assemblies in Onshape. STEP exports are the canonical interchange format here.

A typical workflow:

1. Download the `.zip` (or `.step`) for the part you want.
2. Extract the archive if needed.
3. Open the `.step` in your CAD tool of choice.
4. Use the included sub-assembly structure to drill into individual components.

---

## Revisions

The `-RevX` suffix in each filename is the **released revision** of that part as of the last commit. When you reference a part in a paper, build log, or BOM, please cite the full filename including the revision so others can reproduce your work against the exact same geometry.

If you find an issue with a file, open a GitHub Issue with:

- The part number + revision you're using
- The CAD tool you opened it in
- A screenshot or description of the problem

---

## Contributing

Contributions are welcome — especially:

- **Better descriptions** for parts currently marked _TBD_ in the index above
- **Manufacturing notes** (tolerances, materials, finishes) where they're missing
- **Derivative designs** (alternative housings, mounts, adapters) — these are encouraged as forks or separate folders

Workflow:

1. Fork the repo.
2. Create a feature branch (`git checkout -b add-700-00012-description`).
3. Make your changes; update this README's index table if you add or revise a file.
4. Open a Pull Request describing what you changed and why.

For substantial new parts, please follow the existing PN convention (`PPP-NNNNN-RevX`) and place the file in the appropriate folder (or create a new top-level folder if it represents a new category).

---

## Related repositories

The mechanical files here are one piece of the broader Open-LIFU stack. See also:

- **[OpenLIFU-app](https://github.com/OpenwaterHealth/OpenLIFU-app)** — GUI for planning and controlling sonications
- **[SlicerOpenLIFU](https://github.com/OpenwaterHealth/SlicerOpenLIFU)** — 3D Slicer extension wrapping the OpenLIFU app
- **[openlifu-verification-tank](https://github.com/OpenwaterHealth/openlifu-verification-tank)** — Python control software for the acoustic verification tank (uses the 900-series fixtures in this repo)
- **[opw_ustx](https://github.com/OpenwaterHealth/opw_ustx)** — Openwater Ultrasound Transmit Module (USTX) firmware and design
- **[OpenwaterWiki — Neuromodulation](https://wiki.openwater.health/index.php/Neuromodulation)** — System-level documentation

---

## License

This repository is released under the **GNU Affero General Public License v3.0 (AGPL-3.0)**. See [`LICENSE`](LICENSE) for the full text. Derivative hardware designs are welcomed; please respect the copyleft terms when redistributing modified versions.

---

## Citation

If you build on these designs in published work, please cite the repository:

```
@misc{openlifu_mechanical,
  title  = {OpenLIFU-Mechanical: Open-Source Mechanical Designs for the Open-LIFU Platform},
  author = {Openwater Health},
  url    = {https://github.com/OpenwaterHealth/OpenLIFU-Mechanical},
  year   = {2026}
}
```

---

_Maintained by [Openwater](https://www.openwater.health). Questions or partnership inquiries: open a GitHub Issue or reach out via the [Openwater Community Hub](https://openwaterhealth.github.io/openwater-community/)._
