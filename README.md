<p align="center">
  <a href="https://no-do.dev"><img src="assets/banner.svg" width="100%" alt="eva420 — NO-DO · security and OSINT engineering · Remote · EU"></a>
</p>

<div align="center">

`I reverse-engineer live threats, then build the OSINT / GEOINT and authorized-offensive tooling that answers them.`

<sub>Founder &amp; principal engineer · <a href="https://no-do.dev">NO-DO</a> &nbsp;·&nbsp; <em>Desmonto amenazas reales y construyo lo que las responde.</em></sub>

</div>

<p align="center">
  <img alt="Location: Remote, EU" src="https://img.shields.io/badge/Location-Remote%20%C2%B7%20EU-informational?style=flat-square&labelColor=0A0E14&color=1F2630">
  <img alt="Focus: Security and OSINT" src="https://img.shields.io/badge/Focus-Security%20%C2%B7%20OSINT-informational?style=flat-square&labelColor=0A0E14&color=1F2630">
  <img alt="Primary languages: TypeScript and Python" src="https://img.shields.io/badge/Writes-TypeScript%20%C2%B7%20Python-informational?style=flat-square&labelColor=0A0E14&color=1F2630">
  <a href="https://no-do.dev"><img alt="Live site: no-do.dev" src="https://img.shields.io/badge/Live-no--do.dev-informational?style=flat-square&labelColor=0A0E14&color=1F2630&logo=cloudflare&logoColor=22D3EE"></a>
  <a href="https://github.com/eva420/salat-stealer-analysis"><img alt="Public research at TLP:CLEAR" src="https://img.shields.io/badge/Research-TLP%3ACLEAR-informational?style=flat-square&labelColor=0A0E14&color=1F2630"></a>
</p>

## `whoami`

