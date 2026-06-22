# Changelog

### PUQVPNCP module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-puqvpncp.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/) | [COMMUNITY](https://community.puqcloud.com/) | [PUQVPNCP](https://puqvpncp.com/)

---

## v1.2 — 22-06-2026

Speed tiers via Configurable Options, an automated welcome email with connection configs, a clearer One-Time Link, and a cleaner client-area overview.

### Configurable Options — speed presets

- **One-click creator** — a **Create speed presets** button on the product Module Settings tab builds the WHMCS Configurable Options for **Download limit (Mbit/s)** and **Upload limit (Mbit/s)**, adds the presets (Unlimited, 10, 25, 50, 100, 250, 500, 1000 Mbit/s) priced at `0` in every currency, and links the group to the product. Idempotent — safe to click repeatedly.
- **Per-order speed** — the customer's selected value overrides the product's default download/upload limit. Applied on provisioning and on every upgrade/downgrade (WHMCS calls change-package for configurable-option changes as well).
- Per-tier pricing can be set on the sub-options to charge for faster speeds.

### Welcome email

- Optional **welcome email** sent on provisioning, containing the connection details, full WireGuard config text and an inline QR code, plus a manage-service link.
- Selectable template — use any WHMCS Product/Service template or the bundled **PUQ VPNcp - Welcome**, with **Create if missing** / **Reset to default** buttons. The template is auto-created on first send if absent.
- **Resend welcome email** button on the admin service tab; works regardless of the per-product auto-send setting.

### One-Time Link

- The client-area One-Time Link now includes a description, an **Open link** button, and a notice stating it carries every protocol config, QR code and credential and can be opened only once.

### Client area

- The default WHMCS **Domain / Username / Server Name / IP Address / Visit Website** block is hidden on the service overview, as it is not relevant for VPN products.

### Maintenance

- Admin AJAX endpoints made POST-only; output-escaping fixes; minor edge-case corrections.

---

## v1.1 18-06-2026

### Bug fixes

- **Client area blank page** — fixed output-buffer conflict in the AJAX controller: WHMCS buffered HTML was prepended to JSON responses, causing the client area to render nothing
- **VPN session list false-positive error** — the `/client/online` endpoint returning an empty list `[]` (no active sessions) was incorrectly treated as an API failure; now handled correctly
- **Smarty template security error** — replaced blocked `{$smarty.get.id}` superglobal access (disallowed by WHMCS Smarty security policy) with the safe `{$service->service_id}` in client area and traffic statistics templates
- **Wrong default API port** — HTTP connections to the PUQVPNCP panel were falling back to port 80 instead of the correct default 8098; fixed in all four code locations across three files
- **AJAX responses on inactive services** — AJAX requests for suspended or terminated services now return a proper JSON error response instead of an empty string, preventing JavaScript parse errors in the client area
---

## v1.0 (2026)

- First release
- Multi-protocol VPN provisioning (WireGuard, OpenVPN, IKEv2)
- Lifecycle: create / suspend / unsuspend / terminate / change-package
- Per-client download and upload bandwidth caps
- Per-product VPN network selection via checkboxes — iterated at provisioning, first with free IP wins
- Client area: VPN client details, WireGuard config + QR, OpenVPN profile, IKEv2 profile, OTL generator
- Client area: monthly traffic chart with totals
- Admin service tab: API connection status, remote client state, bandwidth, selected networks
- License verification (online + offline cache)
