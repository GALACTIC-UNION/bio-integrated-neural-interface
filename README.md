# 🧠 Bio-Integrated Neural Interface

[![CI](https://github.com/GALACTIC-UNION/bio-integrated-neural-interface/actions/workflows/ci.yml/badge.svg)](https://github.com/GALACTIC-UNION/bio-integrated-neural-interface/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Python 3.12+](https://img.shields.io/badge/python-3.12%2B-blue)](https://www.python.org/)

**Signal acquisition, processing, and decoding pipeline for non-invasive
brain-computer interfaces (BCI)** — Part of the OCN GAIA-NANO domain.

---

## Overview

Bio-Integrated Neural Interface (BINI) provides an end-to-end platform for
EEG/ECoG signal acquisition, real-time artefact rejection, feature extraction,
and intent decoding for human-machine interface applications. It is designed for
research use and follows established neuroscience and biomedical engineering
standards.

### Key Capabilities

| Capability | Description |
|---|---|
| **Multi-modal acquisition** | LSL-compatible adapters for EEG, ECoG, and EMG headsets |
| **Artefact rejection** | ICA, wavelet denoising, and adaptive filtering pipelines |
| **Feature extraction** | Band power, CSP, and Riemannian geometry feature sets |
| **Intent decoding** | EEGNet, ShallowConvNet, and custom PyTorch classifiers |
| **Real-time inference** | <50 ms end-to-end latency on edge-class hardware |
| **Device output** | Keyboard emulation, HID, and custom device protocol adapters |

---

## Quick Start

```bash
git clone https://github.com/GALACTIC-UNION/bio-integrated-neural-interface.git
cd bio-integrated-neural-interface
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
# Stream from a supported EEG headset (or use the simulator):
python src/acquisition/simulator.py --channels 64 --duration 60
# In a second terminal, run the decoding pipeline:
python src/pipeline/run_pipeline.py --config config/pipeline.example.yaml
```

## Project Structure

```
bio-integrated-neural-interface/
├── src/
│   ├── acquisition/      # LSL adapters and hardware drivers
│   ├── preprocessing/    # Artefact rejection and signal conditioning
│   ├── features/         # Feature extraction (band power, CSP, Riemannian)
│   ├── decoding/         # PyTorch classifiers (EEGNet, ShallowConvNet)
│   └── output/           # Device control adapters (HID, keyboard, custom)
├── docs/
│   ├── hardware-compatibility.md
│   ├── signal-processing.md
│   ├── model-training.md
│   └── ethics-and-safety.md
├── tests/
├── config/
├── .github/workflows/ci.yml
├── requirements.txt
├── CONTRIBUTING.md
└── README.md
```

## Ethics & Safety

Neural interface research involves human participants and sensitive neurological data.
All experiments must comply with IRB/ethics board approvals, and data must be handled
per GDPR/HIPAA guidelines. See [docs/ethics-and-safety.md](docs/ethics-and-safety.md).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT — see [LICENSE](LICENSE).
