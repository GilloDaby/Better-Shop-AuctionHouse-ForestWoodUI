# BetterShopAuction Forest Wood UI Pack

Asset-only companion plugin for [BetterShopAuction](../Better-Shop-AuctionHouse) that
swaps the modern dark/cyan theme for a warm **oak / pine / moss / leaf**
forest-wood look.

This pack ships:

- A custom `BetterShopCommon.ui` with a forest color palette (sage moss,
  bleached birch, oak brown, honey amber).
- All 45 page-level `.ui` files re-pointing button / container / dropdown /
  input textures from `Textures/ModernShop/...` → `Textures/ForestWoodShop/...`.
- A texture folder under `Common/UI/Custom/Textures/ForestWoodShop/` ready
  for forest-themed PNG art.

## Installation

1. Build the jar: `gradle jar` — produces `build/libs/BetterShopAuctionForestWoodUI-1.0.0.jar`.
2. Drop the jar into your server's `mods/` folder alongside `BetterShopAuction`.
3. **Do NOT install** the modern `BetterShopAuctionExtensionsUI` or
   medieval `BetterShopAuctionMedievalUI` packs at the same time — all three
   packs override the same `.ui` paths and will conflict. Pick one theme.
4. Restart the server. Open any shop / auction / market UI in-game and verify
   the new theme appears.

## What's currently shipped vs. what you need to provide

The PNG **textures shipped right now are copies of the medieval pack as
starting placeholders**. The `.ui` overrides and color palette are already
forest-themed — but until you swap the textures, your UI will mix forest
colors with parchment/leather button art. To finish the theme, replace the
PNGs in `src/main/resources/Common/UI/Custom/Textures/ForestWoodShop/` with
forest art that respects the **same image dimensions and 9-patch border
pixel counts** as the originals.

### Texture inventory (58 files to replace)

#### Buttons (`Patches/Buttons/`)
9-patch borders: `VerticalBorder: 12, HorizontalBorder: 80` for primary /
destructive variants; `Border: 12` for secondary / tertiary.

| File | Suggested forest art |
|---|---|
| `Primary.png` / `Primary_Hovered.png` / `Primary_Pressed.png` | Carved oak plank with bronze nail studs, glowing moss inlay on hover |
| `Secondary.png` / `Secondary_Hovered.png` / `Secondary_Pressed.png` | Birch bark with rope binding |
| `Tertiary.png` / `Tertiary_Hovered.png` / `Tertiary_Pressed.png` / `Tertiary_Active.png` | Pine wood plank with iron rivets |
| `Destructive.png` / `Destructive_Hovered.png` / `Destructive_Pressed.png` | Charred wood / red maple leaf trim with thorns |
| `Disabled.png` | Rotten greyed wood |

#### Buy / Sell buttons (`BuyButton/`, `SellButton/`)

| File | Suggested forest art |
|---|---|
| `Buy.png` / `Buy_Hovered.png` / `Buy_Pressed.png` | Honey amber wooden plaque with leaf engraving |
| `Sell.png` / `Sell_Hovered.png` / `Sell_Pressed.png` | Sage moss plaque with golden mushroom corner detail |

#### Container chrome (`Patches/`)
`Border: 23` for content patches, `HorizontalBorder: 35..50` for headers.

| File | Suggested forest art |
|---|---|
| `ContainerPatch.png` | Aged oak panel with knot details |
| `ContainerPanelPatch.png` / `ContainerPanelLightPatch.png` | Lighter inner pine board |
| `ContainerFullPatch.png` | Treehouse panel framed with carved branches |
| `ContainerHeader.png` / `ContainerHeaderNoRunes.png` | Carved bark header with vine motifs |
| `ContainerSectionSeparator.png` | Thin vine + leaf divider |
| `ContainerCloseButton.png` / `ContainerCloseButtonHovered.png` / `ContainerCloseButtonPressed.png` | Knotted wood "X" with leaf accent |

#### Dropdowns (`Patches/`)

| File | Suggested forest art |
|---|---|
| `Dropdown.png` / `DropdownHovered.png` / `DropdownPressed.png` | Sunken bark trough with subtle moss line |
| `DropdownBox.png` | Open scroll-of-leaves panel |
| `DropdownCaret.png` / `DropdownPressedCaret.png` | Small bronze leaf arrow |

