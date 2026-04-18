# EFIS Hardware — 7-Inch BeagleBone Display

**Status:** Open Hardware — Experimental Amateur-Built Category  
**Form Factor:** 7-inch display, BeagleBone Black host  
**Files:** Enclosure CAD, BeagleBone cape design, renderings

---

## What This Is

This repository contains the **mechanical and hardware design files** for a 7-inch EFIS (Electronic Flight Instrument System) display unit. It uses a BeagleBone Black single-board computer and a Newhaven 7-inch capacitive touchscreen cape as the display engine. The design includes a complete machined or printed enclosure with panel-mount provisions.

This is the larger sibling to the [5-inch Raspberry Pi EFIS hardware](../efis-5-inch-raspberry-pi). The 7-inch form factor provides more screen area for IFR use cases, particularly when displaying a moving map alongside primary flight instruments.

![Exploded View](Renderings/Exploded.JPG)

---

## Repository Contents

| Path | Description |
|---|---|
| `Enclosure/` | CAD files for the display enclosure (panel mount, bezel, rear housing) |
| `Beaglebone Cape/` | Hardware design files for any custom BeagleBone interface cape |
| `Renderings/` | 3D renderings of the assembled unit for reference |

## Required Hardware

| Component | Source |
|---|---|
| [BeagleBone Black Rev C](https://www.digikey.com/product-detail/en/ghi-electronics-llc/BBB01-SC-505/BBB01-SC-505-ND/6210999) | Compute host |
| [Newhaven 7" CTP Cape](https://www.digikey.com/product-detail/en/newhaven-display-intl/NHD-7.0CTP-CAPE-N/NHD-7.0CTP-CAPE-N-ND/6622772) | Display + touch interface |
| This enclosure design | Panel integration |

## Software

The display unit runs:
- **[pyEfis](../pyEfis)** — EFIS display application (Python/PyQt6)
- **[FIX-Gateway](../fix-gateway)** — data broker connecting to the aircraft avionics network
- **[pyAvMap](../pyAvMap)** — optional moving map overlay for VFR/IFR chart display

## Role in the MakerPlane / MAOS Ecosystem

This unit is suitable as a **primary flight display** for IFR-capable MAOS avionics. The 7-inch screen accommodates a full PFD layout (attitude indicator, airspeed tape, altitude tape, HSI) alongside a moving map panel. It provides the physical housing and compute platform for the software display stack.

For MAOS, a pair of these units (pilot and copilot) would constitute a redundant cockpit display architecture when driven from a FIX-Gateway data broker connected to the MAOS avionics bus.

## Important Disclaimer

> This is open hardware for Experimental Amateur-Built aircraft use only.  
> Hardware designs have not been independently reviewed for airworthiness.  
> The builder is responsible for all fabrication, assembly, and installation decisions.
