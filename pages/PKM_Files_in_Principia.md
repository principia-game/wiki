The Android version of Principia uses the PKM file format for textures stored in the platform specific data folder (`data-mobile`).

PNG files can be converted to PKM using the `etc1tool` which is bundled in Android's platform tools.

Example usage would be as such:

```bash
etc1tool --encode "menu_bg.png" -o "menu_bg.pkm"
```