#### Inputs (`Patches/`)

| File | Suggested forest art |
|---|---|
| `InputBox.png` / `InputBoxHovered.png` / `InputBoxPressed.png` / `InputBoxSelected.png` | Carved wood text-trough with mossy border |
| `InputBinding.png` | Vine-binding indicator |

#### Scrollbar (`Patches/`)
`Border: 3`.

| File | Suggested forest art |
|---|---|
| `Scrollbar.png` | Vertical wooden trellis |
| `ScrollbarHandle.png` / `ScrollbarHandleHovered.png` / `ScrollbarHandleDragged.png` | Acorn or mushroom bead |

#### Rarity slot frames (`Rarities/`)

| File | Suggested forest art |
|---|---|
| `SlotDefault.png` / `SlotCommon.png` | Plain oak slot |
| `SlotUncommon.png` | Bronze acorn-trimmed slot |
| `SlotRare.png` | Silver birch-trimmed slot with sapphire dewdrop |
| `SlotEpic.png` | Honey-amber slot with golden mushroom corner |
| `SlotLegendary.png` | Ornate vine-wreathed slot with crystal leaf |
| `SlotJunk.png` | Rotten driftwood slot |

#### Container decorations (`Decorations/`) — overrides vanilla `Common/`
These are the ornate ribbons rendered at the top and bottom of every
`@DecoratedContainer` (used by **17 pages** — auctions, market, requests,
admin hubs, etc.).

| File | Anchor in markup | Suggested forest art |
|---|---|---|
| `ContainerDecorationTop.png` | `Width: 236, Height: 11, Top: -12` | Carved branch with leaf cluster center, dripping moss tendrils at extremities |
| `ContainerDecorationBottom.png` | `Width: 236, Height: 11, Bottom: -6` | Mirror of the top (vine garland with tassels of small mushrooms) |

#### Checkboxes (`CheckBox/`) — overrides vanilla `Common/`

| File | Anchor in markup | Suggested forest art |
|---|---|---|
| `CheckBoxFrame.png` | `22x22 px`, `Border: 7` (9-patch) | Bark-trimmed wood square frame |
| `Checkmark.png` | `22x22 px` (no patch border) | Glowing moss "✓" or carved leaf shape |

#### Sliders (`Slider/`) — overrides vanilla `Common/`

| File | Spec | Suggested forest art |
|---|---|---|
| `SliderBackground.png` | `Border: 2` (9-patch), height ≈ 5px | Wooden rail with vine accents |
| `SliderHandle.png` | `16x16 px` (no patch border) | Acorn or wooden knob with leaf detail |

## Color palette (already wired in `BetterShopCommon.ui`)

| Token | Hex | Usage |
|---|---|---|
| `@ColorDefault` | `#ebe2c9` | Bleached birch bark — main bright text |
| `@ColorDefaultLabel` | `#b8c89d` | Sun-faded leaf — default labels |
| `@ColorBlueAccent` | `#87a96b` | Sage moss (replaces blue accent) |
| `@ColorBlueAccentHovered` | `#a8c789` | Fresh moss (hover) |
| `@ColorBlueAccentPressed` | `#5a7a4a` | Deep forest moss (pressed) |
| `@ColorGoldHighlight` | `#c8a04d` | Honey amber (titles, important values) |
| `@ColorGrayCaption` | `#8a9b6e` | Olive caption |
| `@ColorButtonText` | `#e6dfc4` | Warm cream text on buttons |
| `@ColorDisabled` | `#5e5742` | Weathered wood (disabled) |
| `@ColorPlaceholder` | `#7a7252` | Damp earth placeholder text |
| `@ColorBackgroundCode` | `#1a2110` | Deep forest floor |

## Conflicts

This plugin and any other BetterShopAuction theme pack
(`BetterShopAuctionExtensionsUI`, `BetterShopAuctionMedievalUI`) cannot
coexist — they ship the same `.ui` file paths under
`Common/UI/Custom/Pages/`. Install **only one theme pack at a time**.

## License

Same as the parent BetterShopAuction project.
