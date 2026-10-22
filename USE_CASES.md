# Use cases

An Omnipha phone is a full Linux computer in a phone body. The display, processor, storage, battery, sensors, Wi-Fi, Bluetooth and cameras are already built in.

This file is the catalog of intended uses. It is written for people choosing a project and for agents scoping work. It does not claim that any setup below is tested or released. Device evidence lives in [`ports`](https://github.com/omnipha/ports/blob/main/DEVICES.md); installable images, once they exist, live in [`images`](https://github.com/omnipha/images).

## Status

| Status | Meaning |
|---|---|
| `idea` | Intended use. No verified Omnipha setup. |
| `tested` | Ran on a named device. Evidence is linked. |
| `released` | Installable from a verified image release. |

Every entry below is `idea` as of 2026-10-22. Do not promote an entry without device evidence.

## What the hardware already gives you

| Part | What it enables |
|---|---|
| Display and touch | Dashboards, kiosks, printer consoles, local control |
| Processor and GPU | Agents, builds, containers, small local models |
| Storage | Git, files, backups, media, camera recordings |
| Battery | Keeps the node alive through short power cuts |
| Sensors | Light, motion, orientation, proximity, microphone, GPS where the device has them |
| Wi-Fi and Bluetooth | Network access, presence, nearby-device detection |
| Cameras | Monitoring, printer watching, vision experiments |

Exact parts differ by device. Read `device.yaml` before relying on one.

## Agents and development

### `agent-host`
A phone that stays on and runs Claude Code, Codex, OpenClaw or Hermes over SSH.
- Uses: CPU, RAM, storage, Wi-Fi, battery
- Profile: `agent-host`
- Status: `idea`

### `build-runner`
A small Git, build or CI node for repositories that fit in the phone's memory.
- Uses: CPU, storage, Wi-Fi
- Profile: `server`
- Status: `idea`

### `local-models`
Runs small local language or vision models on the phone GPU instead of sending every request out. Pick the phone from the [GPU and RAM catalog](https://github.com/omnipha/ports/blob/main/GPU.md): RAM limits the model size, the GPU ranking is external Android data, and the Linux GPU column says whether we have actually tried it.
- Uses: GPU, RAM, storage
- Profile: `agent-host`
- Status: `idea`

### `travel-server`
A pocket server for a trip or outage: SSH, files and an agent, powered by its own battery.
- Uses: Wi-Fi or USB network, storage, battery
- Profile: `server`
- Status: `idea`

## Home and sensors

### `home-assistant-node`
A Home Assistant add-on host or sensor bridge. Screw the phone to a wall, power it, and it contributes light, motion, proximity, sound, camera and its own battery state. This is a container or integration on Omnipha Linux, not a Home Assistant OS image.
- Uses: sensors, camera, Wi-Fi, display, battery
- Profile: `agent-host`
- Status: `idea`

### `wall-display`
The screen shows calendar, build status, energy, weather or whatever the room needs. Touch input stays available.
- Uses: display, touch, Wi-Fi
- Profile: `console-ui`
- Status: `idea`

### `room-presence`
Detects who or what is nearby through Bluetooth and Wi-Fi, without a separate presence sensor.
- Uses: Bluetooth, Wi-Fi
- Profile: `server`
- Status: `idea`

### `voice-endpoint`
Microphone and speaker make the phone a local voice endpoint for an assistant or intercom.
- Uses: microphone, speaker, Wi-Fi
- Profile: `agent-host`
- Status: `idea`

## Workshop

### `printer-host`
Runs a 3D-printer stack such as Klipper, watches the print through the camera and shows status on the phone display.
- Uses: USB or network, camera, display, Wi-Fi
- Profile: `console-ui`
- Status: `idea`

### `print-server`
Shares a normal printer with the local network.
- Uses: USB or network, Wi-Fi
- Profile: `server`
- Status: `idea`

### `room-camera`
A camera for your own room, stored locally or sent to your own recorder. Not a claim of a packaged surveillance product.
- Uses: camera, storage, Wi-Fi
- Profile: `server`
- Status: `idea`

## Data and network

### `pocket-nas`
A small file, backup or media node for the home network. Capacity is the phone's own storage unless external storage is attached.
- Uses: storage, Wi-Fi, USB
- Profile: `server`
- Status: `idea`

### `network-node`
Runs your own DNS filter, VPN exit or Tailscale node where the phone already sits on the network.
- Uses: Wi-Fi, CPU
- Profile: `server`
- Status: `idea`

### `wifi-repeater`
Extends or creates Wi-Fi. The phone joins an existing network and re-broadcasts it, or acts as an access point or router with a different uplink: USB Ethernet adapter, or the SIM modem as a mobile router.
- Uses: Wi-Fi in access-point mode, USB Ethernet, modem where supported, battery
- Profile: `server`
- Status: `idea`
- Caveat: Repeating on one radio halves throughput. A wired uplink or a SIM uplink gives full Wi-Fi speed. Access-point mode and simultaneous client plus AP depend on the Wi-Fi chip and driver, so check per device in `ports`.

## Out and about

### `sensor-logger`
Carries GPS and motion sensors and records a trip or environment without a separate logger.
- Uses: GPS, motion sensors, storage, battery
- Profile: `server`
- Status: `idea`

### `machine-controller`
Camera, motion sensors and Linux I/O make the phone a controller or telemetry node for a robot, machine or vehicle.
- Uses: camera, sensors, USB or Bluetooth, battery
- Profile: `agent-host`
- Status: `idea`

### `signage`
A powered phone becomes a small looping display for a shop, event or workshop.
- Uses: display, storage, Wi-Fi
- Profile: `console-ui`
- Status: `idea`

### `field-probe`
A portable jump host or network probe you can place somewhere, reach over SSH, and remove again.
- Uses: Wi-Fi, battery, USB network
- Profile: `server`
- Status: `idea`

## Security

### `security-lab`
A pocket pentest toolkit in the spirit of Kali Linux or a Flipper Zero: network and Wi-Fi audits, Bluetooth and NFC inspection, USB gadget experiments, and a screen to read results on site.
- Uses: Wi-Fi, Bluetooth, NFC where present, USB OTG, display, battery
- Profile: `console-ui`
- Status: `idea`
- Caveat: Wi-Fi monitor mode and packet injection depend on the chip and driver. Many phone Wi-Fi chips do not support them, so expect an external USB adapter. Hardware support is checked per device in `ports`.

## For agents

- Add or change a use case in this file only. Do not copy the catalog into another repo.
- Keep the `id`, `Uses`, `Profile` and `Status` lines. They are the machine-readable contract.
- `idea` never means a device supports it. Check `ports` before naming hardware as available.
- A use case graduates to `tested` only with a device id, date and linked evidence. It graduates to `released` only with a verified `images` release.
