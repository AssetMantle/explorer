# AssetMantle Explorer

The official block explorer for the [AssetMantle](https://assetmantle.one) chain (`mantle-1`), forked from [ping-pub/explorer](https://github.com/ping-pub/explorer).

Live at: **https://explorer.assetmantle.one**

## Endpoints

The explorer ships with the AssetMantle aggregator endpoints baked in:

- **RPC**: `https://rpc.assetmantle.one`
- **REST**: `https://rest.assetmantle.one`
- **gRPC**: `https://grpc.assetmantle.one`

The aggregator is a Caddy reverse proxy running on Akash that fronts a pool of community RPC nodes. See [assetmantle-infra](https://github.com/AssetMantle/assetmantle-infra) for the deployment configuration.

## Development

Requires Node 20 or 22 (Vercel deprecated 18).

```sh
yarn install --frozen-lockfile
yarn dev          # local dev server
yarn build        # production build → dist/
```

## Adding a chain

Drop a new JSON file into `chains/mainnet/` (or `chains/testnet/`). The Vite glob picks it up at build time. See `chains/mainnet/assetmantle.json` for the AssetMantle reference config.

## Upstream sync

Track upstream ping-pub:

```sh
git remote add upstream https://github.com/ping-pub/explorer.git
git fetch upstream
git merge upstream/master
```

## License

Apache-2.0 (inherited from upstream ping-pub/explorer).
