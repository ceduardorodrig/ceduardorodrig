# Validation Scripts

This directory replaces the old `cvcheck/`. Validation is now done
by the unified **StênioKernel**, located at:

```
/mnt/NVME_PCI/agentic-ai/sumaenimahub/sumaenima-hub/scripts/steniocheck
```

## Usage

```bash
# Rodar todas as verificações do perfil resume
./scripts/stenio_check

# Auto-teste do kernel
./scripts/stenio_check --self-test

# Listar drivers disponíveis
./scripts/stenio_check 2>&1 | grep resume_
```

The `resume` profile includes 10 drivers that validate:
- PT-BR dates
- Spelling (PT and EN)
- Bilingual parity
- Acronyms with definition
- Images with alt text
- Loose content
- Table of contents (TOC)
- Consistent tone

## CI (GitHub Actions)

The `.github/workflows/ci.yml` workflow runs the same validation on every push. It checks out
**SUMAENIMA-HUB** (the kernel's private repository) via SSH deploy key and runs:

```bash
PYTHONPATH=<sumaenima-hub>/scripts \
  python3 -m steniocheck --tag resume --scope static --format github
```

The same kernel code runs locally and in CI — unified governance.

### CI Security

Access to SUMAENIMA-HUB uses a **read-only SSH deploy key**, without exposing the user's
account credentials. The private key is stored as an encrypted GitHub Actions secret
(`STENIOCHECK_SSH_KEY`) and never appears in logs or in the source code.
