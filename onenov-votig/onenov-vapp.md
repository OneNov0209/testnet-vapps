# OneNov Voting dApp

A **decentralized, verifiable voting dApp** powered by **Soundness Layer**, offering transparent, privacy-preserving governance through ZK proofs.

---

## Overview

**OneNov Voting dApp** memungkinkan komunitas atau DAO melakukan voting yang:
- **Verifiable** — setiap vote dilengkapi zero-knowledge proof (`ZKP`)  
- **Private** — hasil dihitung tanpa mengungkap identitas voter  
- **Immutable** — proof tersimpan di Walrus dan diverifikasi via Soundness Layer  

Dengan memanfaatkan integrasi Soundness, voting jadi cepat, terdesentralisasi, dan rendah biaya on-chain.

---

## Soundness Layer Integration

- **Generate proof** saat user vote via Soundness CLI atau client-side prover seperti Ligero  
- **Upload proof** ke **Walrus**, lalu ambil `blob ID` sebagai reference  
- **Submit blob ID** via smart contract di Soundness Layer (Move) → diverifikasi oleh validator Sui, dengan attestation on-chain  
  - Proses ini murah, cepat, dan tidak perlu menyimpan data voting full di chain2  
- Frontend/backend memanfaatkan proof sebagai verifikasi transparan dan audit-friendly

---

## Architecture

[Frontend (React)]  ── cast vote → generate ZKP(s) → └─ proof → Walrus → blob ID → Soundness Layer contract (on Sui)

- **Smart Contract**: Move-based (Soundness Layer), menerima blob ID dan menyimpan attestation
- **Backend/CLI**: menghasilkan proof dan submit ke Soundness
- **Frontend**: interface untuk create proposal, vote, dan tampilkan hasil tunduk attested proof

---

## Stack

| Layer       | Tech / Tool                                  |
|-------------|----------------------------------------------|
| Frontend    | React + Tailwind                             |
| Proof       | Soundness CLI / Ligero                        |
| Storage     | Walrus (decentralized data)                   |
| Blockchain  | Soundness Layer contract (Move on Sui)       |
| dApp Host   | Soundness Layer Testnet (developer access)   |

---

## Features

1. **Submit voting proposal** di frontend  
2. **Cast vote → generate ZKP → store to Walrus**  
3. **Submit blob ID to Soundness Layer**, store attestation on-chain  
4. **View tally & proof status**, transparan dan dapat diaudit oleh siapa saja

---

## Timeline

**PoC (2-4 weeks)**  
- Integrasi Soundness CLI & generate proof  
- Simpan proof di Walrus → dapatkan blob ID  
- Submit to Soundness Layer contract + simple React UI  

**MVP (4-8 weeks)**  
- Tambahkan multi-choice voting  
- Auth (Discord/Github) + UI polish  
- User testing & proof explorer

---

## Contact

- **Website**: [onenov.xyz](https://onenov.xyz)  
- **GitHub**: [@OneNov0209](https://github.com/OneNov0209)  
- **Discord**: suryaone#6296 (ID: 956188958071607348)  
- **Telegram**: [t.me/OneNov02](https://t.me/OneNov02)

---

## Why Soundness?

- **Fast finality & low cost**: ideal buat voting yang butuh real-time  
- **Decentralized & censorship-resistant**: proof tidak dikendalikan satu pihak saja3  
- **Cross-chain readiness**: proof bisa diverifikasi lintas blockchain  
- **Proof auditability**: semua vote bisa dicek oleh pihak ketiga tanpa kompromi

---
