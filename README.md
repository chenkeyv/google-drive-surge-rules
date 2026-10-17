# Google Drive Surge Rules

Version: 2026.10.17.1

A deliberately small, manually maintained Surge RULE-SET for three observed Google Drive endpoints. Each line is an exact domain match with no policy column. This is not a complete Google Workspace allowlist.

| Host | Purpose |
| --- | --- |
| drive.google.com | Drive web app |
| drivefrontend-pa.clients6.google.com | Drive browser frontend API and observed upload endpoint |
| drivefrontend-pa.googleapis.com | Drive frontend API observed in the desktop client |

The latter two hosts were confirmed from Drive connections; Google documents the broader clients and APIs host families. No wildcard or shared Google domain is included. New endpoints should be reviewed before adding them. Download/export hosts such as drive.usercontent.google.com and drive-data-export.usercontent.google.com are not included because they were not observed in the upload workflow being addressed.

Usage in the Surge profile, before broader Google rules:

```ini
[Rule]
RULE-SET,https://raw.githubusercontent.com/chenkeyv/google-drive-surge-rules/main/GoogleDrive.list,DRIVE_FIXED_PROXY
```

Replace DRIVE_FIXED_PROXY with your own concrete proxy policy. Keep policy and node credentials in your private Surge configuration. To pin a reviewed version, replace main in the URL with its full commit SHA and add update-interval=-1. A downloaded local copy may also be referenced by its absolute path on Surge Mac.

Rollback: remove this RULE-SET reference, or restore the previously reviewed file/commit. This repository does not change active connections or local settings.

Sources, checked 2026-10-17:

- [Google Drive and Sites firewall and proxy settings](https://knowledge.workspace.google.com/admin/drive/drive-and-sites-firewall-and-proxy-settings?hl=en)
- [Surge RULE-SET format and local-file support](https://manual.nssurge.com/rules/ruleset.html)

Only this README and the domain rules belong in the public repository.
