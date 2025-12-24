# DID:nostr Explorer

A lightweight, client-side explorer for Nostr Decentralized Identifiers (DIDs).

## Features

- **DID Resolution**: Fetches DID documents from providers (default: nostr.rocks)
- **Profile Display**: Shows profile info from Nostr relays (kind 0)
- **Follows List**: Displays follows with pagination (kind 3)
- **Deep Linking**: Share links via URL hash (e.g., `#<pubkey>`)
- **Dark Mode**: Respects system preference

## Usage

Visit the explorer at: https://nostrapps.github.io/did-explorer/

Enter a DID or pubkey:
- `did:nostr:f0af1224d58d3f8c4e64d0182b3ec9966b3f2632f392c64eee669a627dfa6c71`
- `f0af1224d58d3f8c4e64d0182b3ec9966b3f2632f392c64eee669a627dfa6c71`

## Tech Stack

- **Preact + htm**: Lightweight React alternative (~4kb)
- **TailwindCSS**: Utility-first CSS (CDN)
- **No build step**: Pure ES modules, runs directly in browser

## DID:nostr Specification

This explorer implements the [DID:nostr specification](https://nostrcg.github.io/did-nostr/).

A DID:nostr identifier has the format:
```
did:nostr:<64-char-hex-pubkey>
```

## Self-Hosting

Simply serve `index.html` from any static host. No build required.

```bash
# Local development
python -m http.server 8000

# Or with Node
npx serve .
```

## Provider API

The explorer fetches DID documents from:
```
GET https://<provider>/.well-known/did/nostr/<pubkey>.json
```

Default provider is `https://nostr.rocks`. You can change it in the UI.

## License

MIT
