# TrustCore-TPM v1.0.1 Release Notes

## Overview

TrustCore-TPM v1.0.1 is a production-ready Python library for hardware-based device fingerprinting using TPM 2.0. This release includes professional documentation and the correct package name.

## Installation

```bash
pip install trustcore-tpm
```

## What's New in v1.0.1

### Package Updates
- **Correct Package Name**: Now published as `trustcore-tpm` (previously `tpm-fingerprint-lib`)
- **Updated Metadata**: Correct GitHub repository URLs and project information

### Documentation Improvements
- **Professional Documentation**: Removed emojis and marketing language
- **Technical Focus**: Industry-standard terminology throughout
- **Enhanced Diagrams**: Added Mermaid diagrams for better visualization
  - Component architecture diagram
  - Data flow sequence diagram
  - State machine diagram
  - Anti-cloning flow diagram
  - Policy enforcement diagram
  - Trust chain diagram

### Removed
- Patent-related language and terminology
- PATENTS.md file
- Marketing and promotional language

## Features

- Hardware-rooted device fingerprinting using TPM 2.0
- PCR-based state binding for platform integrity
- Cryptographic sealing with AES-256-GCM
- Challenge-response authentication protocol
- Automatic policy enforcement
- Offline verification capability
- Comprehensive audit logging

## Requirements

- Python 3.8+
- TPM 2.0 hardware (or software simulator)
- Windows: WMI access for TPM operations
- Linux: tpm2-tools package

## Quick Start

```python
from tpm_fingerprint_lib import OfflineVerifier

# Initialize verifier
verifier = OfflineVerifier()

# Enroll device
device_id = "device-001"
result = verifier.enroll_device(device_id)

if result["success"]:
    print(f"Device enrolled: {result['fingerprint_id']}")
    
# Verify device
verification = verifier.verify_device(device_id)
print(f"Valid: {verification['valid']}")
```

## Documentation

- [README.md](README.md) - Main documentation
- [QUICKSTART.md](QUICKSTART.md) - Quick start guide
- [ARCHITECTURE.md](ARCHITECTURE.md) - Detailed architecture
- [USAGE_GUIDE.md](USAGE_GUIDE.md) - Complete usage guide
- [DIAGRAM_INDEX.md](DIAGRAM_INDEX.md) - Visual diagram index

## Links

- **PyPI**: https://pypi.org/project/trustcore-tpm/1.0.1/
- **GitHub**: https://github.com/Johnsonajibi/Trustcore-TPM
- **Issues**: https://github.com/Johnsonajibi/Trustcore-TPM/issues

## Changelog

### Added
- Mermaid architecture diagrams in README
- Professional technical documentation
- Complete API reference
- Comprehensive examples

### Changed
- Package name from `tpm-fingerprint-lib` to `trustcore-tpm`
- Documentation tone to industry standard
- CLI command from `tpm-fingerprint` to `trustcore-tpm`

### Removed
- Emojis from all documentation
- Patent-related terminology
- Marketing language
- PATENTS.md file

## Credits

Developed and maintained by the TrustCore-TPM team.

## License

MIT License - see [LICENSE](LICENSE) file for details.
