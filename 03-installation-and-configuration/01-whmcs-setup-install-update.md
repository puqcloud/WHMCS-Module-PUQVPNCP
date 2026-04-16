lt# WHMCS setup (install / update)

### PUQVPNCP module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-puqvpncp.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/) | [COMMUNITY](https://community.puqcloud.com/) | [PUQVPNCP](https://puqvpncp.com/)

## System requirements

| Requirement | Minimum version         |
|-------------|-------------------------|
| **PHP** | 7.4, 8.1, 8.2 or higher |
| **WHMCS** | 8.x or 9.x              |
| **ionCube Loader** | v13 or newer (v14, v15) |
| **PUQVPNCP panel** | v2.x                    |

> **Note:** The module uses ionCube encoding. Make sure ionCube Loader is installed and active on your server.

---

## Download

The module can be ordered and downloaded from PUQ Cloud:

- **Order / Download:** [https://puqcloud.com/whmcs-module-puqvpncp.php](https://puqcloud.com/whmcs-module-puqvpncp.php)
- **Direct download link for the latest version:** 
- PHP 8.2+
- WHMCS 8.x or 9.x
```
wget https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/php82/PUQ_WHMCS-PUQVPNCP-latest.zip
```

> Older module versions for WHMCS 8 / older PHP runtimes are available in PHP-specific directories:
> - PHP 7.4: [https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/php74/](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/php74/)
> - PHP 8.1: [https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/php81/](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/php81/)

After downloading, extract the archive:

```
unzip PUQ_WHMCS-PUQVPNCP-latest.zip
```

---

## Installation

### Step 1: Upload files

Extract the module archive and copy the `puqVPNcp` directory to the WHMCS servers module directory:

```
WHMCS_WEB_DIR/modules/servers/puqVPNcp
```

Make sure file permissions allow the WHMCS PHP user to read every file in that directory.

### Step 2: First admin-area visit

Log in to the WHMCS admin area. On the first request the module auto-creates its helper table (`puq_license`) and registers the licence record for each product.

### Step 3: Add a server

Navigate to **System Settings** → **Servers** → **Add New Server**:

1. Enter the **Name** and **Hostname** of your PUQVPNCP panel.
2. In Server Details, select the **PUQ VPNcp** module.
3. Paste the panel API Bearer token into the **Password** field (the **Username** field is unused — leave it blank).
4. Tick **Secure** (SSL) and set the panel port (default `443`).
5. Click **Test Connection** to verify.

Detailed instructions: [Add server](05-add-server.md).

### Step 4: Create a product

Navigate to **System Settings** → **Products/Services** → **Create a New Product**:

1. Select **PUQ VPNcp** in the Module Settings tab.
2. Paste your licence key.
3. Configure bandwidth limits, the client-name template and tick the allowed VPN networks.

Detailed instructions: [Product configuration](06-product-configuration.md).

---

## Update

### Step 1: Backup

Before updating, it is recommended to back up:
- WHMCS database
- Module files in `modules/servers/puqVPNcp/`

### Step 2: Upload new files

Download and extract the new version, then overwrite all files in:

```
WHMCS_WEB_DIR/modules/servers/puqVPNcp/
```

### Step 3: Verification

1. Log in to the WHMCS admin area.
2. Open **System Settings** → **Servers**, edit the PUQVPNCP server and click **Test Connection** — it must report success.
3. Open an existing service that uses the module and confirm the **Connection status** and **VPN Client** blocks render correctly on the Products/Services tab.

> **Important:** review the **[Changelog](../02-changelog.md)** before updating — some versions require product reconfiguration.