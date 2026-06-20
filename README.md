# ⬡ QuantumVault

> A futuristic banking web app secured by Quantum Key Distribution (QKD) using the BB84 protocol.

![QuantumVault](https://img.shields.io/badge/Security-BB84%20QKD-00D4FF?style=flat-square)
![HTML](https://img.shields.io/badge/Built%20with-HTML%20%2F%20CSS%20%2F%20JS-0A1628?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

---

## 🔐 What is QuantumVault?

QuantumVault is a single-page banking application that simulates a real-world bank UI enhanced with **Quantum Key Distribution (QKD)** for transaction encryption. Every fund transfer is encrypted using key bits generated through a simulated BB84 quantum protocol — the same foundation used in real-world quantum-secure networks.

---

## ✨ Features

### 🏦 Banking
| Feature | Description |
|---|---|
| **PIN Login** | 4-digit PIN authentication with on-screen numpad |
| **Dashboard** | Live balance across savings and current accounts |
| **Debit Card** | Visual card with chip, card number, and expiry |
| **Send Money** | IMPS / NEFT / RTGS transfers with recipient, amount, remark |
| **Receive** | QR code + UPI ID display with payment request link |
| **History** | Full transaction log with filter chips (All / Sent / Received / Loan EMIs) |
| **Loans** | Home loan and car loan with progress bars and EMI details |
| **Profile & Settings** | Biometrics, QKD settings, card controls, notifications, sign out |

### ⚛️ Quantum Security
| Feature | Description |
|---|---|
| **BB84 Protocol** | Simulated photon emission in 4 bases: H, V, D, A |
| **Basis Sifting** | Alice and Bob compare bases; ~50% of bits kept |
| **QBER Check** | Quantum Bit Error Rate computed; flags eavesdrop if QBER > 11% |
| **OTP Encryption** | Transaction payload XOR'd with sifted key bits |
| **Live Key Display** | Rotating key bits shown in the top bar |
| **QKD Lab** | Interactive BB84 simulation with round-by-round table |
| **Photon Channel** | Animated Alice → Bob photon stream with polarisation colours |

---

## 🚀 Getting Started

### Option 1 — Open directly
No build step needed. Just open `index.html` in any modern browser.

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/quantumvault-bank.git
cd quantumvault-bank

# Open in browser
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

### Option 2 — Serve locally
```bash
# Python
python3 -m http.server 8080

# Node.js (npx)
npx serve .
```

Then visit `http://localhost:8080`

---

## 🔑 Demo Credentials

| Field | Value |
|---|---|
| Account ID | `QV-2847-9301` |
| PIN | `2847` |

---

## 📁 Project Structure

```
quantumvault-bank/
├── index.html       # Full app — single self-contained file
└── README.md        # This file
```

All CSS and JavaScript are embedded in `index.html` — no dependencies to install, no build tools required.

**External CDN resources loaded at runtime:**
- [Space Grotesk & Space Mono](https://fonts.google.com/) — typography
- [Tabler Icons](https://tabler-icons.io/) — icon set

---

## 🛡️ How QKD Works in QuantumVault

```
Alice (Bank)                              Bob (Client)
     │                                         │
     │──── photons in random bases ──────────>│
     │     |H⟩  |V⟩  |D⟩  |A⟩               │
     │                                         │
     │<─── Bob announces his bases ───────────│
     │                                         │
     │  Both discard mismatched bases (~50%)   │
     │                                         │
     │  Sifted key = matched basis results     │
     │                                         │
     │  QBER check: if > 11% → eavesdrop!     │
     │                                         │
     │  Encrypt: payload XOR sifted_key_bits  │
     │──── ciphertext ──────────────────────>│
```

**Key facts:**
- Any eavesdropper (Eve) physically disturbs the photons, raising the QBER above the 11% threshold and alerting both parties
- The sifted key is used as a **one-time pad (OTP)** — information-theoretically secure when key length ≥ message length
- Each transaction generates a fresh key — no key reuse

---

## 🎨 Design System

| Token | Value | Usage |
|---|---|---|
| `--navy` | `#020B18` | App background |
| `--surface` | `#0A1628` | Cards, topbar |
| `--cyan` | `#00D4FF` | Accent, QKD elements |
| `--green` | `#00FF94` | Received transactions |
| `--red` | `#FF4D6A` | Sent transactions, errors |
| `--amber` | `#FFB800` | Loans, card chip |

**Typography:** Space Grotesk (UI) + Space Mono (data, keys, code)

**Signature element:** Animated quantum particle lattice behind the balance card — a live node-edge network that reacts to the session.

---

## 🗺️ Roadmap

- [ ] Spending analytics chart (monthly breakdown)
- [ ] Eavesdropper (Eve) attack simulation in QKD Lab
- [ ] Bill payments & recharges
- [ ] Dark/light theme toggle
- [ ] Backend integration (Node.js / FastAPI)
- [ ] Real WebSocket-based QKD simulation
- [ ] PWA support (installable on mobile)

---

## 📜 License

MIT © 2026 — free to use, modify, and distribute.

---

> *"The security of quantum cryptography relies on the laws of physics, not computational hardness."*
> — Charles Bennett & Gilles Brassard, inventors of BB84 (1984)