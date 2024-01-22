# /vg/station RUST-G

This repository holds /vg/station modifications of [rust-g](https://github.com/tgstation/rust-g) libraries from /tg/station.

This works by keeping a folder of /vg/station patches to be applied, and applies it to a specific version tag of tg's rust-g. This reduces our need for major reworks to code, as we can just use patches to achieve what we need without cluttering the main tree.

## License

The license for RUST-G itself can be found on tg's repo. Code for the /vg/station modifications falls under the same license.

## How to (Compiling)

1. You **must** have a copy of `Git Bash` or some other bash emulator on windows, and a git identity setup. This will not work otherwise.
2. Run the `apply_patches.sh` file to autocreate a clone of `tg-rust-g`, and apply the patches to it.
3. Paradise RUST-G requires all features to be enabled, so this one does too. It could be slimmed down, probably.
    - To build on Windows, run `cargo build --release --features=all --target=i686-pc-windows-msvc`. This will generate a 32-bit `.dll` file that is compatible with BYOND.
    - To build on Linux, run `cargo build --release --features=all --target=i686-unknown-linux-gnu`. This will generate a 32-bit `.so` file that is compatible with BYOND.

If you are still stuck, check tg's README for more detailed instructions.

## How to (Developing)

1. You **must** have a copy of `Git Bash` or some other bash emulator on windows, and a git identity setup. This will not work otherwise.
2. Run the `apply_patches.sh` file to autocreate a clone of `tg-rust-g`, and apply the patches to it.
3. Open the folder called `vg-rust-g` inside an IDE of your choice. Make your edits in here.
4. Save your edits as a single commit inside `vg-rust-g`. Do not push changes. Do not modify `tg-rust-g`.
5. Run the `rebuild_patches.sh` script to convert your commit into a patch that will be saved in the `vg_patches` directory

## Credits

- /tg/station for the original RUST-G works.
- SpigotMC for the patching logic.
- ParadiseSS13 for adapting this patching logic for use with rust-g.