> **`eva420`** — the engineering home of [NO-DO](https://no-do.dev), a founder-led security & OSINT studio.
> One person covers the chain: recon, authorized operation, infrastructure, signed evidence, deploy on Cloudflare. Offensive and defensive work, always with written authorization.

---

## `SEC/01 · Public research`

[**`salat-stealer-analysis`**](https://github.com/eva420/salat-stealer-analysis) is an independent, end-to-end reverse-engineering of an **active Go-based Malware-as-a-Service infostealer** (*Salat Stealer / WebRat*, sold by Russian-speaking actors). Starting from a trojanized "gamer tools" pack, I reversed the `garble`-obfuscated Go loader in **Ghidra (headless)**, extracted and decrypted its self-embedded payload — **ChaCha20-Poly1305 + zstd**, CBOR-chunked — to recover a 12.5 MB PE32 stealer, detonated it in an **isolated lab**, and pulled the live C2 straight off the **TLS ClientHello SNI** after the sample hid resolution behind DNS-over-HTTPS. A purely **passive urlscan.io pivot by IP** then expanded the 5 documented C2 domains to **12 domains plus a live admin panel** whose origin was exposed by an operator OPSEC failure. Attribution is kept **group-level and sanitized** — no victim data, no named individuals — and the write-up ships a full IOC table with a machine-readable [`iocs.csv`](https://github.com/eva420/salat-stealer-analysis/blob/main/iocs.csv).

[![TLP:CLEAR](https://img.shields.io/badge/TLP-CLEAR-informational?style=flat-square&labelColor=0A0E14&color=DC2626)](https://github.com/eva420/salat-stealer-analysis) &nbsp; **Read the full write-up →** [`eva420/salat-stealer-analysis`](https://github.com/eva420/salat-stealer-analysis)

## `SEC/02 · Capabilities`

What I work on and where you can check it. The code of the products is private; each row points to a public repo or a live site.

| Discipline | Where it's proven |
|---|---|
| Malware RE & threat intelligence | **[salat-stealer-analysis](https://github.com/eva420/salat-stealer-analysis)** — Ghidra RE, payload decryption, live C2 discovery, published IOCs *(public)* |
| OSINT / GEOINT | **[TRACEZ](https://tracez.no-do.dev)** — entity graphs, geolocation & timeline, live Earth data *(in production)* |
| Authorized offensive security | **[GRIMZ](https://grimz.no-do.dev)** — scope-bound pentest tooling, live billing *(in production)* |
| Edge infrastructure & applied crypto | Cloudflare Workers + D1; Ed25519 node-locked licensing & signed evidence — applied crypto shown publicly in the [salat payload decryption](https://github.com/eva420/salat-stealer-analysis) (ChaCha20-Poly1305) |

## `SEC/03 · In production`

Research turned into tooling. Each product has its own site, so you can check it without access to a private repo.

| Product | What it is | Status |
|---|---|---|
| **[TRACEZ](https://tracez.no-do.dev)** | OSINT/GEOINT graph console: entities, relationships, geolocation and timeline, plus live Earth data (flights, earthquakes, weather, ISS, NASA imagery) and AI case auto-expansion, fed by 32 open sources, with continuous monitors and Ed25519-signed evidence anyone can verify without an account — one investigation workspace on Cloudflare Workers + D1. Mobile Lighthouse 99 · CLS 0. | ![public beta](https://img.shields.io/badge/live-public%20beta-informational?style=flat-square&labelColor=0A0E14&color=D99A52) |
| **[GRIMZ](https://grimz.no-do.dev)** | Authorized-pentest product: deny-by-default scope enforcement, node-locked licensing, enterprise engagements and controlled-intrusion training labs. | ![live, billing](https://img.shields.io/badge/live-billing-informational?style=flat-square&labelColor=0A0E14&color=22D3EE) |
| **[ATTEST](https://verify.no-do.dev)** | Signs a finished case as a dossier a third party can verify without an account: Ed25519 signature plus an RFC 3161 timestamp, with a public verifier. | ![live](https://img.shields.io/badge/live-online-informational?style=flat-square&labelColor=0A0E14&color=22D3EE) |

## `SEC/04 · Rules of engagement`

How the work is kept inside its limits:

- **Authorization-first.** Offensive capability is gated on written scope and rules of engagement — enforced in code. GRIMZ ships **deny-by-default scope**: out-of-scope targets are refused by construction, not by convention.
- **Scope-bound by construction.** Licensing is **node-locked (Ed25519)** — tooling runs where it is authorized to run, and nowhere else.
- **Evidence you can verify.** Deliverables are **Ed25519-signed**, so a third party can check integrity and origin without having to trust me.
- **Defender-focused.** Public research ships at **TLP:CLEAR** with IOCs for blue teams; attribution stays group-level; labs are isolated and disposable.
- **No rented offensive access.** NO-DO deliberately does not sell hosted offensive capability — a liability line held on purpose, not a missing feature.

Coordinated disclosure & full policy: [`SECURITY.md`](./SECURITY.md) · [contacto@no-do.dev](mailto:contacto@no-do.dev)

## `SEC/05 · Stack`

TypeScript (strict) end to end · Python for tooling and analysis · Go for reverse-engineering and binary internals · Cloudflare Workers + D1 at the edge · Ed25519 for node-locked licensing and signed evidence · Ghidra and `tshark` for reverse-engineering · a **local** LLM for analysis, so investigation data never leaves the box.

<p align="center">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-1F2630?style=flat-square&logo=typescript&logoColor=22D3EE">
  <img alt="Python" src="https://img.shields.io/badge/Python-1F2630?style=flat-square&logo=python&logoColor=22D3EE">
  <img alt="Go (reverse-engineering)" src="https://img.shields.io/badge/Go-RE-1F2630?style=flat-square&logo=go&logoColor=22D3EE">
  <img alt="Cloudflare Workers" src="https://img.shields.io/badge/Cloudflare%20Workers-1F2630?style=flat-square&logo=cloudflareworkers&logoColor=22D3EE">
  <img alt="Cloudflare D1" src="https://img.shields.io/badge/Cloudflare%20D1-1F2630?style=flat-square&logo=cloudflare&logoColor=22D3EE">
  <img alt="Ghidra reverse engineering" src="https://img.shields.io/badge/Ghidra-1F2630?style=flat-square">
  <img alt="Ed25519 signed evidence" src="https://img.shields.io/badge/Ed25519-1F2630?style=flat-square">
</p>

## `SEC/06 · Engage`

Authorized security and OSINT engagements, research collaboration or hiring:

- **Email** — [contacto@no-do.dev](mailto:contacto@no-do.dev)
- **Web** — [no-do.dev](https://no-do.dev)

<sub>Open to collaboration and select security roles. · Abierto a colaboración y a proyectos seleccionados.</sub>

---

<p align="center">
  <sub><code>+ &nbsp; eva420 · NO-DO · recon → operation → signed evidence · Remote · EU</code></sub>
</p>