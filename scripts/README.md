# Home Assistant Area Shutdown & Secure Scripts

This repository contains two reusable Home Assistant scripts designed to work **together** or **independently** to manage whole-home state changes in a clean, composable way:

- **Shutdown Area** – powers down selected subsystems (lights, fans, media players, shades)
- **Secure Area** – secures selected areas (locks, closes garage doors, notifies on open windows/doors)

These scripts are intentionally **area-driven** and **option-based**, making them easy to reuse inside higher-level automations like *Goodnight*, *Goodbye*, or *Work Time* without duplicating logic.

---

## Philosophy

Rather than creating monolithic automations for every scenario, these scripts act as **building blocks**:

- Higher-level automations decide *when* and *where*
- These scripts decide *how*

This keeps your automations readable, maintainable, and easy to extend.

---

## Scripts Overview

### 🛑 Shutdown Area

**Purpose:**  
Gracefully powers down selected subsystems in one or more areas.

**Capabilities:**
- Turn off lights
- Turn off fans
- Stop media players (unjoin + stop)
- Close shades (with window-open safety check)

**Selectable subsystems** allow the same script to behave differently depending on context (e.g., bedtime vs. leaving the house).

---

### 🔒 Secure Area

**Purpose:**  
Secures one or more areas and alerts you if something prevents full security.

**Capabilities:**
- Notify if any **windows** are open
- Notify if any **exterior doors** are open
- Close **garage doors**
- Lock **all locks** in the selected areas

This script does *not* block on open sensors — it reports issues and proceeds with securing actions.

---

## Label Usage (Important)

### `exterior_door` Label

The **Secure Area** script uses Home Assistant **Labels** to determine which door sensors are considered *exterior*.

Apply the label:

```
exterior_door
```

…to any `binary_sensor` with `device_class: door` that represents an exterior entry, such as:
- Front door
- Back door
- Garage entry door
- Side gate

**Do NOT apply this label** to interior doors (bedrooms, pantry, closets, etc.).  
This prevents unwanted notifications for interior activity.

---

## Script Inputs

### Shutdown Area

| Field | Description |
|------|------------|
| `target_area` | One or more Home Assistant areas |
| `shutdown_options` | Subsystems to shut down (`lights`, `fans`, `media`, `blinds`) |

### Secure Area

| Field | Description |
|------|------------|
| `target_area` | One or more Home Assistant areas |
| `notify_service` | Notification service to use (defaults to `notify.notify`) |

---

## Window Sensor ↔ Shade Naming Convention

When shutting down shades, the **Shutdown Area** script includes a safety check to avoid closing blinds if a corresponding window is open.

To support this, the script assumes the following **naming convention**:

- Each shade entity has a matching window sensor
- The window sensor’s `entity_id` is:

```
binary_sensor.<shade_entity_name>
```

### Example

| Shade | Expected Window Sensor |
|------|------------------------|
| `cover.bedroom_blinds` | `binary_sensor.bedroom_blinds` |
| `cover.kitchen_shade` | `binary_sensor.kitchen_shade` |

### Behavior

- If the window sensor **does not exist**, the shade will close
- If the window sensor **exists and is `off` (closed)**, the shade will close
- If the window sensor **exists and is `on` (open)**, the shade will **not** close

This allows the script to fail safely without requiring window sensors in every location.

### Customizing This Behavior

If your environment does not follow this convention, you can:
- Rename entities to match
- Modify the script to use labels instead
- Remove the safety check entirely if not needed

The current approach was chosen for simplicity and zero-configuration behavior in a typical home setup.

---

## Common Usage Patterns

These scripts are designed to be **composed** into higher-level automations.

### 🌙 Goodnight

- Secure **all areas**
- Shutdown **all areas**
- Exclude fans and media players in bedrooms

**Example behavior:**
- House is locked
- Garage is closed
- Lights go out everywhere
- Bedroom fans and Sonos continue running

---

### 👋 Goodbye (Leaving the House)

- Secure **all areas**
- Shutdown **all areas**
- Shutdown **all subsystems**

This is the “full power-down” scenario.

---

### 🛌 Kids in Bed

- Shutdown lights in:
  - Kids’ bedrooms
  - Kids’ bathroom
  - Hallway
  - Foyer
- Leave the rest of the house untouched
- Start Sonos sleep music separately

This avoids mixing “bedtime routines” into your global shutdown logic.

---

### 💻 Work Time

- Shutdown **all areas except the office**
- Leaves office lights, media, and devices running
- Keeps the rest of the house quiet and distraction-free

---

## Why Area-Based Scripts?

- No hardcoded entity IDs
- Automatically adapts as devices are added to areas
- Easier to reason about than per-device automations
- Makes complex routines readable at a glance

---

## Requirements & Assumptions

- Home Assistant areas are properly assigned
- Devices have appropriate `device_class` values:
  - Windows: `window`
  - Doors: `door`
  - Garage doors: `garage`
  - Shades: `shade`
- Exterior door sensors are labeled with `exterior_door`
- Shade and window entities follow the documented naming convention
- Locks are safe to operate at the area level

---

## Extending These Scripts

Ideas for customization:
- Add additional labels (e.g., `secure_ignore`, `night_only`)
- Add a “dry run” notification mode
- Add time-based behavior (night vs. day)
- Expand to alarm panel or presence checks

---

## License

These scripts are provided as-is for personal and community use.  
Adapt them freely to suit your home and workflows.

---

Happy automating 🏡✨
