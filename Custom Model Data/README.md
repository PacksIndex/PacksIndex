📘 Custom Model Data – Data Component Format
minecraft:custom_model_data

Type: [NBT Compound / JSON Object]

Purpose: A container of values used by item model definitions for model selection and coloring.

floats

Type: [NBT List / JSON Array] of [Float]

Used for: The range_dispatch model type (which selects a model based on a range of floats).

Behavior: If no matching value is found in the list, the model falls back to the default.

flags

Type: [Byte Array] (list of booleans)

Used for: The condition model type (model selection based on boolean flags).

Behavior: Missing values lead to the is_false model.

strings

Type: [NBT List / JSON Array] of [String]

Used for: The select model type (chooses models based on string values).

Behavior: If none of the strings match, the fallback model is used.

colors

Type: [NBT List / JSON Array] or [Int Array]

Purpose: Provides RGB values for tints applied by the model type’s coloring logic.

Details:

Each entry may be a list of floats or an integer.

If a list of floats is provided, it’s automatically converted to an integer internally and stored as an int array.

If values are missing, the default color from the item model definition is used.

🔍 Why This Matters

This format allows resource pack makers to define highly detailed custom models with advanced selection logic, including:

Choosing models based on numeric ranges (floats),

Using boolean flags (flags),

Matching text strings (strings),

Applying custom color tints (colors).

These systems give a lot more power than the older integer‑only model override system.
