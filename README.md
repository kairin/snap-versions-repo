# Browser Installation Guide

This repository contains instructions for installing the latest versions of Google Chrome and Microsoft Edge on Debian/Ubuntu-based Linux distributions.

## Google Chrome

To install Google Chrome, follow these steps:

1.  **Add the Google Chrome repository:**
    ```bash
    echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list
    ```

2.  **Add the Google signing key:**
    ```bash
    wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/google-chrome.gpg
    ```

3.  **Update your package list and install Google Chrome:**
    ```bash
    sudo apt update && sudo apt install google-chrome-stable
    ```

## Microsoft Edge

To install Microsoft Edge, follow these steps:

1.  **Install prerequisite packages:**
    ```bash
    sudo apt update && sudo apt install -y software-properties-common apt-transport-https ca-certificates curl
    ```

2.  **Add the Microsoft signing key and repository:**
    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
    sudo install -o root -g root -m 644 microsoft.gpg /etc/apt/trusted.gpg.d/
    sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/edge stable main" > /etc/apt/sources.list.d/microsoft-edge.list'
    rm microsoft.gpg
    ```

3.  **Update your package list and install Microsoft Edge:**
    ```bash
    sudo apt update && sudo apt install microsoft-edge-stable
    ```

---

## Snap Migration and Comparison

This repository also tracks the migration of applications from `apt` to `snap`, and compares the versions of applications available in both packaging formats.

*   **[Installed Snap Applications](./snap_management/snap_installed_list.md):** A list of all applications currently installed via Snap.
*   **[APT to Snap Migration Log](./snap_management/apt_to_snap_migration_log.md):** A log of applications that have been migrated from `apt` to `snap`.
*   **Application Comparisons:** A categorized comparison of applications available as both `apt` packages and `snap` packages.
    *   **[GNOME Apps](./snap_management/app_comparisons/gnome_apps.md)**
    *   **[Development Tools](./snap_management/app_comparisons/development_tools.md)**
    *   **[Office and Productivity](./snap_management/app_comparisons/office_and_productivity.md)**
    *   **[Utilities](./snap_management/app_comparisons/utilities.md)**
