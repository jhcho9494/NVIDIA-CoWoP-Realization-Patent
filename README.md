# Cools CoWoP Realization Patent Portfolio

## A package-substrate-less architecture for AI/HPC and CPO systems

> **Delete the separate ABF package substrate. Keep the motherboard coarse. Transfer the fine-line RDL. Bond the EIC to the PIC without heating the PIC body.**

**Integrated technical brief:**  
[English](CPO_INTEGRATED_COWOP_EN.md) · [한국어](CPO_INTEGRATED_COWOP_KR.md) · [中文](CPO_INTEGRATED_COWOP_ZH.md)

This repository is a public notice of Cools Inc.'s unpublished patent-pending architecture for practical Chip-on-Wafer-on-PCB (CoWoP) realization in AI/HPC GPU, HBM, switch-ASIC, chiplet, and Co-Packaged Optics (CPO) systems.

In this portfolio, CoWoP means an architecture that **removes the separate ABF package-substrate layer between the fine-line semiconductor interconnect structure and the final system motherboard**.

## The industry bottleneck

Simply attaching an interposer directly to a PCB does not complete package-substrate elimination.

The separate Ajinomoto Build-up Film (ABF) package substrate traditionally provides:

- fine-pitch fan-out and escape routing;
- power and ground redistribution;
- pitch conversion;
- thermomechanical buffering;
- a controlled assembly surface; and
- connection to the coarse system board.

If that layer is removed without replacing those functions, the result is an unmanufacturable fine-line-PCB burden, unacceptable board-level stress, or an incomplete heterogeneous-integration platform.

## Cools architecture

Cools redistributes the former package-substrate functions into separately optimized structures:

```text
Coarse system motherboard
+ transferred fine-line RDL skin or local patches
+ multi-zone variable-ratio fan-out
+ known-good and replaceable RDL tiles
+ compliant direct board joint
+ high-thermal-conductivity support / local thermal inserts
+ zero-thermal-budget EIC–PIC bonding for CPO
```

The motherboard is not manufactured as a full-area package-substrate-grade fine-line PCB. Fine routing is fabricated on a flat carrier, inspected independently, and transferred only where required.

## Patent portfolio coverage

The portfolio includes patent-pending architectures covering, among other elements:

- local transferred fine-RDL patches directly joined to a coarse system board;
- board-scale transferred RDL overlays and stitched multi-tile RDL skins;
- multi-zone fan-out structures with different pitch-conversion ratios for logic, HBM, power, and photonics regions;
- package-substrate functions integrated into a board-level redistribution motherboard;
- high-thermal-conductivity supports and flat insulating reference surfaces for fine wiring;
- vacuum-deposition-free fine-wiring structures manufactured on ultra-thin-copper-foil carriers;
- reusable carrier assemblies with permanent protective layers and consumable release layers;
- compliant joints that replace the thermomechanical buffering function lost when the package substrate is removed; and
- sub-bandgap nanosecond bonding of Electronic Integrated Circuits (EICs) and Photonic Integrated Circuits (PICs) without heating the PIC body.

## CPO-integrated CoWoP

The photonics extension completes the electrical–optical architecture.

A representative silicon-photonics route uses an approximately 1.5 µm-class sub-bandgap nanosecond pulse that passes through the PIC body and is selectively absorbed by a metal interface associated with the copper bond pad, such as Ti, TiN, Cr, Ni, Ta, a related nitride or oxide, or a multilayer absorber stack.

```text
Sub-bandgap pulse
→ passes through the PIC body
→ heats only the selected Cu-pad interface
→ activates and bonds the interface
→ suppresses package-wide PIC heating
→ prevents bonding-induced optical drift instead of correcting it afterward
```

The objective is to reduce or eliminate assembly-induced wavelength drift, residual-stress change, post-bond trimming, micro-heater correction, and calibration attributable to the joining process.

## What replaces the separate ABF package substrate

