# Multi-Platform Matrix Build with Artifacts

This repository demonstrates a GitHub Actions workflow with matrix build strategy that builds across multiple platforms and Node.js versions in parallel.

## Overview

The workflow showcases:
- **Matrix Strategy**: Builds across 3 operating systems (Ubuntu, macOS, Windows) and 3 Node.js versions (16, 18, 20)
- **Parallel Execution**: 9 jobs run simultaneously (3 OS × 3 Node versions)
- **Artifact Management**: Each job generates and uploads unique build artifacts
- **Build Information**: Artifacts contain system info, build metadata, and timestamps

## Matrix Configuration

The workflow uses a matrix strategy with the following dimensions:

- **Operating Systems**: 
  - `ubuntu-latest`
  - `macos-latest`
  - `windows-latest`

- **Node.js Versions**: 
  - `16`
  - `18`
  - `20`

This results in **9 parallel build jobs**, each producing a unique artifact.

## Build Artifacts

Each matrix job generates an artifact named: `build-eeefeec-<os>-node<version>`

Examples:
- `build-eeefeec-ubuntu-latest-node16`
- `build-eeefeec-macos-latest-node18`
- `build-eeefeec-windows-latest-node20`

### Artifact Contents

Each artifact contains:
1. `build-output.txt` - Build information including OS, Node version, timestamp, and commit details
2. `build-artifacts/metadata.json` - JSON metadata about the build
3. `build-artifacts/status.txt` - Build status message

## Workflow Features

✅ Matrix build with 9 variants (3 OS × 3 Node.js versions)  
✅ All jobs run in parallel for efficiency  
✅ Each job produces a unique, non-empty artifact  
✅ Step identifier `matrix-eeefeec` included  
✅ Artifacts uploaded with `build-eeefeec-` prefix  
✅ Uses `actions/upload-artifact@v4`  

## Triggering the Workflow

The workflow runs on:
- Push to `main` or `master` branch
- Pull requests to `main` or `master` branch
- Manual trigger via workflow_dispatch

## Viewing Results

1. Go to the [Actions tab](https://github.com/shreyak541/Multi-Platform-Matrix-Build-with-Artifacts/actions)
2. Click on the latest workflow run
3. View all 9 matrix jobs and their status
4. Download artifacts from the "Artifacts" section

## Contact

**Email**: shreyak541@gmail.com

---

Repository: https://github.com/shreyak541/Multi-Platform-Matrix-Build-with-Artifacts
