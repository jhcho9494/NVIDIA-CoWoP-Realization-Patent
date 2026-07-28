# Cools CoWoP–CPO Integrated Architecture

## Delete the separate ABF package substrate. Transfer the fine-line RDL. Bond the EIC to the PIC without heating the PIC body.

> **The motherboard remains coarse. Fine-line routing is transferred only where it is needed. The separate ABF package-substrate layer disappears. Electronic and photonic ICs are then joined without imposing a package-wide thermal budget on the photonic device.**

[한국어](CPO_INTEGRATED_COWOP_KR.md) · [中文](CPO_INTEGRATED_COWOP_ZH.md)

## 1. Why CoWoP needs more than direct attachment

Removing the separate Ajinomoto Build-up Film (ABF) package substrate is not completed merely by mounting an interposer directly onto a printed circuit board.

The ABF package substrate has historically performed several functions at once:

- fine-pitch fan-out and escape routing;
- power and ground redistribution;
- pitch conversion between the package and the system board;
- thermomechanical buffering between a low-CTE package and a high-CTE motherboard; and
- a controlled assembly surface for heterogeneous dies.

A practical package-substrate-less architecture must replace each function independently rather than simply removing one physical layer.

## 2. The Cools integration thesis

Cools reorganizes those functions into a board-level platform:

```text
Separate ABF package substrate
        ↓ removed

Coarse system motherboard
+ transferred fine-line RDL skin / local RDL patches
+ multi-zone pitch conversion
+ known-good and replaceable RDL tiles
+ compliant board-to-overlay joint
+ high-thermal-conductivity support or local thermal inserts
+ sub-bandgap zero-thermal-budget EIC–PIC bonding
```

The result is not a finer PCB. It is a **coarse motherboard carrying separately manufactured fine-line redistribution structures**.

## 3. Architectural layers

### 3.1 Coarse motherboard

The motherboard retains manufacturable coarse routing, power planes, ground planes, external connectors, mechanical support, and system-level interfaces. It is not required to become a full-area package-substrate-grade fine-line PCB.

### 3.2 Transferred fine-line RDL

Fine redistribution is fabricated on a flat temporary carrier and transferred to the motherboard as one or more of the following:

- local RDL patches;
- board-scale RDL skins;
- tiled or segmented overlays;
- local interconnect bridges; or
- function-specific wiring islands.

The flat carrier supplies the lithographic reference surface. The motherboard can therefore remain coarse and warped within ordinary board-manufacturing capability.

### 3.3 Multi-zone pitch conversion

Different functional regions can use different pitch-conversion ratios and wiring rules within the same transferred structure.

| Zone | Representative device | Main routing objective |
|---|---|---|
| Logic zone | GPU, XPU, switch ASIC | highest I/O density and high-speed escape |
| Memory zone | HBM stack | dense short-reach signal fan-out |
| Power zone | IVR, VRM, PMIC | wide conductors and low impedance |
| Photonics zone | EIC, PIC, optical engine | ultra-short electrical path and optical stability |
| Board-transition zone | motherboard pads and planes | conversion to coarse board pitch |

This prevents the entire structure from being overdesigned to the smallest pitch and allows each zone to use its own layer count, via diameter, conductor width, current capacity, and conversion ratio.

### 3.4 Known-good, repairable tiles

The transferred RDL may be divided into independently fabricated and tested tiles. Only known-good tiles are mounted. A defective tile can be isolated, removed, and replaced without discarding the entire motherboard or high-value die population.

### 3.5 Thermomechanical buffering without the package substrate

When the ABF package substrate is removed, its compliant buffering function also disappears. Cools replaces that function at the direct board-to-overlay joint through one or more of:

- a low-modulus buffer layer or underfill;
- high-aspect-ratio compliant conductive pillars;
- curved or S-shaped redistribution interconnects;
- enlarged perimeter joints or dummy stress-distribution joints; and
- local stiffening frames combined with compliant interfaces.

The package-substrate layer is therefore removed without abandoning the thermomechanical function it once provided.

## 4. CPO integration: the missing layer in conventional CoWoP

A Co-Packaged Optics (CPO) module places a Photonic Integrated Circuit (PIC) next to an Electronic Integrated Circuit (EIC), switch ASIC, GPU, or XPU. Even after the separate ABF package substrate is deleted, conventional EIC–PIC joining can reintroduce a large thermal budget.

Conventional thermal joining can change:

- the thermo-optic refractive index;
- residual stress in waveguides and resonators;
- ring-resonator and laser wavelength;
- optical coupling alignment; and
- the calibration state established before assembly.

The industry then compensates after bonding with trimming, micro-heaters, thermoelectric coolers, lookup tables, and active control.

Cools changes the order: **prevent the bonding-induced optical shift instead of correcting it after assembly.**

## 5. Sub-bandgap zero-thermal-budget EIC–PIC bonding

For a silicon-based PIC, a representative near-infrared nanosecond pulse in the approximately 1.5 µm band can pass through the semiconductor optical body with low bulk absorption. The pulse is instead absorbed by a selected metal interface associated with the copper bond pad.