| Former package-substrate function | Cools replacement |
|---|---|
| Fine fan-out | transferred RDL skin or local RDL patch |
| Heterogeneous pitch conversion | multi-zone variable-ratio fan-out |
| Power and ground redistribution | dedicated RDL power and ground layers |
| Fine-process reference surface | flat temporary carrier |
| Yield protection | known-good and replaceable RDL tiles |
| Thermomechanical buffering | compliant interconnect and low-modulus buffer |
| Photonics assembly surface | sub-bandgap zero-thermal-budget bonding zone |
| Heat spreading | high-conductivity support or local thermal insert |

## Core proposition

> **The package substrate disappears, fine-line routing is transferred, and electronic and photonic ICs are joined without changing the optical-device state through package-wide heating.**

The objective is a practical package-substrate-less system platform with shorter signal paths, fewer interfaces, reduced package height, lower dependency on ABF package-substrate supply, repairable fine-line regions, and integrated electrical, optical, power, mechanical, and thermal functions.

## Public disclosure scope

This repository intentionally discloses the system architecture and commercial proposition at a high level. Detailed claim language, manufacturing parameters, structural drawings, process recipes, material-stack optimization, and non-public know-how are not fully disclosed here.

## Intended readers and partners

- AI/HPC accelerator and GPU companies
- HBM and memory-system teams
- CPO, silicon-photonics, and optical-engine companies
- semiconductor foundries and advanced-packaging organizations
- Outsourced Semiconductor Assembly and Test (OSAT) companies
- PCB, RDL, substrate, and carrier manufacturers
- equipment and process-integration companies
- strategic investors and technology-acquisition partners

## Related Cools repositories

- [CPO Zero-Thermal-Budget Bonding](https://github.com/jhcho9494/Cools_CPO_Zero_Thermal_Budget_Bonding)
- [Large-Area Thermal Clutch / No-Warpage Bonding](https://github.com/jhcho9494/Cools_CoWos_No_WarpageSolution)
- [HBM Thermal Clutch](https://github.com/jhcho9494/Cools_HBM_Thermal_Clutch)
- [CoolVia Glass Metallization](https://github.com/jhcho9494/Cools_CoolVia_Glass_Metallization)
- [DPP Thermal Clutch EUV](https://github.com/jhcho9494/Cools_DPP_Thermal_Clutch_EUV)

## Status

Patent pending / unpublished applications and associated proprietary know-how.

## Intellectual property and transaction options

The technologies and architectures described in this repository are protected by pending patent applications and associated proprietary know-how of Cools Inc.

Cools is open to structured discussions with qualified strategic partners. Depending on the field, territory, scope, and commercial purpose, potential transaction structures may include:

- exclusive or non-exclusive patent licensing;
- field-of-use or territory-limited rights;
- technology and process-architecture transfer;
- joint development and commercialization;
- strategic investment or transfer of the relevant technology business; and
- where commercially appropriate, assignment or transfer of the relevant patent applications and patent rights themselves.

**Negotiations are not limited to a licence. Where the purpose and conditions are appropriate, the relevant patent portfolio itself may be included in the transaction.**

Publication of this repository does not constitute an offer, licence, waiver, or permission to practise the disclosed technology. Any transaction is subject to technical and legal due diligence and a definitive written agreement.

## Inventor background

Dr. Jinhyun Cho is the Founder and CEO of Cools Inc. and a former Samsung Electronics Master-level engineer with long-term experience in heat transfer, mechanical reliability, package and system integration, high-performance electronics, and semiconductor manufacturing architecture.

## Contact

**Dr. Jinhyun Cho — Founder & CEO, Cools Inc.**  
Email: [jhcho@cools.co.kr](mailto:jhcho@cools.co.kr)  
Alternative email: [jhcho9494@naver.com](mailto:jhcho9494@naver.com)

© 2026 Cools Inc. All rights reserved.
