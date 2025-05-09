# Data Gen

This repository is a simple tool which connects
to [BDS](https://www.minecraft.net/en-us/download/server/bedrock)
using [gophertunnel](https://github.com/Sandertv/gophertunnel) and generates necessary data
for [Dragonfly](https://github.com/df-mc/dragonfly) updates.

## Usage

1. Download the [latest version of BDS](https://www.minecraft.net/en-us/download/server/bedrock) and run the
   server. You will also need to generate a vanilla world with education features and any other appropriate
   experiments enabled. Ensure `block-network-ids-are-hashes` is disabled within BDS `server.properties` aswell.
2. Make sure `data/block_state_meta_map.json` and `data/canonical_block_states.nbt` are up-to-date
   from [BedrockData](https://github.com/pmmp/BedrockData) (or newly generated
   from [bds-mod-mapping](https://github.com/pmmp/bds-mod-mapping))
3. Run `go run main.go` and authenticate with Xbox if it is your first time running the tool
4. Once the data is generated, copy the required folders from `output` into the desired location

> [!NOTE]
> All `.nbt` files use the network-encoding variant of NBT.

> [!TIP]
> The tool will generate the data in a structured format, allowing you to easily copy the data into the
> respective repositories.

## Dragonfly data (output/dragonfly)

| File                                                                                                                                  | Description                                                                         |
|---------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| [server/item/creative/creative_items.nbt](https://github.com/df-mc/dragonfly/blob/master/server/item/creative/creative_items.nbt)     | This file contains the creative groups and items in the vanilla order               |
| [server/item/recipe/crafting_data.nbt](https://github.com/df-mc/dragonfly/blob/master/server/item/recipe/crafting_data.nbt)           | This file contains a list of shaped and shapeless crafting recipes                  |
| [server/item/recipe/furnace_data.nbt](https://github.com/df-mc/dragonfly/blob/master/server/item/recipe/furnace_data.nbt)             | This file contains a list of furnace recipes                                        |
| [server/item/recipe/potion_data.nbt](https://github.com/df-mc/dragonfly/blob/master/server/item/recipe/potion_data.nbt)               | This file contains a list of brewing stand recipes                                  |
| [server/item/recipe/smithing_data.nbt](https://github.com/df-mc/dragonfly/blob/master/server/item/recipe/smithing_data.nbt)           | This file contains a list of recipes for the smithing table, excluding armour trims |
| [server/item/recipe/smithing_trim_data.nbt](https://github.com/df-mc/dragonfly/blob/master/server/item/recipe/smithing_trim_data.nbt) | This file contains a list of recipes for armour trims in the smithing table         |
| [server/vanilla_items.nbt](https://github.com/df-mc/dragonfly/blob/master/server/world/item_runtime_ids.nbt)                          | This file contains a list of all vanilla items with their runtime ID and version    |
