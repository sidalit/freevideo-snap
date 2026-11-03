<div align="center">

<img src="snap/gui/freevideo.png" alt="FreeVideo logo" width="128" />

# FreeVideo

**Create AI videos with a desktop launcher and ComfyUI workspace**

[![freevideo](https://snapcraft.io/freevideo/badge.svg)](https://snapcraft.io/freevideo)
[![Base: core24](https://img.shields.io/badge/Base-core24-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core24)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64](https://img.shields.io/badge/Architectures-amd64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [FreeVideo](https://github.com/FlashML-org/FreeVideo), a local AI video and audio generator with a ComfyUI workspace and timeline editor.

</div>

---

## Getting Started

<a href="https://snapcraft.io/freevideo"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install freevideo
freevideo
```

Choose a new installation folder and select **Install & launch**. The desktop launcher downloads a compatible ComfyUI runtime and models, then opens the FreeVideo workspace in your browser. It starts the local server when needed; no separate ComfyUI snap is required.

Local generation requires an NVIDIA Ampere GPU or newer (RTX 30 series or newer), driver 580 or newer, at least 8 GB VRAM and 16 GB RAM. The launcher shows the required disk space before installation.

## Configure

Use the desktop settings to select model folders, download sources and optional LAN access. The default installation, models and caches are kept under `~/snap/freevideo/common` and survive snap refreshes. Downloads can be several gigabytes; the snap initially contains only the launcher and application source.

Snap refreshes update the launcher and bundled FreeVideo source. The application manages its downloaded ComfyUI, Python/CUDA dependencies and models separately; their updates or repairs may require additional downloads.

| Feature | Command |
| --- | --- |
| Models or media on USB drives and other removable media (`/media`, `/mnt`) | `sudo snap connect freevideo:removable-media` |

## Limitations

- Linux amd64 and NVIDIA GPUs only; no CPU-only generation.
- Existing ComfyUI installations in other snaps cannot be modified. Use the launcher's own installation.
- Files outside your home directory and connected removable media are unavailable. Host coding-agent installation and user systemd service setup are not provided.

## Build

```bash
git clone https://github.com/sidalit/freevideo-snap.git
cd freevideo-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/freevideo-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/FlashML-org/FreeVideo/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/freevideo-snap/blob/main/LICENSE).
