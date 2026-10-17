# borked-craft-client-pack

[packwiz](https://packwiz.infra.link/) client modpack for the BorkedCraft Minecraft server. Pairs with the server pack [borked-craft-pack](https://github.com/pgmac/borked-craft-pack).

It is a port of henkelmax's [Xisuma's Hermitcraft Pack](https://modrinth.com/modpack/xisumas-hermitcraft-pack) 1.4.0 (Minecraft 26.2) to **Minecraft 26.3**. Not affiliated with Hermitcraft, Xisuma or henkelmax. Switch back to the upstream pack once it ships a 26.3 release.

## Installing

1. Download `borked-craft-client-vX.Y.Z.mrpack` from the [latest release](https://github.com/pgmac/borked-craft-client-pack/releases/latest).
2. Modrinth App: **+ Create** → **Import** → choose the `.mrpack`.

Prism Launcher can import the same file, or use [packwiz-installer](https://packwiz.infra.link/tutorials/installing/packwiz-installer/) against `https://raw.githubusercontent.com/pgmac/borked-craft-client-pack/main/pack.toml`.

Resource packs (Xisuma's VT, Bushy Leaves, Redstone Tweaks) are included but not switched on. Enable them under Options → Resource Packs.

## Differences from upstream 1.4.0

| Change | Reason |
| --- | --- |
| All mods bumped to their 26.3 builds | Target version |
| Fabric loader 0.19.3 → 0.20.0 | Latest for 26.3, matches the server |
| Redstone Tweaks 2.5.5 → 2.5.6 (options carried over) | 26.3 build |
| Added Voxy Server Side | Matches the server. Needs [Voxy](https://modrinth.com/mod/voxy), which has no 26.3 build yet |
| Added Xaero's Minimap | Local preference |
| Removed Shade & Saturation Slider (`sss`) | No 26.3 build |
| Removed Better Third Person | Shipped disabled upstream; no build since 1.21.8 |
| Enhanced Anvils, Big Sign Writer are optional, off by default | Shipped disabled upstream |

Xisuma's VT resource pack is still the 26.2 build. Minecraft may flag it as made for an older version; it loads anyway.

## Releasing

```bash
packwiz update --all     # bump mods
packwiz refresh          # after adding or removing files
# bump version in pack.toml, merge, then:
git tag v1.0.1 && git push origin v1.0.1
```

The `release` workflow exports the `.mrpack` and attaches it to a GitHub release. The tag must match `version` in `pack.toml`.
