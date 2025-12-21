# PyPI Publishing Guide for TrustCore-TPM

## Prerequisites

1. Install build tools:
```bash
pip install --upgrade pip setuptools wheel twine build
```

2. Create PyPI account at https://pypi.org/account/register/

3. Create API token at https://pypi.org/manage/account/token/

## Build the Package

```bash
# Clean previous builds
rm -rf build/ dist/ *.egg-info/

# Build distribution packages
python -m build
```

This creates:
- `dist/trustcore-tpm-1.0.0.tar.gz` (source distribution)
- `dist/trustcore_tpm-1.0.0-py3-none-any.whl` (wheel)

## Test on TestPyPI (Optional but Recommended)

```bash
# Upload to TestPyPI
python -m twine upload --repository testpypi dist/*

# Test installation
pip install --index-url https://test.pypi.org/simple/ trustcore-tpm
```

## Publish to PyPI

```bash
# Upload to PyPI
python -m twine upload dist/*

# You'll be prompted for:
# Username: __token__
# Password: pypi-AgEIcHlwaS5vcmc... (your API token)
```

## Verify Installation

```bash
pip install trustcore-tpm

python -c "from tpm_fingerprint_lib import OfflineVerifier; print('Success!')"
```

## Update Version

When releasing new versions:

1. Update version in `setup.py`:
   ```python
   version="1.0.1",
   ```

2. Update version in `tpm_fingerprint_lib/__init__.py`:
   ```python
   __version__ = "1.0.1"
   ```

3. Rebuild and upload:
   ```bash
   python -m build
   python -m twine upload dist/*
   ```

## Troubleshooting

### Build Errors
```bash
# Check setup.py syntax
python setup.py check

# View package contents
tar -tzf dist/trustcore-tpm-1.0.0.tar.gz
```

### Upload Errors
- Ensure version number hasn't been used before
- Check that all required files are included
- Verify API token is valid

## Package URL

After publishing, your package will be available at:
- https://pypi.org/project/trustcore-tpm/
- `pip install trustcore-tpm`

