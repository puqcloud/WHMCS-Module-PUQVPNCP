# WHMCS Installation and Update

### PUQVPNCP module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-puqvpncp.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/) | [Community](https://community.puqcloud.com/) | [PUQVPNCP](https://puqvpncp.com/) | [Order PUQVPNCP](https://puqcloud.com/puqvpncp.php)

## System requirements

> **Important:** This module works exclusively with **PUQVPNCP** and requires version **2.x or higher** ([PUQVPNCP Website](https://puqvpncp.com/) | [Order PUQVPNCP](https://puqcloud.com/puqvpncp.php)).

| Requirement | Minimum |
|-------------|---------|
| **WHMCS** | 8.x+, 9.x+ |
| **PHP** | 7.4, 8.1, 8.2, 8.3, 8.4 |
| **PUQVPNCP panel** | v2.x and higher |
| **ionCube Loader** | v15+ |

> **Note:** The module uses ionCube encoding. Make sure ionCube Loader is installed and active on your server.

## Installation

> **Note:** The module now uses **ionCube 15**, which provides universal out-of-the-box support for all encodings.
>
> All versions can be found at this link:
> `https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/`
>
> Older module versions for WHMCS 8 are available in the archive directory:
> `https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/archive/`

1. Download the latest version from the PUQ download page:
   ```bash
   wget https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-PUQVPNCP/PUQ_WHMCS-PUQVPNCP-latest.zip
   ```

2. Unzip the archive:
   ```bash
   unzip PUQ_WHMCS-PUQVPNCP-latest.zip -d PUQ_WHMCS-PUQVPNCP-latest
   ```

3. Upload the module files to your WHMCS installation:
   - For **Server modules:** copy the `puqVPNcp` directory from the unzipped folder to `whmcs/modules/servers/`
   ```bash
   cp -r PUQ_WHMCS-PUQVPNCP-latest/puqVPNcp /path/to/whmcs/modules/servers/
   ```

4. The module files are now in place. Proceed to the PUQVPNCP setup guide and configuration.

## Update

The update procedure is the same as installation — replace the existing files with the new version:

1. Download the latest version as described in the Installation section.
2. Unzip the archive.
3. For server modules: simply overwrite the files in `whmcs/modules/servers/puqVPNcp/`. No deactivation is needed.
4. Verify the version number in the module interface matches the new release.
