# Home Assistant Automations & Blueprints by Indemnity83

A collection of my Home Assistant blueprints, automation helpers, and configuration snippets that I've found useful and wanted to share with the community.

---

## 🧠 Blueprints

### [🔦 Motion Nightlight](https://github.com/Indemnity83/home-assistant/blob/main/blueprints/motion_nightlight.yaml)

This blueprint turns on a light with a smooth transition when motion is detected **and** the ambient light is below a configurable lux threshold. Designed with the [ThirdReality Multifunction Night Light](https://amzn.to/42qSZyK) in mind.

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fmotion_nightlight.yaml)

### [❄️ Smart HVAC Control](https://github.com/Indemnity83/home-assistant/blob/main/blueprints/smart_hvac_control.yaml)

This blueprint intelligently manages your thermostat based on occupancy, door/window status, and solar power availability. If a door or window is left open, it turns off the HVAC. When power is abundant (e.g. from solar), it cools to a preset temperature. Otherwise, or if nobody is home, it switches to eco mode. Designed for homes with solar and smart climate control.

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2FIndemnity83%2Fhome-assistant%2Frefs%2Fheads%2Fmain%2Fblueprints%2Fsmart_hvac_control.yaml)
---

## 📁 Repo Structure

- `blueprints/` — reusable automation blueprints for various smart devices and triggers  
- `automations/` — longer automations or YAML snippets not structured as blueprints  
- `config/` — reusable configuration helpers or templates  

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
