# KunBlocker Data

Public database distribution for KunBlocker iOS.

## Files

- `us-spam.json` — US suspected spam caller identification database.
- `manifest.json` — Version, timestamp, file size, and SHA-256 checksum.

## Data source

The database is generated from public FCC consumer complaints.

Only complaints categorized as Phone / Unwanted Calls are considered.
Numbers require at least two reports within the collection window.

## Important limitations

- Complaint records are unverified.
- Caller ID numbers may be spoofed.
- Presence in this database does not prove that a number is malicious.
- The database is for caller identification only, not automatic blocking.

KunBlocker maintains personal blocking rules separately.

## Updates

Database candidates are generated and validated by the private
KunBlocker repository's GitHub Actions workflow before publication.

## US Curated Blocklist

- `us-blocklist.json` — Curated US phone numbers intended for blocking.
- `blocklist-manifest.json` — Version, entry count, file size, and SHA-256 checksum.

These numbers were collected from user-provided screenshots. They are not independently verified by the FCC.

The blocklist is separate from the FCC spam identification database. KunBlocker uses this list for blocking and the FCC list for caller identification.
