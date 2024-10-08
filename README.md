## Disclaimer

This script is intended for use in authorized security testing and educational purposes only. Unauthorized use of this script on any system, network, or domain without explicit permission from the owner is illegal and unethical.

By using this script, you agree to take full responsibility for your actions and acknowledge that the author(s) of this script are not liable for any misuse or damage caused. Always ensure you have obtained proper authorization before conducting any security testing or vulnerability assessments.

**Remember:** Unauthorized hacking is illegal. Stay ethical and always work within the boundaries of the law.


# SVN Exposure Automation Script

## Overview

This script automates the process of identifying and exploiting exposed SVN `.svn/wc.db` files on target domains. It leverages tools such as `subfinder`, `httpx`, `nuclei`, `sqlite3`, and `wget` to find subdomains, detect exposed SVN directories, extract source code paths, and download the corresponding source code files.

## Prerequisites

Ensure you have the following tools installed:

- `subfinder`
- `httpx`
- `nuclei`
- `sqlite3`
- `wget`

Additionally, make sure you have the necessary Nuclei templates installed, particularly the `svn-wc-db.yaml` template located at:

/home/kali/nuclei-templates/http/exposures/files/svn-wc-db.yaml


    The script will:
        Find subdomains using subfinder.
        Check for live subdomains with httpx.
        Probe for exposed .svn/wc.db files using nuclei.
        Download the wc.db files if found.
        Extract source code paths from the wc.db files.
        Generate URLs for the source code files.
        Download the source code files using wget.

    Output Files:
        live_hosts.txt: List of live subdomains.
        svn_exposed.txt: List of subdomains with exposed .svn directories.
        wc_dbs/: Directory containing downloaded wc.db files.
        Snv_Database.txt: Paths to the source code files extracted from wc.db.
        Urls_generated.txt: URLs pointing to the source code files.
        Source_code/: Directory containing the downloaded source code files.

Notes

    Ensure you have permission to test the target domain before running this script.
    The script includes custom headers to identify your traffic during testing.
    Output files and directories will be created in the script's working directory.
