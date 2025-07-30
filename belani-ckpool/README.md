# CKPool Umbrel App

This is an Umbrel-compatible app that runs a CKPool solo mining stratum server in Docker and connects to Umbrel's built-in Bitcoin node.

## Features

- Dockerized CKPool
- Exposes Stratum server on port `3333`
- Supports optional stats API/UI on `8000`
- Uses Umbrel's Bitcoin Core node via env variables

## Installation

Clone into Umbrel's `apps` folder and run:

```bash
umbrel dev
```

Or install via the Umbrel Community App Store.
