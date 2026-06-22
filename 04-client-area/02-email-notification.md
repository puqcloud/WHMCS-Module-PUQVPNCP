# Email notification

### PUQVPNCP module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-puqvpncp.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/) | [COMMUNITY](https://community.puqcloud.com/) | [PUQVPNCP](https://puqvpncp.com/)

The module can send a **welcome email** the moment a VPN account is provisioned, so the customer receives everything needed to connect without opening a ticket.

## What the welcome email contains

- Connection details — VPN client name, IP address, username and password
- The full **WireGuard configuration** text, ready to paste into a client
- An inline **QR code** for instant mobile import
- A button linking straight to the service management page

## Enabling it

Turn it on per product with **Send welcome email after account provisioning** on the *Module Settings* tab, and choose which template to send (the bundled **PUQ VPNcp - Welcome** by default). See [Welcome Email](../03-installation-and-configuration/06-product-configuration.md#welcome-email) for the full setup, including the one-click template creator and the available merge variables.

The template lives in **Setup → Email Templates → Product/Services** and can be edited freely. If it is missing when the first welcome email is due, the module creates it automatically.

## Resending on demand

An admin can re-send the welcome email at any time from the service's admin tab — see [Email notification (admin)](../05-admin-area/01-product-information.md#email-notification). This works even if the per-product auto-send option is disabled.
