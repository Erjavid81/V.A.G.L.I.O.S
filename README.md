# V.A.G.L.I.O.S — Central Intelligence Hub

> **V**ersatile **A**utomated **G**uardian & **L**inked **I**ntelligence **O**perations **S**ystem

Homepage privata di smistamento per i servizi smart home di `vaglios.com`.  
Ispirata all'estetica **J.A.R.V.I.S** di Iron Man. Deployata su **Cloudflare Pages**.

---

## Struttura repository

```
vaglios-site/
├── index.html          ← Homepage principale (tutto self-contained)
├── favicon.svg         ← Favicon Arc Reactor
├── robots.txt          ← Blocca indicizzazione (sito privato)
├── sitemap.xml         ← Sitemap minimale
├── _redirects          ← Regole redirect Cloudflare Pages
├── _headers            ← HTTP headers sicurezza/cache
├── assets/
│   ├── css/            ← Eventuali fogli di stile aggiuntivi
│   └── js/             ← Eventuali script aggiuntivi
└── README.md
```

---

## Deploy su Cloudflare Pages

1. Vai su [Cloudflare Pages](https://pages.cloudflare.com/)
2. **Create a project → Connect to Git → seleziona questa repository**
3. Impostazioni build:
   | Campo | Valore |
   |---|---|
   | Framework preset | `None` |
   | Build command | *(lascia vuoto)* |
   | Build output directory | `/` oppure `.` |
4. Salva e deploy — Cloudflare leggerà `_redirects` e `_headers` automaticamente.

### Dominio custom
- In Cloudflare Pages → **Custom domains** → aggiungi `www.vaglios.com`
- Il record DNS viene creato automaticamente se il dominio è già su Cloudflare

---

## Sottodomini collegati

| Sottodominio | Servizio | Tunnel Cloudflare |
|---|---|---|
| `ia.vaglios.com` | Intelligenza Artificiale | ✅ |
| `casa.vaglios.com` | Home Assistant | ✅ |
| `telecamere.vaglios.com` | Sistema CCTV | ✅ |
| `media.vaglios.com` | Media Server (Jellyfin) | pianificato |
| `vpn.vaglios.com` | VPN (WireGuard/Tailscale) | pianificato |
| `files.vaglios.com` | Cloud privato (Nextcloud) | pianificato |
| `monitor.vaglios.com` | Monitoring (Grafana) | beta |
| `energia.vaglios.com` | Gestione energia | pianificato |
| `admin.vaglios.com` | Portainer / Docker | ✅ |

---

## Tech stack

- **HTML/CSS/JS** puro — zero dipendenze, zero build step
- **Cloudflare Pages** — hosting statico globale con CDN
- **Cloudflare Tunnel** — accesso sicuro ai servizi interni senza aprire porte
- **Font**: Orbitron · Rajdhani · Share Tech Mono (Google Fonts)

---

*© Vaglios — Sistema privato, tutti i diritti riservati*
