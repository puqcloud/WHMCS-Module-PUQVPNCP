# Changelog

### PUQVPNCP module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-puqvpncp.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/) | [COMMUNITY](https://community.puqcloud.com/) | [PUQVPNCP](https://puqvpncp.com/)

---

## v1.1 (June 2026)

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
