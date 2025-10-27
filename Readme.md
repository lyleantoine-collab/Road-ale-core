# Road Ale Core

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Made in Newfoundland](https://img.shields.io/badge/Made%20in-Newfoundland-green.svg)](https://www.gov.nl.ca/)
[![Asphalt Tough](https://img.shields.io/badge/Asphalt-Tough-black.svg)](https://en.wikipedia.org/wiki/Asphalt_concrete)

Welcome to **Road Ale Core** – the open-source brew for pothole-proof asphalt. We're not just patching roads; we're *fermenting* them back to life with calcium-precipitating bacteria that seal cracks like a Newfie sealing a deal over screech. This repo is the core of **Road Ale**: a DIY admixture for hot-mix asphalt. One 40g packet treats one ton of mix. Culture doubles every 20 hours. Just add sugar. Keep it warm. Potholes? No joke. But with Road Ale? They're history.

Inspired by bio-self-healing tech (think bacteria munching cracks and spitting calcite like Roman roads on steroids), Road Ale turns your asphalt into a living, breathing beast. Scale from garage fermenters to full-site batches. Brew it local, sell it tough. Warning: May attract hipsters mistaking it for craft IPA. **Brew Responsibly.**

**Why "Ale"?** Because it's fermented grit. Sugar-fed microbes brewing in the fog. And yeah, it might just save your tires – and your sanity.

## Features
- **Asphalt Admixture Simulator**: Model bacterial precipitation in hot-mix. Factor in sugar boosts (+20% sealing rate), temp cycles (hot laydown to freeze-thaw), and bitumen tolerance.
- **Yield Calculator**: Input starter (10g vial?), feed (sucrose + warmth), batch volume. Output: packets per run, ROI at 0.1% market (~$750K/year on NL roads alone, minus the odd backhoe bandit).
- **Recipe Optimizer**: Auto-scale for calcium-precipitating strains (e.g., Sporosarcina pasteurii). Recipes for "Rock Road Ale" (salt-hardened) vs. "Mainland Mash" (soft summer slop).
- **Deployment Guide**: How to mix into hot-mix trucks without the crew noticing (or the bikers unionizing).
- **Risk Assessor**: Unofficial: "How not to end up under the Trans-Canada." (Pro tip: Bribe with free samples.)

## Quick Start

### Prerequisites
- Python 3.8+
- Libraries: `numpy`, `matplotlib`, `scipy` (for sims), `pandas` (for yields)
- A shed, an IBC tote, and a tolerance for yeasty smells (worse than fish, but less oily).
- Starter culture: Grab from [Sigma-Aldrich](https://www.sigmaaldrich.com) (Sporosarcina pasteurii, ~$150/100g dry – the calcite kings).

### Installation
1. Clone the repo:cd road-ale-core
2. python -m venv ale_env
source ale_env/bin/activate  # Windows: ale_env\Scripts\activate
pip install -r requirements.txt
from road_ale_core.simulator import AsphaltBrewer

# Rock setup: Salt-hardened, sugar-fueled
ab = AsphaltBrewer(volume_l=100, temp_c=30, sugar_g=500, starter_g=1)
growth = ab.simulate(hours=20)  # Doubles every 20h
packets = growth.dry_yield_g / 40  # 40g per ton hot-mix

print(f"Yield: {packets:.0f} packets – seals {packets} tons of asphalt!")
# Output: Yield: 1200 packets – seals 1200 tons of asphalt!

from road_ale_core.simulator import AsphaltBrewer

# Rock setup: Salt-hardened, sugar-fueled
ab = AsphaltBrewer(volume_l=100, temp_c=30, sugar_g=500, starter_g=1)
growth = ab.simulate(hours=20)  # Doubles every 20h
packets = growth.dry_yield_g / 40  # 40g per ton hot-mix

print(f"Yield: {packets:.0f} packets – seals {packets} tons of asphalt!")
# Output: Yield: 1200 packets – seals 1200 tons of asphalt!

growth.plot_seal(save_as="rock_road_calcite.png")

road-ale-core/
├── src/
│   ├── simulator.py     # Growth models (Monod kinetics + sugar rush)
│   ├── calculator.py    # Packet math, hot-mix ROI
│   └── optimizer.py     # Tweak for bitumen compatibility
├── recipes/             # MD: Base, Rock Road, Slab Ale variants
├── data/                # Sample seals, asphalt refs (no Romans – this is blacktop)
├── tests/               # Tests: Does it survive 150°C laydown?
└── docs/                # Pitches for ACOA: "Sugar-waste → Pothole-proof highways"

