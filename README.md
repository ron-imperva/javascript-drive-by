# JavaScript Drive-By

## Overview

Inspired by the "Java Drive-By" attacks from the early 2000s, this repository contains proof-of-concept (PoC) exploits demonstrated in the blog post, "Java(Script) Drive-By: Hacking Without 0days." that show how the File System Access API in Chromium-based browsers can be abused to achieve arbitrary code execution on macOS systems.

## Warning ⚠️

**This repository is intended for educational purposes only.** The PoC code provided here should not be used for unauthorized activity or to harm other users. Unauthorized use of this code may violate local, state, and federal laws. By using this code, you agree to abide by all relevant legal obligations and ethical responsibilities.

## How It Works

The exploit abuses the Chromium blocklist and the limitations of macOS Gatekeeper:
- **Chromium Blocklist Bypass**: Chrome’s blocklist restricts write access to critical directories, but drag-and-drop file selection bypasses this restriction.
- **macOS Gatekeeper Limitations**: The API's added quarantine attribute isn't rechecked by Gatekeeper when executed by Chrome, leaving users vulnerable if they grant access to malicious files.

## PoC Limitations
- Multiple Profiles: This exploit may not work if multiple Google profiles are used in Chrome and the default profile is not the one used during the exploit.
- If Chrome updates during the exploit, it may fail due to changes in file paths or permissions.
