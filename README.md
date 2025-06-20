# PyGrunn-2012-synth-python3_13

<a href="https://buymeacoffee.com/champagnearden" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

[![champagnearden - pygrunn-2012-synth-python3_13](https://img.shields.io/static/v1?label=champagnearden&message=pygrunn-2012-synth-python3_13&color=blue&logo=github)](https://github.com/champagnearden/pygrunn-2012-synth-python3_13 "Go to GitHub repo")
[![stars - pygrunn-2012-synth-python3_13](https://img.shields.io/github/stars/champagnearden/pygrunn-2012-synth-python3_13?style=social)](https://github.com/champagnearden/pygrunn-2012-synth-python3_13)
[![forks - pygrunn-2012-synth-python3_13](https://img.shields.io/github/forks/champagnearden/pygrunn-2012-synth-python3_13?style=social)](https://github.com/champagnearden/pygrunn-2012-synth-python3_13)
[![issues - pygrunn-2012-synth-python3_13](https://img.shields.io/github/issues/champagnearden/pygrunn-2012-synth-python3_13)](https://github.com/champagnearden/pygrunn-2012-synth-python3_13/issues)

> **Heads-up:** This repository is a personal fork of [thedjinn/pygrunn-2012-synth](https://github.com/thedjinn/pygrunn-2012-synth)
> It has been updated for today’s Python, streamlined, and documented, while
> preserving the original demo’s spirit.

---

## ✨ What is it?

A tiny, self-contained additive synthesizer written in pure Python.
Originally a live‑coding demo for the **PyGrunn 2012** conference, it generates
raw PCM samples in real time, mixes voices with ADSR envelopes, and saves the
result as a WAV file—no third‑party DSP libraries required.

This fork:

* **Python 3.8+ ready** – fixes PEP 479 `StopIteration` issues and replaces
  deprecated iterator code.
* **Stream‑to‑disk rendering** – no more building the entire track in RAM.
* **CLI helpers & docs** – run `python synth.py --help` for options.
* **Continuous integration** – linting and basic regression tests via GitHub
  Actions (optional—see `.github/workflows/`).

---

## 🏁 Quick start

```bash
# 1. Clone this fork
git clone https://github.com/chqmpagnearden/pygrunn-2012-synth-python3_13.git
cd pygrunn-2012-synth-python3_13

# 2. (Optional) create a virtual environment
python -m venv .venv
source .venv/bin/activate       # Windows: .venv\Scripts\activate

# 3. Run the demo
python synth.py
```

The demo writes **`output.wav`** in the project root. Open it in any audio
player.

Listen to the output:

 [output.wav](/output.wav)

---

## 💡 How it works (high‑level)

1. **Score generator** yields `(t, notes)` tuples — at time `t` start these
   notes.
2. **Voice objects** produce a stream of floats `[-1.0, 1.0]` using sine waves
   plus an ADSR envelope.
3. **`voice_combiner`** mixes active voices sample‑by‑sample until they finish.
4. Samples are converted to 16‑bit integers and streamed straight into a WAV
   file via the standard `wave` module.

All audio math lives in **one file** (`synth.py`) so you can hack away without
digging through packages.

---

## 🙏 Credits

* **Original author:** *Ross “thedjinn” Lagerwall*– PyGrunn 2012 lightning talk & initial code.
* **Fork maintainer:** *champagnearden*
  – Python 3 upgrades, doc, output.

Sound design inspiration from *ChucK*, *SuperCollider*, and the classic
“Sine + Noise” school of lo‑fi synths.

---

Enjoy the bleeps & bloops!
