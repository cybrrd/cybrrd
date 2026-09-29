# cyBRRD

**Aviation telemetry and UAV technology, with the world's first open UAV Remote ID tracking platform.** We build open, community-run receivers for drone Remote ID, and the network that shows what they hear.

Since 2024, most drones flying in the United States must broadcast Remote ID: an aircraft identifier, its position and altitude, and where its operator is. It is public by design, but short-range: Bluetooth and Wi-Fi typically reach under a kilometer, so no single receiver sees much. cyBRRD turns many small receivers into a shared, live picture of the low-altitude airspace.

## What we build

| | |
|---|---|
| **[BRRDfeeder](https://github.com/cybrrd/brrdfeeder)** | Turns a Raspberry Pi into a Remote ID receiver. Hears Wi-Fi (2.4 and 5 GHz) and Bluetooth LE, including long-range Coded PHY. Free and open source under AGPL-3.0. |
| **[globe.cybrrd.com](https://globe.cybrrd.com)** | A live map of the drones and operator stations the network hears. |
| **[get.cybrrd.com](https://get.cybrrd.com)** | One-command install for BRRDfeeder. |

## Run a receiver

On a Raspberry Pi 4 or 5 (or Compute Module 4 or 5), 64-bit:

```sh
curl -fsSL https://get.cybrrd.com | bash
```

You'll need an external Wi-Fi adapter that supports monitor mode, a Realtek RTL8761B Bluetooth dongle, and a u-blox USB GPS. The installer walks you through the rest.

## How we build it

- **Listen only.** BRRDfeeder never transmits to, jams, or interferes with any aircraft.
- **Verified before it runs.** The installer checks a pinned SHA-256 before it asks for `sudo`, and pulls container images by digest, never by tag.
- **Witnessed, not decreed.** Every report carries which receiver heard it and how. What an aircraft broadcasts is shown as a claim, never as verified truth.

## Links

[www.cybrrd.com](https://www.cybrrd.com) · [globe.cybrrd.com](https://globe.cybrrd.com) · [BRRDfeeder source](https://github.com/cybrrd/brrdfeeder)
