# Home Assistant Automations & Blueprints by Indemnity83

A collection of my Home Assistant blueprints, automation helpers, and configuration snippets that I've found useful and wanted to share with the community.

## 🧠 Blueprints

All blueprints support one-click import and automatic updates. Click the badges below to import, or visit the **[Wiki](../../wiki)** for detailed documentation, examples, and troubleshooting.

### Script Blueprints

Composable building blocks for whole-home state management. Import these to create callable scripts that can be used from your automations.

| Blueprint | Description | Import |
|-----------|-------------|--------|
| **[🛑 Shutdown Area](../../wiki/Shutdown-Area)** | Powers down subsystems (lights, fans, media, shades) in selected areas | [![Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fshutdown-area.yaml) |
| **[🔒 Secure Area](../../wiki/Secure-Area)** | Locks doors, closes garages, notifies on open windows/doors | [![Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fsecure-area.yaml) |

### Automation Blueprints

Ready-to-use automations for common smart home scenarios.

| Blueprint | Description | Import |
|-----------|-------------|--------|
| **[🔦 Motion Nightlight](../../wiki/Motion-Nightlight)** | Lux-based motion lighting with smooth transitions | [![Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fmotion_nightlight.yaml) |
| **[❄️ Smart HVAC Control](../../wiki/Smart-HVAC-Control)** | Solar-aware climate control with occupancy detection | [![Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fsmart_hvac_control.yaml) |
| **[🌬️ Whole House Fan](../../wiki/Whole-House-Fan-Controller)** | Temperature-based whole house fan automation | [![Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fwhole_house_fan_controller.yaml) |

---

## 📁 Repo Structure

- `blueprints/` — reusable automation and script blueprints
  - Automation blueprints (motion_nightlight.yaml, smart_hvac_control.yaml, etc.)
  - Script blueprints (shutdown-area.yaml, secure-area.yaml)
  - Full documentation in blueprints/README.md

This repo is intended to grow over time with more blueprints, integrations, and useful automations.

---

## ⚠️ Affiliate Disclosure

Some links to products (e.g. Amazon) may be affiliate links. This means if you purchase through them, I may earn a small commission at no additional cost to you. Thanks for the support!

---

## 🤝 Contributing

PRs, improvements, and suggestions are always welcome! Feel free to fork or reuse any of the blueprints in your own setup.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).
