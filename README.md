# TF2 patcher for full-colored decals

## Summary

This tool allows you to remove various restrictions when applying a decal to a decalable item in TF2.

In short, now you can apply fully-colored images to your Objectors, Flairs, Photo Badges and Clan Prides.

This is a June 2024 fix of [tf2patcher](https://github.com/default-username-was-already-taken/tf2patcher). The original
tool was abandoned and likely broke due to the TF2 64-bit update.

## Is it safe?

> [!CAUTION]  
> **USE AT YOU OWN RISK.**
>
> It is unlikely that this tool will be detected by VAC. **However:**
>
> - It may be a good idea to take a look at current active issues;
> - After running this tool, **be sure to close TF2**. You can then safely open it again. This is not strictly
    necessary, but it's best to clear all memory modifications before connecting to a secure server.

## How to use

1. Download the latest release [here](https://github.com/dborodin836/tf2patcher/releases/latest);

2. Run tf2patcher.exe and launch TF2 (or do it in reverse, the order does not matter);

3. Now try applying a decal to your item - the preview pane should show a fully-colored image;

4. **After you've applied your decal, close TF2 in order to remove any modifications caused by the patcher.**

## Building from source

Run `make TARGET=32` or `make TARGET=64`, depending on which architecture you want to build for.

C11-aware compiler is required.

## How does it work

What exactly gets patched:

- m_pFilterCombo->GetActiveItem() call gets changed to "mov eax, 1" (reg/imm32 form) - this forces an "Identity" filter
  no matter what the schema says;

- bDoBlendLayers conditional jump gets changed to an inconditional jump (this skips all blending code altogether).

## Linux support?

Currently, this project can only be built for Windows (both x86 and x86-64).

I may add Linux support later, but I don't feel like doing it right now.

## License

See UNLICENSE file.