Representative selective absorbers include:

- titanium (Ti);
- titanium nitride (TiN);
- chromium (Cr);
- nickel (Ni);
- tantalum (Ta);
- related metal nitrides or oxides;
- multilayer adhesion/barrier/passivation stacks; and
- a separately introduced nanoscale absorber.

```text
Sub-bandgap nanosecond pulse
        ↓
passes through the PIC body
        ↓
absorbed at the Cu-pad interface layer
        ↓
localized interfacial heating
        ↓
activation / diffusion / bonding at the bond line
        ↓
PIC optical body remains near its original thermal state
```

The process objective is not “lower package temperature” in a general sense. It is **spatially selective heat generation at the bond line while suppressing temperature rise in the optical device body**.

## 6. Two CPO assembly routes

### Route A — direct EIC-to-PIC bonding

The EIC and PIC are aligned face-to-face or side-by-side and joined through copper pads whose interface layers selectively absorb the sub-bandgap pulse.

### Route B — EIC and PIC bonded to a transferred RDL photonics zone

The EIC and PIC are independently joined to a transferred fine-line RDL zone. The overlay provides:

- ultra-short EIC–PIC electrical interconnects;
- power and ground redistribution;
- impedance-controlled high-speed paths;
- optical-engine mounting lands;
- local thermal-spreading structures; and
- transition to the coarse motherboard.

Route B is particularly compatible with package-substrate deletion because the transferred RDL becomes both the electrical fan-out platform and the optical-engine assembly platform.

## 7. High-thermal-conductivity support

The photonics zone may be formed on or connected to a high-thermal-conductivity support, such as AlN, Si₃N₄, SiC, RBSC with an insulating reference surface, a metal–ceramic composite, or a local thermal insert.

A flat insulating reference surface enables fine wiring while the underlying support acts as a heat spreader or connects to a cold plate, heat sink, microchannel structure, or other cooling system.

This creates separate thermal domains for:

- the switch ASIC or XPU;
- the EIC driver and receiver circuits; and
- the PIC or on-board optical source.

## 8. What replaces the ABF package substrate

| Former ABF package-substrate function | Cools replacement |
|---|---|
| Fine fan-out | transferred RDL skin or local patch |
| Heterogeneous pitch conversion | multi-zone variable-ratio fan-out |
| Power and ground redistribution | dedicated RDL power and ground layers |
| Board manufacturing reference surface | flat temporary carrier |
| Yield protection | known-good and replaceable RDL tiles |
| Thermomechanical buffering | compliant joint and low-modulus buffer |
| Photonic assembly surface | zero-thermal-budget photonics zone |
| Thermal spreading | high-conductivity support or local thermal insert |

The separate ABF package substrate is removed because its functions have been redistributed into independently optimized layers.

## 9. System-level result

```text
Conventional stack
EIC / PIC / GPU / HBM
→ interposer or package RDL
→ ABF package substrate
→ BGA
→ motherboard

Cools integrated CoWoP–CPO
EIC / PIC / GPU / HBM
→ transferred multi-zone RDL
→ compliant direct joint
→ coarse motherboard
```

The integrated architecture targets:

- elimination of the separate ABF package-substrate layer;
- shorter electrical paths;
- fewer C4/BGA-type interfaces;
- lower package height and material count;
- removal of full-area fine-line PCB requirements;
- reduced bonding-induced photonic wavelength shift;
- reduced or eliminated post-bond correction attributable to assembly;
- local repairability and known-good-tile yield control; and
- direct integration of electrical, optical, power, and thermal functions at board level.

## 10. Core proposition

> **The package substrate disappears, fine-line routing is transferred, and the electronic and photonic ICs are joined without changing the optical device state through package-wide heating.**

This is the Cools route from CoWoP to a package-substrate-less electrical–photonic system platform.

## Related Cools technology

- [CPO Zero-Thermal-Budget Bonding](https://github.com/jhcho9494/Cools_CPO_Zero_Thermal_Budget_Bonding)
- [Large-Area Thermal Clutch / No-Warpage Bonding](https://github.com/jhcho9494/Cools_CoWos_No_WarpageSolution)
- [HBM Thermal Clutch](https://github.com/jhcho9494/Cools_HBM_Thermal_Clutch)
- [CoolVia Glass Metallization](https://github.com/jhcho9494/Cools_CoolVia_Glass_Metallization)

## Intellectual property and transaction options

The architectures described here are protected by pending patent applications and associated proprietary know-how of Cools Inc.

Potential discussions may include patent licensing, field- or territory-limited rights, process and architecture transfer, joint development, strategic investment, technology-business transfer, and—where commercially appropriate—assignment or transfer of the relevant patent applications and patent rights themselves.

Publication does not grant any licence, implied right, waiver, or permission to practise the disclosed technology. Any transaction requires technical and legal due diligence and a definitive written agreement.

## Contact

**Dr. Jinhyun Cho — Founder & CEO, Cools Inc.**  
Email: [jhcho@cools.co.kr](mailto:jhcho@cools.co.kr)

© 2026 Cools Inc. All rights reserved.
